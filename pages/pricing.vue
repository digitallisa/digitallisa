<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="display-4">
          Plans & Pricing
        </h1>
      </v-col>
    </v-row>
    <v-row justify="space-around">
      <v-col v-for="(plan, index) in plans" :key="index" cols="4">
        <pricing-card :plan="plan" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import PricingCard from '~/components/pricing/pricingCard.vue'
export default {
  components: {
    PricingCard
  },
  data() {
    return {
      plans: [
        {
          title: 'Free',
          keyPoints: [
            'No costs',
            'Learn by yourself with our verified tutorials'
          ],
          priceTitle: 'Free'
        },
        {
          title: 'Premium',
          keyPoints: [],
          priceTitle: 'Pay-Per-Use'
        }
      ]
    }
  }
}
</script>

<style></style>
