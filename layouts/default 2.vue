<template>
  <v-app>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title class="font-weight-medium" v-text="title" />
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
