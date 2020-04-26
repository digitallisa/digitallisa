<template>
  <v-container class="custom-color">
    <v-row v-for="(request, requestIndex) in chatRequests" :key="requestIndex">
      <v-col>
        <v-row>
          <v-col>
            <chat-request :question="request.question" />
          </v-col>
        </v-row>
        <v-row>
          <v-col
            v-for="(answer, answerIndex) in request.answers"
            :key="answerIndex"
          ></v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ChatRequest from '~/components/chatBot/chatBody/chatRequest.vue'
export default {
  components: {
    ChatRequest
  },
  data() {
    return {
      chatRequests: [
        {
          question:
            'Hello there, so you wanna get your business digital during the corona crisis. I am here to help.',
          answers: []
        },
        {
          question:
            'To get started. Do you have any digial appearences (e.g. Website, Facebook Page) online?',
          answers: [
            {
              text: 'Yes',
              clickable: true
            },
            {
              text: 'No',
              clickable: false
            }
          ]
        }
      ]
    }
  }
}
</script>

<style>
.custom-color {
  background-color: #eeeeee;
}
</style>
