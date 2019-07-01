<template>
  <div id="app">
    <Background/>
    <ClockWidget id="clock"/>
  </div>
</template>

<script>
import ClockWidget from './components/Clock.vue'
import Background from './components/Background.vue'

export default {
  name: 'app',
  components: {
    Background,
    ClockWidget
  }
}
</script>

<style>
body {
  margin: 0;
}
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

<style scoped>
#clock {
  padding-top: 30vh;
}
</style>

