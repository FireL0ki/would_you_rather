<template>
  <div class="hello">
    
    <h2>Please make your choice!</h2>

    <h3>{{ question }}</h3>

    <input type="radio" v-model="choice" v-bind:value="answer1">
    <label>{{ answer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="answer2">
    <label>{{ answer2 }}</label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: String,
    answer1: String,
    answer2: String,
  },
  data() {
    return {
      choice: ''
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
