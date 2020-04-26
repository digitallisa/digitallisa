<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="display-1">{{ title }}</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <about-card
          title="The Project"
          text="This project was initiated during the Hackathon #EuVsVirus that took place from April 24th until April 26th 2020. Our team took part of the challenge ‚new and resilient business models‘. 
During the COVID-1 crises many shops had to close. We figured out that especially small local businesses often don’t have online appearances to share current restrictions, news about business continuity or offered products with their customers.
This is not only due to missing technical skills but also because they are not aware of what online channels they could use.
That’s how our platform ‚DigitalLisa‘ came to life. Here we offer a 
knowledgebase with all available online channels business owners could make use of. Free Tutorials to show how to configure social media pages, websites or Google entries. And on top a premium service to set up desired channels for them if wished."
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <about-card
          title="The Team"
          text="We are: Daniel, Henrik, Melissa and Nils. All master students in the field of IT-Management and -Consulting and located in Hamburg. We all bring basic to advanced knowledge of business administration, project management, UI Design, backend and frontend development. Those skills made it possible to make up 'DigitalLisa' from the raw idea to this final Version 1.0 in only 48h time."
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <team-card title="The Team" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import AboutCard from '~/components/about/aboutCard.vue'
export default {
  components: {
    AboutCard
  },
  data() {
    return {
      title: 'About'
    }
  }
}
</script>

<style></style>
