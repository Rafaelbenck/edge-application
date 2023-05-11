<template>
  <div class="template-proprieties">
    <v-container class="d-flex">
      <v-col cols="12" class="d-flex justify-center align-center">
        <v-row>
          <v-col
            cols="6"
            class="d-flex justify-center align-center rounded-left"
            :padding="0"
          >
            <span class="text-hello"
              >Lorem Ipsum is simply dummy text of the printing and typesetting
              industry. Lorem Ipsum has been the industry's standard dummy text
              ever since the 1500s,
            </span>
          </v-col>
          <v-col cols="6" class="rounded-right">
            <playlist />
          </v-col>
        </v-row>
      </v-col>
    </v-container>
  </div>
</template>

<script setup>
import Playlist from "./Playlist.vue";
</script>

<style scoped>
.template-proprieties {
  background-color: #fff5ee;
}

.text-hello {
  font-size: 30px;
  font-weight: 400;
  font-family: "Work Sans", sans-serif;
  color: #000;
}
</style>
