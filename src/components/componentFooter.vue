<template>
  <v-footer
    class="text-center d-flex flex-column justify-content-center footer-proprieties"
  >
    <div>
      <v-btn
        v-for="icon in icons"
        :key="icon"
        class="mx-4"
        :icon="icon"
        variant="text"
      ></v-btn>
    </div>

    <div class="pt-0 text">
      Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris
      cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id
      ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui.
      Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada.
      Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin.
      Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius
      natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
    </div>

    <v-divider></v-divider>

    <div>{{ new Date().getFullYear() }} — <strong>Vuetify</strong></div>
  </v-footer>
</template>

<script setup>
import { ref } from "vue";

const icons = ["mdi-spotify", "mdi-github", "mdi-linkedin", "mdi-instagram"];
</script>

<style scoped>
.footer-proprieties {
  font-size: 15px;
  font-weight: 400;
  line-height: 1.5em;
  font-family: "Work Sans", sans-serif;
  margin-top: 100px;
}

.text {
  max-width: 80%;
}
</style>
