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
          title: 'Lisa & You Do It',
          proPoints: [
            'Completely Free',
            'Quick and easy process',
            'Lisa teaches you how to do it'
          ],
          contraPoints: [
            'You need to actually do it',
            'You need to maintain it'
          ],
          priceTitle: 'Free'
        },
        {
          title: 'We Do It For You',
          proPoints: [
            'You pay for what you get',
            'We create the requested page for you',
            'We do it quick and professionally'
          ],
          contraPoints: ['You need to maintain it'],
          priceTitle: 'Pay-Per-Service'
        },
        {
          title: 'We Do & Maintain It For You',
          proPoints: [
            'You pay for what you get',
            'We create the requested page for you',
            'We do it quick and professionally',
            'We maintain your requested page'
          ],
          contraPoints: [],
          priceTitle: 'Subscription'
        }
      ]
    }
  }
}
</script>

<style></style>
