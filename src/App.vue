<template>
  <h1>How fast can you catch me?</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
    <Block :delay = "delay" @endGame="endGame"/>
  </div>
  <div v-if="isEnd">
    <Result :result="score"/>
  </div>
</template>

<script>
import Result from './components/Result.vue';
import Block from './components/Block.vue';
export default {
  data(){
    return{
      isPlaying: false,
      delay : null,
      score : 0,
      isEnd : false,
    }
  },
  methods : {
    start(){
      this.isPlaying = true
      this.isEnd = false
      this.delay = 2000 + Math.random() * 5000
      console.log(this.isPlaying)
    },
    endGame(score){
      this.score = score
      this.isEnd = true
      this.isPlaying = false
    }
  },
  components: {
    Block,
    Result
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
