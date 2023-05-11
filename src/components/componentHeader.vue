<template>
  <v-app-bar app>
    <v-toolbar-title class="header-title mr-12">Home</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn class="contact-me" @click="onButtonClick">Contact me</v-btn>
  </v-app-bar>
</template>

<script setup>
import { ref } from "vue";

const title = ref("My App");
const buttonLabel = ref("Button");

const onButtonClick = () => {
  // Implement your button click handler here
};
</script>

<style scoped>
.header-title {
  font-size: 28px;
  font-weight: 500;
  font-family: "Work Sans", sans-serif;
  color: #000;
}

.contat-me {
  color: #f6ff00;
  font-size: 25px;
  background-color: #262627;
  font-weight: 700;
  font-family: "Work Sans", sans-serif;
  margin: 36px 0;
  width: 150px;
  height: 50px;
}

.contact-me:hover {
  color: #fff;
  background-color: #0b03f7d8;
}
</style>
