<template>
  <v-container height="520" class="d-flex container-proprieties">
    <v-col cols="6" class="d-flex justify-center align-center" padding="0px;">
      <v-row>
        <span class="text-hello">{{ nome }} {{ sobrenome }}</span>
      </v-row>
      <v-row>
        <v-btn @click="nextSlide" class="btn-saber-mais">Saber Mais</v-btn>
      </v-row>
    </v-col>
    <v-col cols="6" class="rounded-right">
      <v-img
        :width="500"
        src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
      ></v-img>
    </v-col>
  </v-container>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

const nome = ref("");
const sobrenome = ref("");

const fetchData = async () => {
  try {
    const response = await axios.get("http://oj7bby70j8.map.azionedge.net/");
    const data = response.data;

    nome.value = data.nome;
    sobrenome.value = data.sobrenome;
  } catch (error) {
    console.error(error);
  }
};

onMounted(fetchData);

const currentSlide = ref(0);

const items = [
  { image: "https://via.placeholder.com/400x400?text=Image+1", alt: "Image 1" },
  { image: "https://via.placeholder.com/400x400?text=Image+2", alt: "Image 2" },
  { image: "https://via.placeholder.com/400x400?text=Image+3", alt: "Image 3" },
];

function nextSlide() {
  currentSlide.value = (currentSlide.value + 1) % items.length;
}
</script>

<style scoped>
.container-proprieties {
  background-color: #008080;
  border: #fff;
  border-radius: 23px;
}
.text-hello {
  font-size: 32px;
  font-weight: bold;
}
.btn-saber-mais {
  background-color: #262627;
  color: #fff;
  margin-top: 16px;
}
</style>
