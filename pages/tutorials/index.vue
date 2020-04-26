<template>
  <v-container>
    <v-row align="stretch">
      <v-col v-for="(tutorial, index) in tutorials" :key="index" cols="4">
        <tutorial-card
          :text="tutorial.title"
          :beschreibung="tutorial.description"
          :link="tutorial.link"
        />
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
      tutorials: [
        {
          title: 'Create a Website',
          description:
            'In this tutorial you learn how to create your own website'
        },
        {
          title: 'Google Ads',
          description:
            'In this tutorial you can learn how to promote yourself with online adversitments'
        },
        {
          title: 'Google Business',
          description:
            'In this tutorial you can learn how to promote you business on all Google applications',
          link: '/tutorials/googlebusiness'
        },
        {
          title: 'Google Search',
          description:
            'In this tutorial you can learn how to be at the top of the google search results'
        },
        {
          title: 'Facebook',
          description:
            'In this tutorial you can lean how to set up the Facebook page for your business'
        },
        {
          title: 'Instagram',
          description:
            'In this tutorial you can lean how to set up the Instagram page for your business'
        },
        {
          title: 'LinkedIn',
          description:
            'In this tutorial you can lean how to set up the LinkedIn page for your business'
        },
        {
          title: 'Twitter',
          description:
            'In this tutorial you can lean how to set up the Twitter page for your business'
        },
        {
          title: 'COVID-19 Measures',
          description:
            'Here we will post solutions for the current COVID-19 measures of each country'
        }
      ]
    }
  }
}
</script>

<style></style>
