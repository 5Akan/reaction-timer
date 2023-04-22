<template>
 <h1>Reaction Timer</h1>
  <button @click="start" :disabled = "isPlaying"  >Play</button>
  <!-- Disabled means you cant click it while it isPlaying -->
  <Block1 v-if= "isPlaying" :delay="delay" @end = 'endGame'/>
  <Result1 v-if= "showResult"  :score = "score"/>
  <!-- <p v-if= "showResult">The Reaction Time : {{ score }} ms</p> -->
</template>

<script>
import Block1 from './components/Block1.vue';
import Result1 from './components/Result1.vue';
export default {
  name: 'App',
  components: { Block1, Result1 },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResult:false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() *  5000, 
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true; 
              
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
