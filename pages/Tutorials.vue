<template>
  <v-container>
    <v-row>
      <tutorial-card :text="text" />
    </v-row>
  </v-container>
</template>

<script>
import TutorialCard from '~/components/Tutorial/TutorialCards.vue'
export default {
  components: {
    TutorialCard
  },
  data() {
    return {
      text: 'Google Ads'
    }
  }
}
</script>

<style></style>
