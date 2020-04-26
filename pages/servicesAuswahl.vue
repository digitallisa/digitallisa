<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Pricing</h1>
        <v-card>
          <v-list shaped>
            <v-list-item-group v-model="model" multiple>
              <template v-for="(item, i) in items">
                <v-divider v-if="!item" :key="`divider-${i}`"></v-divider>

                <v-list-item
                  v-else
                  :key="`item-${i}`"
                  :value="item"
                  active-class="deep-purple--text text--accent-4"
                >
                  <template v-slot:default="{ active, toggle }">
                    <v-list-item-content>
                      <v-list-item-title v-text="item"></v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-action>
                      <v-checkbox
                        :input-value="active"
                        :true-value="item"
                        color="deep-purple accent-4"
                        @click="toggle"
                      ></v-checkbox>
                    </v-list-item-action>
                  </template>
                </v-list-item>
              </template>
            </v-list-item-group>
          </v-list>
        </v-card>
        <v-card>
          <v-list-item three-line>
            <v-list-item-content>
              <v-list-item-title class="headline mb-1">Price</v-list-item-title>
            </v-list-item-content>
          </v-list-item>

          <v-card-actions>
            <v-btn text>Buy</v-btn>
            <v-btn text>Button</v-btn>
          </v-card-actions>
        </v-card>
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
      'Maintenance Service',
      'Online Ads Service'
    ],
    model: ['Carrots']
  })
}
</script>

<style></style>
