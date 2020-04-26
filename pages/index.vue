<template>
  <v-container fluid class="pa-0 ma-0">
    <v-row no-gutters>
      <main-container />
    </v-row>
    <v-row>
      <v-container>
        <v-row>
          <v-col v-for="(tutorial, index) in tutorials" :key="index" cols="4">
            <tutorial-card
              :text="tutorial.title"
              :beschreibung="tutorial.description"
            />
          </v-col>
        </v-row>
      </v-container>
    </v-row>
  </v-container>
</template>

<script>
import MainContainer from '~/components/index/mainContainer.vue'
import TutorialCard from '~/components/index/tutorialCard.vue'

export default {
  components: {
    MainContainer,
    TutorialCard
  },
  data() {
    return {
      tutorials: [
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
        }
      ]
    }
  }
}
</script>

<style></style>
