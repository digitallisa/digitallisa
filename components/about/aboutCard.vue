<template>
  <v-card outlined>
    <v-card-title>{{ title }}</v-card-title>
    <v-card-text>{{ text }}</v-card-text>
    <!-- <v-card-actions> -->
    <!-- <v-btn to="/chatbot" nuxt></v-btn> -->
    <!-- </v-card-actions> -->
  </v-card>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: () => ''
    },
    text: {
      type: String,
      default: () => ''
    }
  }
}
</script>

<style></style>
