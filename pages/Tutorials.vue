<template>
  <v-container>
    <v-row align="stretch">
      <v-col cols="3" align-self="stretch">
        <tutorial-card :text="google" :beschreibung="b1" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="web" :beschreibung="b2" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="business" :beschreibung="b3" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="suchmaschine" :beschreibung="b4" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="facebook" :beschreibung="b5" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="instagram" :beschreibung="b6" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="linkedIn" :beschreibung="b7" />
      </v-col>
      <v-col cols="3">
        <tutorial-card :text="twitter" :beschreibung="b8" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import TutorialCard from '~/components/tutorials/tutorialCard.vue'
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
      suchmaschine: 'Google Search',
      facebook: 'Facebook',
      instagram: 'Instagram',
      linkedIn: 'LinkedIn',
      twitter: 'Twitter',
      b1: 'In this tutorial you learn how to create your own website',
      b2:
        'In this tutorial you can learn how to promote yourself with online adversitments',
      b3:
        'In this tutorial you can learn how to promote you business on all Google applications',
      b4:
        'In this tutorial you can learn how to be at the top of the google search results',
      b5:
        'In this tutorial you can lean how to set up the Facebook page for your business',
      b6:
        'In this tutorial you can learn how to set up the Instagram page for your business',
      b7:
        'In this tutorial you can learn how to set up the LinkedIn page for your business',
      b8:
        'In this tutorial you can learn how to set up the Twitter page for your business'
    }
  }
}
</script>

<style></style>
