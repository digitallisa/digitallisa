<template>
  <v-card color="blue" max-width="75%">
    <v-container>
      <v-row dense>
        <v-col class="white--text"> {{ question }}</v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  props: {
    question: {
      type: String,
      default: () => ''
    }
  }
}
</script>

<style></style>
