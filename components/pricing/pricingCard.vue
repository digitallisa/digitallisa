<template>
  <v-card class="d-flex flex-column" elevation="12" height="45vh" width="30vw">
    <v-sheet class="blue lighten-3" height="60px" width="100%">
      <v-container class="pa-0 fill-height" fluid>
        <v-row justify="center" align="center" no-gutters>
          <v-col cols="auto">
            <div class="display-1 font-weight-bold">
              {{ plan.title }}
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
    <div v-for="(keyPoint, kPIndex) in plan.keyPoints" :key="kPIndex" cols="12">
      <v-row align="end">
        <v-col cols="auto">
          <v-icon>mdi-check</v-icon>
        </v-col>
        <v-col class="font-weight-light" cols="auto">
          {{ keyPoint }}
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
