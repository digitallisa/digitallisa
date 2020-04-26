<template>
  <v-card width="100%">
    <v-container>
      <v-row>
        <v-col cols="auto">
          <v-list-item-avatar
            class="ml-4"
            tile
            size="80"
            color="grey"
          ></v-list-item-avatar>
        </v-col>
        <v-col cols="5">
          <v-row>
            <v-card-title>{{ service.title }}</v-card-title>
          </v-row>
          <v-row>
            <v-card-subtitle>
              {{ service.description }}
            </v-card-subtitle>
          </v-row>
        </v-col>
        <v-col cols="3">
          <v-row>
            <v-col>
              <v-btn text>
                Start Tutorial Now
                <v-icon right>mdi-arrow-right</v-icon>
              </v-btn>
            </v-col>
            <v-col>
              <v-btn dark color="black" @click="$emit('serviceChosen')">
                Add Premium Service
                <v-icon right>mdi-plus</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  props: {
    service: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style></style>
