<template>
  <div class="hello">

    <h2> Please make your choice!</h2>

    <h3>{{questions[0].wyrQ}}</h3>

    <input type="radio" v-model="choice1" v-bind:value="questions[0].wyrA1" v-on:change="choiceMade"><label>{{questions[0].wyrA1}}</label>
    <input type="radio" v-model="choice1" v-bind:value="questions[0].wyrA2" v-on:change="choiceMade"><label>{{questions[0].wyrA2}}</label>

    <h3>{{questions[1].wyrQ}}</h3>

    <input type="radio" v-model="choice2" v-bind:value="questions[1].wyrA1" v-on:change="choiceMade1"><label>{{questions[1].wyrA1}}</label>
    <input type="radio" v-model="choice2" v-bind:value="questions[1].wyrA2" v-on:change="choiceMade1"><label>{{questions[1].wyrA2}}</label>

    <h3>{{questions[2].wyrQ}}</h3>

    <input type="radio" v-model="choice3" v-bind:value="questions[2].wyrA1" v-on:change="choiceMade2"><label>{{questions[2].wyrA1}}</label>
    <input type="radio" v-model="choice3" v-bind:value="questions[2].wyrA2" v-on:change="choiceMade2"><label>{{questions[2].wyrA2}}</label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    questions: Array,

  },
  data(){
    return{
      choice1:'',
      choice2:'',
      choice3:'',
    }
  },
  methods:{
    choiceMade(){
      this.$emit('answer-changed', this.choice1)
    },
    choiceMade1(){
      this.$emit('answer-changed1', this.choice2)
    },
    choiceMade2(){
      this.$emit('answer-changed2', this.choice3)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
