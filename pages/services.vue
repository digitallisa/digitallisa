<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="display-1">{{ title }}</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="3">
        <service-card title="Create google maps page" />
      </v-col>
      <v-col cols="3">
        <service-card title="Add Facebook Page" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ServiceCard from '~/components/services/serviceCard.vue'
export default {
  components: {
    ServiceCard
  },
  data() {
    return {
      title: 'Services'
    }
  }
}
</script>

<style></style>
