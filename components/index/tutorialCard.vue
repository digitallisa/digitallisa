<template>
  <v-card max-width="400" height="100%" outlined>
    <v-list-item three-line>
      <v-list-item-content>
        <v-list-item-title class="headline mb-1">{{ text }}</v-list-item-title>
      </v-list-item-content>
      <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
    </v-list-item>
    <v-card-subtitle class="pb-0">{{ beschreibung }}</v-card-subtitle>

    <v-card-actions>
      <v-btn text color="deep-purple accent-4">View Tutorial</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: () => ''
    },
    beschreibung: {
      type: String,
      default: () => ''
    }
  }
}
</script>

<style></style>
