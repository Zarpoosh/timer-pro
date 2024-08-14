<template>
  <h1>minicode Reaction Timer :))</h1>
  <p v-if="comparing"></p>
  <button @click="start" :disabled="isplay">Start</button>
  <!-- <p v-if="showResult">Reaction :  {{ scor }} ms</p> -->
   <Result v-if="showResult" :scor="scor"/>
  <Block v-if="isplay" :delay="delay" @end="endGame" />
</template>

<script>
import Result from "./components/Result.vue"
import Block from "./components/Block.vue";
export default {
  name: "App",
  components: { Block , Result },
  data() {
    return {
      delay: null,
      isplay: false,
      showResult:false,
      scor:null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isplay = true;
      this.showResult=false;
      console.log(this.delay);
    },
    endGame(reactiontime){
      this.scor=reactiontime
      this.isplay=false
      this.showResult=true;
    }
  },
};
</script>

<style scoped>
button{
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor:not-allowed;
}
</style>
