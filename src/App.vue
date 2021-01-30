<template>
  <h1>How Fast Can u Catch me ?</h1>
  <button @click="start" :disabled="isplaying">play</button>
  <div v-if="isplaying">
    <Block :delay="delay" @endGame="endGame"/>
  </div>
  <div v-if="end">
    <Result :score="score" />
  </div>
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: 'App',
  components: {
    Block,Result
  },
  data(){
    return {
      isplaying:false,
      delay:null,
      score:0,
      end:false
    }
    
  },
  methods:{
    start(){
      this.isplaying=true,
      this.delay=2000+Math.random()*5000;
    },
    endGame(score){
      this.score=score;
      this.isplaying=false;
      this.end=true;
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
