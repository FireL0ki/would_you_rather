<template>
  <div class="wyr">
    
    <h2>Please make your choice!</h2>
    <h3>{{ question }}</h3>

    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade">
    <label>{{ answer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade">
    <label>{{ answer2 }}</label>

  </div>


</template>


<script>
export default {
  name: 'WouldYouRather',
  // these are the properties that can be passed to the child component
  props: {
    question: String,
    answer1: String,
    answer2: String,
    id: Number,
  },
  data() {
    return {
      choice: ''
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice, this.id) // pass choice & id for tracking over to app.vue
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

.wyr {
  border: 1px black solid;
  background: rgb(240, 196, 114); 
}

</style>
