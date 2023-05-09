<template>
  <div>
    <template>
      <v-app-bar app color="red" elevate-on-scroll>
        <v-toolbar-title class="ml-4"> João </v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn text @click="scrollToAboutMe"> About Me </v-btn>
      </v-app-bar>
    </template>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

const nome = ref("");
const sobrenome = ref("");
const idade = ref("");
const profissao = ref("");
const caracteristicas = ref({});
const skills = ref({});
const report = ref("");

const scrollToAboutMe = () => {
  const aboutMe = document.getElementById("about-me");
  aboutMe.scrollIntoView({ behavior: "smooth" });
};

const fetchData = async () => {
  try {
    const response = await axios.get("http://oj7bby70j8.map.azionedge.net/");
    const data = response.data;

    nome.value = data.nome;
    sobrenome.value = data.sobrenome;
    idade.value = data.idade;
    profissao.value = data.profissao;
    caracteristicas.value = data.caracteristicas;
    skills.value = data.skills;
    report.value = data.report;
  } catch (error) {
    console.error(error);
  }
};

onMounted(fetchData);

const nomeCompleto = `${nome.value} ${sobrenome.value}`;
</script>

<style scoped></style>
