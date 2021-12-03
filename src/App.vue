<template>  <!-- template tag needs to have exactly one child element -->
  <div id="app">

    <h1>Would you rather?</h1>

    <!-- you can use the uppercase style, but the dashes between is the convention for writing vue tagnames
    There is no valid HTML tag with dashes-->

    <!-- TODO v-for to loop over the list of questions & answers -->
    <would-you-rather v-for="(question) in questionsArray" :key="question.id"
      v-bind:question="question.wyrQuestion"
      v-bind:answer1="question.wyrAnswer1"
      v-bind:answer2="question.wyrAnswer2"
      v-on:answer-changed="answerChanged">
    </would-you-rather>



    <!-- 'app' is the main page, WouldYouRather is inside it,
    we need to specifiy that app should show this component-->

    <!-- create unordered list of selections -->
    <p id="ywr"> You Would Rather...</p>

    <!-- loop over userSelectionsArray, put each response in an unordered list. -->
    <ul id="userSelectionsArray">
      <li v-for="(selection) in userSelectionsArray">
        {{ selection }} 
      </li>
    </ul>

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
        },
        {
          id: 1,
          wyrQuestion:'Would you rather have a full suit of armour or a horse?',
          wyrAnswer1: 'Have a full suit of armour',
          wyrAnswer2: 'Have a horse',
        },
        {
          id: 2,
          wyrQuestion: 'Would you rather have eyes that change color depending on your mood or hair that changes color depending on the temperature?',
          wyrAnswer1: 'Eyes that change color depending on mood',
          wyrAnswer2: 'Hair that changes color depending on temperature',
        }
      ],
      userSelectionsArray: [
      ]
    }
  },
  methods: {
    answerChanged(choice) {
        if (this.userSelectionsArray.includes(choice)) {
          return
        } else {
          this.userSelectionsArray.push(choice)
        }
    }
  }
}
</script>

<style>

body {
  color: orange;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-weight: 500;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-image: linear-gradient(to right, rgb(190, 19, 19), rgb(228, 228, 225));
}

#ywr {
  font-size: 20px;
  font-weight: 600;
}

</style>