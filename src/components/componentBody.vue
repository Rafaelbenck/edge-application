<template>
  <div>
    <componentHeader />
    <pageTitle />
    <Card />
    <componentParagraph />
  </div>
</template>

<script setup>
import pageTitle from "./pageTitle.vue";
import Card from "./Card.vue";
import componentParagraph from "./componentParagraph.vue";

import { ref, onMounted } from "vue";
import axios from "axios";

const nome = ref("");
const sobrenome = ref("");
const idade = ref("");
const profissao = ref("");
const caracteristicas = ref({});
const skills = ref({});
const report = ref("");

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
</script>
