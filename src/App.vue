<template>

  <h1>Would you rather...</h1>

  <would-you-rather
  v-bind:questions="questions"
  v-on:answer-changed="answerChanged"
  v-on:answer-changed1="answerChanged1"
  v-on:answer-changed2="answerChanged2">
  </would-you-rather>

  <p v-for="message in answers">{{message}}</p>

</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return{
      answers:[],
      questions:[
        {
          id:0,
          wyrQ: 'Would you rather be a detective or a pilot?',
          wyrA1: 'Detective',
          wyrA2: 'Pilot',
        },
        {
          id:1,
          wyrQ: 'Would you rather be a wizard or a superhero?',
          wyrA1: 'Wizard',
          wyrA2: 'Superhero',
        },
        {
          id:2,
          wyrQ: 'Would you rather play hide and seek or dodgeball?',
          wyrA1: 'Hide and seek',
          wyrA2: 'Dodgeball',
          }
      ],

    }
  },
  methods:{
    answerChanged(choice){

      this.answers.push(choice)

    },
    answerChanged1(choice){
      this.answers.push(choice)

    },
    answerChanged2(choice){
      this.answers.push(choice)

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
