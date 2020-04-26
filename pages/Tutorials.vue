<template>
  <v-container>
    <v-row>
      <v-col cols="3">
        <tutorial-card :text="google" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="web" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="business" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="suchmaschine" />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="3">
        <tutorial-card :text="facebook" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="instagram" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="linkedIn" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="twitter" />
      </v-col>
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
      web: 'Google Ads',
      google: 'Create a Website',
      socialmedia: 'Social Media',
      business: 'Google Business',
      suchmaschine: 'Google Suche',
      facebook: 'Facebook',
      instagram: 'Instagram',
      linkedIn: 'LinkedIn',
      twitter: 'Twitter'
    }
  }
}
</script>

<style></style>
