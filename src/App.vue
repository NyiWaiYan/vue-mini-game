<template>
    <h1>CATCH ME IF YOU CAN !</h1>
    <button @click="start" :disabled="isPlaying">PLAY</button>

    <div v-if="isPlaying">
      <Block :delay="delay" @endGame="endGame"/>
    </div>

    <div v-if="end">
      <Result :score="score"/>
    </div>

</template>

<script>
  import Block from "./components/Block.vue"
   import Result from "./components/Result.vue";
export default {
  name: 'App',
  components:{
    Block,
    Result
  },

  data(){
      return{
        isPlaying:false,
        delay:null,
        score:0,
        end:false
      }
  },

  methods:{ 
    start(){
        this.isPlaying=true;
        this.delay =2000 + Math.random()*5000;
    },

    endGame(score){
     this.score = score;
     this.isPlaying=false;
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

button{
  width:70px;
  height: 30px;
  background-color: rgb(176, 249, 171);
  border: 0.1px solid;
}
</style>
