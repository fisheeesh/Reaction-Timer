<template>
  <div class="block" v-if="showBlock">
    Click Here {{ delay }}
  </div>
</template>

<script>
export default {
  data(){
    return {
       showBlock : false
    }
  },
  props : [
    'delay',
  ],
  mounted(){
    setTimeout(()=>{
      this.showBlock = true
    }, this.delay)
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