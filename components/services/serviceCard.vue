<template>
  <v-card>
    <v-card-title>{{ title }}</v-card-title>
    <v-card-actions>
      <v-btn to="/chatbot" nuxt></v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: () => ''
    }
  }
}
</script>

<style></style>
