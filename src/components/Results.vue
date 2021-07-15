<template>
  <div class="results">
      <h2>Your score is: {{score}} ms</h2>
      <p class="rank">{{rank}}</p>
  </div>
</template>

<script>
export default {
    props: ['score',],
    data(){
     return{
         rank: null
     } 
    },
    mounted(){
        if(this.score < 250){
            this.rank = 'Super fast reflexes!'
        } else if(this.score < 500){
            this.rank = 'Fast, but could be faster'
        } else {
            this.rank = 'Too Slow, go again'
        }
    }
}
</script>

<style>
    .rank {
        font-size: 1.4em;
        color: #0faf87;
        font-weight: bold;
    }
</style>