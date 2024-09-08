<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click Here {{ delay }}
  </div>
</template>

<script>
export default {
  data(){
    return {
       showBlock : false,
       score : 0,
       timer : null
    }
  },
  props : [
    'delay',
  ],
  mounted(){
    setTimeout(()=>{
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods : {
    startTimer(){
      this.timer = setInterval(() =>{
        this.score += 50
        console.log(this.score)
      }, 50)
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('endGame', this.score)
    }
  }
}
</script>

<style>
.block{
  width: 400px;
  height: 300px;
  padding-top: 20px;
  background-color: cyan;
  border-radius: 20px;
  margin: 30px auto;
}
</style>