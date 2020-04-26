<template>
  <v-app>
    <v-app-bar flat color="white" fixed app>
      <nuxt-link style="width:50px" to="/">
        <v-img
          :src="require('~/assets/digitalLisaBlank.svg')"
          contain
          height="50"
          position="start start"
        ></v-img>
      </nuxt-link>
      <div class="display-1 blue--text text--darken-4 font-weight-black">
        digitalLisa
      </div>
      <v-spacer></v-spacer>
      <v-btn
        v-for="(site, index) in navigationSites"
        :key="index"
        :to="site.page"
        nuxt
        text
        >{{ site.title }}
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn outlined>
        Sign Up
      </v-btn>
    </v-app-bar>
    <v-content>
      <nuxt />
    </v-content>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'digitalLisa',
      navigationSites: [
        {
          title: 'Tutorials',
          page: '/tutorials'
        },
        {
          title: 'Pricing',
          page: '/pricing'
        },
        {
          title: 'About Us',
          page: '/about'
        }
      ]
    }
  }
}
</script>
