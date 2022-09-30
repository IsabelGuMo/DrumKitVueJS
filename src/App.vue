<template>
<div>
  <h1 class="text-center text-6xl text-slate-300 bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500">VueJS DrumKit</h1>
  <div class="w-auto mt-36 justify-center flex">
  <div class=" grid grid-cols-4">
   
      <Key v-for="(key, i) in keys" :sound="key" :key="i" />
   
  </div>
  </div>
</div>
</template>

<script>
import Key from './components/Key.vue'


  export default {
    name: 'App',
    data () {
      return {
        keys: [
          {
            name: "bombo",
            audio: './assets/bombo.wav',
            letter: "A"
          },
          {
            name: "crash",
            audio: "./assets/crash.wav",
            letter: "S"
          },
          {
            name: "hit-hat",
            audio: "./assets/hit-hat.wav",
            letter: "D"
          },
          {
            name: "redoblante",
            audio: "./assets/redoblante.wav",
            letter: "F"
          },
          
          {
            name: "tom1",
            audio: "./assets/tom1.wav",
            letter: "G"
          },
          {
            name: "tom2",
            audio: "./assets/tom2.wav",
            letter: "H"
          },
          {
            name: "tom3",
            audio: "./assets/tom3.wav",
            letter: "J"
          },
          {
            name: "tom4",
            audio: "./assets/tom4.wav",
            letter: "K"
          },
    
        ]

      }
    
    },

    components: {
      Key
    } 
  } 
</script>

<style>
#app {
  font-family: 'Space Mono', monospace;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
