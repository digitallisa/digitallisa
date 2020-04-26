<template>
  <v-container ref="chat" class="custom-color">
    <v-row v-for="(request, requestIndex) in chatRequests" :key="requestIndex">
      <v-col>
        <v-row dense>
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
            <v-row justify="end" no-gutters>
              <v-col cols="auto">
                <v-btn
                  large
                  rounded
                  :class="{
                    'disabled-color-button': answer.chosen && request.answered
                  }"
                  :disabled="!answer.chosen && request.answered"
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
      chatRequests: [],
      followingRequests: [
        {
          question:
            "Hey there, I'm Lisa and ready to help you building digital customer touchpoints. They increase the user experience for your customers and thus will likely result in more customers.",
          answers: []
        },
        {
          question:
            "Are you ready? I would guide you through some questions now. Don't worry, it does not take long.",
          answers: [
            {
              text: 'Yes',
              chosen: true
            },
            {
              text: 'No',
              chosen: false
            }
          ],
          answered: false
        },
        {
          question: 'Do you have a Google My Business entry?',
          answers: [
            {
              text: 'Yes',
              chosen: false
            },
            {
              text: 'No',
              chosen: true
            }
          ],
          answered: false
        },
        {
          question:
            'Alright, that is no problem! Lets create one together :) A Google My Business Entry helps you to be listed in the Google search engine if someone searches for your business. It would also show your current opening times, address, telephone number etc. That helps you to communicate your current business terms like opening times to your customers. Especially due to the Corona crisis people are unsure whether local business are open or not. ',
          answers: [
            {
              text: 'Yes',
              chosen: true
            },
            {
              text: 'No',
              chosen: false
            }
          ],
          answered: false
        }
      ]
    }
  },
  mounted() {
    this.nextQuestion()
  },
  methods: {
    nextQuestion() {
      this.markCurrentQuestionAsDone()
      if (
        this.followingRequests !== null &&
        this.followingRequests.length !== 0
      ) {
        const currentRequest = this.followingRequests.shift()
        this.chatRequests.push(currentRequest)
        this.$nextTick(() => {
          const chatBody = this.$refs.chat
          chatBody.scrollTop = chatBody.scrollHeight
        })
        if (currentRequest.answers.length === 0) {
          setTimeout(() => {
            this.nextQuestion()
          }, 1000)
        }
      }
    },
    markCurrentQuestionAsDone() {
      if (
        this.chatRequests.length !== 0 &&
        this.chatRequests[this.chatRequests.length - 1].answers !== null &&
        this.chatRequests[this.chatRequests.length - 1].answers.length !== 0
      )
        this.chatRequests[this.chatRequests.length - 1].answered = true
    }
  }
}
</script>

<style>
.custom-color {
  background-color: #eeeeee;
  height: 75vh;
  overflow-y: scroll;
}
.disabled-color-button {
  background-color: #82b1ff !important;
  pointer-events: none;
}
</style>
