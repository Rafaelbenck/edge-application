<template>
  <div>
    <v-container height="520" class="d-flex container-proprieties">
      <v-col cols="12" class="d-flex justify-center align-center">
        <v-row>
          <v-col
            cols="6"
            class="d-flex justify-center align-center"
            :padding="0"
          >
            <v-row>
              <h1>{{ nome }} {{ sobrenome }}</h1>
              <span class="text-hello"
                >Lorem Ipsum is simply dummy text of the printing and
                typesetting industry. Lorem Ipsum has been the industry's
                standard dummy text ever since the 1500s,
              </span>
            </v-row>
          </v-col>
          <v-col cols="6" class="rounded-right">
            <Img />
          </v-col>
        </v-row>
      </v-col>
    </v-container>
    <v-container align="center">
      <div>
        <v-btn class="btn-saber-mais">Get Started</v-btn>
      </div>
    </v-container>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

import Img from "./Img.vue";

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
</script>

<style scoped>
.container-proprieties {
  background-color: #0b03f7d8;
  border: #fff;
  border-radius: 23px;
  padding: 4rem 2.5rem;
  margin-top: 40px;
}

h1 {
  font-size: 50px;
  font-weight: 500;
  font-family: "Work Sans", sans-serif;
  color: #f6ff00;
}
.text-hello {
  font-size: 32px;
  font-weight: 300;
  font-family: "Work Sans", sans-serif;
  color: #fff;
}

.btn-saber-mais {
  color: #262627;
  font-size: 13px;
  background-color: #f6ff00;
  font-weight: 700;
  font-family: "Work Sans", sans-serif;
  margin: 36px 0;
  width: 150px;
  height: 50px;
  border-radius: 33px;
}
.btn-saber-mais:hover {
  color: #f6ff00;
  background-color: #0b03f7d8;
}
</style>
