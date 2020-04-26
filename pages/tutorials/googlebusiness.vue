<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h2 class="display-3">
          Tutorial
        </h2>
      </v-col>
      <v-col cols="12">
        <v-divider></v-divider>
      </v-col>
      <v-col>
        <h3 class="display-2">
          Add your place to google business
        </h3>
      </v-col>
    </v-row>
    <v-row justify="space-around">
      <v-col cols="8">
        <v-row>
          <v-col cols="12">
            <v-card elevation="8">
              <v-container>
                <v-row>
                  <v-col cols="12">
                    <h4 class="title">
                      After doing this tutorial your place is available at
                      Google Maps...
                    </h4>
                  </v-col>
                  <v-col>
                    <v-img :src="require('~/assets/googlemaps.png')" />
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="4">
        <v-row>
          <v-col cols="12">
            <v-card elevation="8">
              <v-card-title>Duration</v-card-title>
              <v-card-subtitle>{{ duration }}</v-card-subtitle>
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-card elevation="8">
              <v-card-title>Requirements</v-card-title>
              <v-container class="pt-0 mt-0">
                <li v-for="(requirement, index) in requirements" :key="index">
                  {{ requirement }}
                </li>
              </v-container>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-row justify="end">
      <v-col cols="auto">
        <v-btn x-large rounded>
          Start Tutorial Now
          <v-icon right>mdi-arrow-right</v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      duration: 'Around 15 minutes',
      requirements: ['Email account', 'Google account']
    }
  }
}
</script>

<style></style>
