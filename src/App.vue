<template>
  <v-app>
    <v-main>
      <componentHeader />
      <componentBody />
      <componentFooter />
    </v-main>
  </v-app>
</template>

<script setup>
import componentHeader from "./components/componentHeader.vue";
import componentBody from "./components/componentBody.vue";
import componentFooter from "./components/componentFooter.vue";

import { ref, onMounted } from "vue";
import { useDisplay } from "vuetify";

const { mobile } = useDisplay();

onMounted(() => {
  console.log(mobile.value);
});
</script>
