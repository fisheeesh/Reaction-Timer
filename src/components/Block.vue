<template>
  <div class="block">
    Click Here {{ delay }}
  </div>
</template>

<script>
export default {
  props : [
    'delay'
  ],
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