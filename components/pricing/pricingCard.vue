<template>
  <v-card class="d-flex flex-column" elevation="12" height="45vh" width="30vw">
    <v-sheet class="blue darken-4" height="60px" width="100%">
      <v-container class="pa-0 fill-height" fluid>
        <v-row justify="center" align="center" no-gutters>
          <v-col cols="auto">
            <div class="headline font-weight-bold white--text">
              {{ plan.title }}
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <div
      v-for="(proPoint, proIndex) in plan.proPoints"
      :key="proIndex"
      cols="12"
      class="ml-3"
    >
      <v-row align="end">
        <v-col cols="auto">
          <v-icon>mdi-check</v-icon>
        </v-col>
        <v-col class="font-weight-regular body-1" cols="auto">
          {{ proPoint }}
        </v-col>
      </v-row>
    </div>
    <div
      v-for="(contraPoint, contraIndex) in plan.contraPoints"
      :key="contraIndex"
      cols="12"
      class="ml-3"
    >
      <v-row align="end">
        <v-col cols="auto">
          <v-icon>mdi-minus</v-icon>
        </v-col>
        <v-col class="font-weight-medium body-1" cols="auto">
          {{ contraPoint }}
        </v-col>
      </v-row>
    </div>
    <div class="fill-height"></div>
    <v-divider></v-divider>
    <v-row justify="center" align="center">
      <v-col cols="auto">
        <div class="title">
          {{ plan.priceTitle }}
        </div>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  props: {
    plan: {
      type: Object,
      default: () => ''
    }
  }
}
</script>

<style></style>
