<template>
  <v-container fluid class="pa-0 ma-0">
    <v-row class="light-blue" align="center" style="height:400px" no-gutters>
      <v-col cols="6">
        <v-container class="ml-6">
          <v-row justify="center" dense>
            <v-col cols="12">
              <h4 class="white--text display-3 font-weight-black">
                Bring your business online with Lisa.
              </h4>
            </v-col>
            <v-col cols="12">
              <v-row>
                <v-col cols="auto">
                  <v-btn to="/chatbot" nuxt x-large rounded>
                    Chat With Lisa
                  </v-btn>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
    </v-row>
    <v-row justify="center" align="center">
      <v-col class="title" cols="auto">You have the control.</v-col>
    </v-row>
    <v-row justify="center" align="center">
      <v-col cols="auto">
        Choose if you want to go through our easy tutorials by yourselves or you
        use our automated service that get you started in minutes!
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {}
</script>

<style></style>
