<template>
  <v-container class="mt-16" fluid>
    <v-row>
      <v-col cols="12">
        <v-card>
          <v-img src="./assets/profile-image.jpg" alt="Profile Image"></v-img>
          <v-card-title class="text-center"
            >{{ nome }} {{ sobrenome }}</v-card-title
          >
          <v-divider></v-divider>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-card-title>Informações Pessoais</v-card-title>
                    <v-card-text>
                      <p>Idade: {{ idade }}</p>
                      <p>Profissão: {{ profissao }}</p>
                      <p>Nacionalidade: {{ caracteristicas.nacionalidade }}</p>
                      <p>
                        Orientação Sexual:
                        {{ caracteristicas.orientacaoSexual }}
                      </p>
                    </v-card-text>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-card-title>Skills</v-card-title>
                    <v-card-text>
                      <p>Linguagens de Programação:</p>
                      <ul>
                        <li
                          v-for="linguagem in skills.linguagensProgramacao"
                          :key="linguagem"
                        >
                          {{ linguagem }}
                        </li>
                      </ul>
                      <p>Sistemas Operacionais:</p>
                      <ul>
                        <li v-for="so in skills.sistemasOperacionais" :key="so">
                          {{ so }}
                        </li>
                      </ul>
                      <p>Bancos de Dados:</p>
                      <ul>
                        <li v-for="bd in skills.bancosdeDados" :key="bd">
                          {{ bd }}
                        </li>
                      </ul>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="primary" outlined>Contato</v-btn>
            <v-btn color="primary" outlined>LinkedIn</v-btn>
            <v-btn color="primary" outlined>Github</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
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
