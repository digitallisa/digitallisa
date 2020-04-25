<template>
  <v-container class="custom-color">
    <v-row v-for="(request, requestIndex) in chatRequests" :key="requestIndex">
      <v-col>
        <v-row>
          <v-col>
            <chat-request :question="request.question" />
          </v-col>
        </v-row>
        <v-row justify="end">
          <v-col
            v-for="(answer, answerIndex) in request.answers"
            :key="answerIndex"
            cols="12"
          >
            <v-row justify="end">
              <v-col cols="auto">
                <v-btn
                  rounded
                  :disabled="!answer.clickable"
                  @click="nextQuestion"
                >
                  {{ answer.text }}
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
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
              clickable: false
            },
            {
              text: 'No',
              clickable: true
            }
          ]
        }
      ]
    }
  },
  methods: {
    nextQuestion() {
      this.chatRequests.push({
        question: 'Do you want to know more about digital services?',
        answers: [
          {
            text: 'Yes',
            clickable: true
          },
          {
            text: 'No',
            clickable: true
          }
        ]
      })
    }
  }
}
</script>

<style>
.custom-color {
  background-color: #eeeeee;
}
</style>
