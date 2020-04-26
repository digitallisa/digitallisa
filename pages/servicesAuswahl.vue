<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Select the Services you need:</h1>
        <v-card>
          <v-list shaped>
            <v-list-item-group v-model="model" multiple>
              <template v-for="(item, i) in items">
                <v-divider v-if="!item" :key="`divider-${i}`"></v-divider>

                <v-list-item
                  v-else
                  :key="`item-${i}`"
                  :value="item"
                  active-class="blue--text text--accent-4"
                >
                  <template v-slot:default="{ active, toggle }">
                    <v-list-item-content>
                      <v-list-item-title v-text="item"></v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-action>
                      <!-- <v-switch value input-value="true" @click="toggle"></v-switch> -->
                      <v-checkbox
                        :input-value="active"
                        :true-value="item"
                        color="deep-blue accent-4"
                        @click="toggle"
                      ></v-checkbox>
                    </v-list-item-action>
                  </template>
                </v-list-item>
              </template>
            </v-list-item-group>
          </v-list>
        </v-card>
        <v-col>
          <v-card>
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="headline">Price</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-btn text>Buy</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    items: [
      'Website',
      'Google Business',
      'Google Search optimization',
      'Facebook',
      'Instagram',
      'LinkedIn',
      'Twitter',
      '',
      'Continous Maintenance Service',
      'Continous Online Ads Service'
    ],
    model: ['Carrots']
  })
}
</script>

<style></style>
