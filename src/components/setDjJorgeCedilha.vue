<template>
  <v-container
    class="container-proprieties d-flex justify-center align-center"
    fluid
  >
    <v-row class="d-flex justify-center align-center">
      <v-col
        cols="12"
        class="spotify-iframe d-flex justify-center align-center"
      >
        <iframe
          style="border-radius: 12px"
          src="https://open.spotify.com/embed/playlist/2D0DXJVGiMUg44e8Ie8UhL?utm_source=generator"
          width="100%"
          height="352"
          frameBorder="0"
          allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
          loading="lazy"
        ></iframe>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.spotify-iframe {
  align-content: center;
}
</style>
