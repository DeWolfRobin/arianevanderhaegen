<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-parallax
        height="300"
        src="https://cdn.vuetifyjs.com/images/parallax/material2.jpg"
      ></v-parallax>
      <h1>test</h1>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
  head() {
    return {
      title: 'Home',
    }
  },
}
</script>

<style></style>
