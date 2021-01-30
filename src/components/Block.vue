<template>
  <div class=" block" v-if="showBlock" @click="stoptimer">click here</div>
</template>

<script>
export default {
  props:['delay'],
  data(){
    return{
      showBlock:false,
      score:0,
      timer:null
    }
  },
  mounted(){
    setTimeout(() => {
      this.showBlock=true;
      this.startTimer()
    }, this.delay);
  },
  methods:{
    startTimer(){
      this.timer=setInterval(() => {
        this.score+=50;
      }, 50);
    },
    stoptimer(){
      clearInterval(this.timer);
      this.$emit("endGame",this.score)
    }
  },
  updated(){
    console.log("updated")
  }
  
}
</script>

<style>
    .block{
        background-color: aqua;
        padding:140px 30px;
        width: 300px;
        margin: 20px auto;
        border-radius: 50%;
    }
</style>