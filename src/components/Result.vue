<template>
  <p>Result is {{score}} ms</p>
  <div v-if="score<250">
      <p>You are too fast</p>
  </div>
  <div v-else-if="score>250 && score<500">
      <p>You are normal.</p>
  </div>
  <div v-else>
      <p class="slow">Your are fu*king Too Slow ! try again</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>
.slow {
    color:red;  
}
</style>