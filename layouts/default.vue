<template>
  <v-app class="app">
    <v-content>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import Footer from "~/components/Footer";

export default {
  components: { Footer }
};
</script>

<style>
</style>
