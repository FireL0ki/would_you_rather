<template>  <!-- template tag needs to have exactly one child element -->
  <div id="app">

    <h1>Would you rather?</h1>

    <!-- you can use the uppercase style, but the dashes between is the convention for writing vue tagnames
    There is no valid HTML tag with dashes-->

    <!-- TODO v-for to loop over the list of questions & answers -->
    <div v-for="(question) in questionsArray" :key="question.id">
      <!-- v-bind:question="wyrQuestion"
      v-bind:answer1="wyrAnswer1"
      v-bind:answer2="wyrAnswer2"> -->
      {{ question.wyrQuestion }}
      {{ question.wyrAnswer1 }}
      {{ question.wyrAnswer2 }}
    </div>

    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-changed="answerChanged">
    </would-you-rather>  
    <!-- 'app' is the main page, WouldYouRather is inside it,
    we need to specifiy that app should show this component-->

    <!-- tied to v-for? -->
    <p>{{ userSelectionMessage }}</p>

  </div>
  
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  // Create a questions array to hold all the questions/possible answers
  data() {
    return {
      questionsArray: [
        {
          id: 0,
          wyrQuestion: 'Would you rather be a wizard or a superhero?',
          wyrAnswer1: 'Wizard',
          wyrAnswer2: 'Superhero',
          // userSelectionMessage: ''
        },
        {
          id: 1,
          wyrQuestion: 'Would you rather have a full suit of armour or a horse?',
          wyrAnswer1: 'A full suit of armour',
          wyrAnswer2: 'A horse',
        },
        {
          id: 2,
          wyrQuestion: 'Would you rather have eyes that change color depending on your mood or hair that changes color depending on the temperature?',
          wyrAnswer1: 'Eyes that change color depending on mood',
          wyrAnswer2: 'Hair that changes color depending on temperature',
        }
      ]
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `Thanks! You chose ${choice}`
    }
  }
}
</script>

<style>

body {
  background: rgb(137, 116, 231);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: rgb(116, 231, 226);
}
</style>