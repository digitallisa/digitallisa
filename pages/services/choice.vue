<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Choose your services</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="8">
        <v-container>
          <v-row>
            <v-col v-for="(service, index) in services" :key="index" cols="12">
              <service-card :service="service" @serviceChosen="serviceChosen()"
            /></v-col>
          </v-row>
        </v-container>
      </v-col>
      <v-divider vertical></v-divider>
      <v-col cols="3">
        <v-row justify="center">
          <v-col cols="12">
            <div class="display-1">Chosen services</div>
          </v-col>
          <v-col
            v-for="(chosenService, index) in chosenServices"
            :key="index"
            cols="12"
          >
            <v-row justify="space-between" align="center">
              <v-col cols="auto">
                <span class="font-weight-thin">{{ chosenService.title }}</span>
              </v-col>
              <v-col cols="auto">
                <v-btn icon>
                  <v-icon>mdi-close</v-icon>
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12">
            <v-divider></v-divider>
          </v-col>
          <v-col cols="12">
            <span class="font-weight-bold">Price </span
            ><span>{{ overallPrice }}€</span>
          </v-col>
          <v-col cols="auto">
            <v-btn dark color="black">
              Buy Now
            </v-btn>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ServiceCard from '~/components/services/choice/serviceCard.vue'
export default {
  components: {
    ServiceCard
  },
  data: () => ({
    chosenServices: [],
    services: [
      {
        title: 'Google Business',
        subtitle: 'Set-up Google Business Account'
      },
      {
        title: 'Facebook',
        subtitle: 'Set-up Facebook'
      }
    ]
  }),
  computed: {
    overallPrice() {
      let overallPrice = 0
      this.chosenServices.forEach((element) => {
        overallPrice = overallPrice + element.price
      })
      return overallPrice
    }
  },
  methods: {
    serviceChosen() {
      this.chosenServices.push({
        title: 'Google Business',
        price: 50
      })
    }
  }
}
</script>

<style></style>
