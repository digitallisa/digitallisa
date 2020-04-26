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
            'Hello there, so you wanna get your business digital during the corona crisis. I am here to help.',
          answers: []
        },
        {
          question:
            'To get started. Do you have any digital appearences (e.g. Website, Facebook Page) online?',
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
          question: 'Do you want to know more about digital services?',
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
          question: 'Do know Google Maps and you want to know more about that?',
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
          question:
            'Google Maps is a map service by Google where people can find your place on a map.',
          answers: []
        },
        {
          question: 'Do you want to have you place listed there?',
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
