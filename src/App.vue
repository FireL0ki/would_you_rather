<template>  <!-- template tag needs to have exactly one child element -->
  <div id="app">

    <h1>Would you rather?</h1>

    <!-- you can use the uppercase style, but the dashes between is the convention for writing vue tagnames
    There is no valid HTML tag with dashes-->
    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    >
      </would-you-rather>  
    <!-- 'app' is the main page, WouldYouRather is inside it,
    we need to specifiy that app should show this component-->

  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      wyrQuestion: 'Would you rather be a wizard or a superhero?',
      wyrAnswer1: 'Wizard',
      wyrAnswer2: 'Superhero',
      userSelectionMessage: ''
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
