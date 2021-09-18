<template>
  <div class="background">
    <h1>Ninja Reaction Timer</h1>
    <button @click="start_game">START</button>
    <Block v-if="is_playing" :delay="delay" @end="end_game"/>
    <p v-if="showResults">Reaction time = {{ score }} ms </p>
  </div>

</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: { Block },
  data() {
    return {
      is_playing: false,
      delay: 1000 + (Math.random() * 2000),
      score: null,
      showResults: false
    }
  },
  methods: {
    start_game() {
      this.is_playing = true
    },
    end_game(reactionTime) {
      this.score = reactionTime
      this.is_playing = false
      this.showResults = true
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
  background-color: black;
  margin-top: 60px;
}
button {
  background: red;
}
.background {
  background: black;
  height: 100%;
  width: 100%;
  margin: 0;
  top: 0;
  position: fixed;
}
</style>
