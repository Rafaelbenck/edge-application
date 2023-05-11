<template>
  <v-container
    class="container-proprieties d-flex justify-center align-center"
    fluid
  >
    <v-row class="d-flex justify-center align-center">
      <v-col cols="12" class="d-flex justify-center align-center">
        <span class="text text-center">
          "Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s."
        </span>
      </v-col>

      <v-col cols="12" class="avatar d-flex justify-center align-center">
        <v-avatar size="120">
          <v-icon size="80">mdi-account-circle</v-icon>
        </v-avatar>

        <div>
          <v-col cols="12">
            <span class="name">João Silva</span>
          </v-col>

          <span class="description">
            Lorem Ipsum is simply dummy text of the printing and typesetting
            industry.
          </span>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup></script>

<style scoped>
.container-proprieties {
  margin: 100px 0;
}
.text {
  font-size: 35px;
  font-weight: 400;
  line-height: 1.2em;
  max-width: 80%;
  font-family: "Work Sans", sans-serif;
}

.name {
  font-size: 15px;
  font-weight: 700;
  line-height: 1.5em;
  font-family: "Work Sans", sans-serif;
}

.description {
  font-size: 15px;
  font-weight: 400;
  line-height: 1.5em;
  font-family: "Work Sans", sans-serif;
}

.avatar {
  margin: 10px 0;
}
</style>
