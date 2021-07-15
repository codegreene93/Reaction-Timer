<template>
 <h1>Amy's reaction Timer</h1>
 <button @click="begin" :disabled="isPlaying">Start Game</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame" /> 
 <Results v-if="showResults" :score="score" @end="endGame" />
 
</template>

<script>
  import Block from './components/Block.vue' 
  import Results from './components/Results.vue' 

export default {
  name: 'App',
  components: {Block, Results },
  data (){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    begin(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame(reactionTime){
      this.score = reactionTime,
      this.isPlaying = false
      this.showResults = true
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
  color: #444;
  margin-top: 60px;
}
</style>
