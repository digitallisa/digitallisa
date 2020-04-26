<template>
  <v-btn rounded :disabled="answer.clickable">
    {{ answer.text }}
  </v-btn>
</template>

<script>
export default {
  props: {
    answer: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style></style>
