<template>
  <v-container>
    <v-row no-gutters>
      <v-col>
        <chat-header />
      </v-col>
    </v-row>
    <v-row no-gutters>
      <v-col>
        <chat-body />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ChatHeader from '~/components/chatBot/chatHeader.vue'
import ChatBody from '~/components/chatBot/chatBody.vue'

export default {
  components: {
    ChatHeader,
    ChatBody
  }
}
</script>

<style></style>
