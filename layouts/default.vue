<template>
  <v-app>
    <v-app-bar :clipped-left="clipped" flat color="white" fixed app>
      <nuxt-link style="width:50px" to="/">
        <v-img
          :src="require('~/assets/digitalLisaBlank.svg')"
          contain
          height="50"
          position="start start"
        ></v-img>
      </nuxt-link>
      <div class="display-1 text-uppercase font-weight-bold">DIGITALLISA</div>
      <div></div>
      <v-spacer></v-spacer>
      <v-btn outlined>
        Sign Up
      </v-btn>
    </v-app-bar>
    <v-content>
      <nuxt />
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'digitalLisa'
    }
  }
}
</script>
