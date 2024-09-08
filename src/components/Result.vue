<template>
  <p>Resut is {{ result }} ms</p>
  <div v-if="result === 0">
    <p>Nigaa WTF! Amazing Nigga 😱</p>
  </div>
  <div v-else-if="result > 0 && result <= 250">
    <p>Nigga! You are fast! 😎</p>
  </div>
  <div v-else-if="result > 250 && result < 500">
    <p>Nigga! You are normal! 😐</p>
  </div>
  <div v-else>
    <p>Nigga! You are slow! 😂</p>
  </div>
</template>

<script>
export default {
    props: [
        'result'
    ]
}
</script>

<style>

</style>