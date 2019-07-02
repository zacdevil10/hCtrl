<template>
  <div id="app">
    <Background/>
    <ClockWidget id="clock"/>

    <div id="nav-bar">
      <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
    </div>
  </div>
</template>

<script>
import ClockWidget from './components/Clock.vue'
import Background from './components/Background.vue'
import ImageButtonWidget from './components/ImageButton.vue'

export default {
  name: 'app',
  components: {
    Background,
    ClockWidget,
    ImageButtonWidget
  },
  data() {
    return {
      buttonColor: 'rgba(128,128,128,0.5)',
      buttonWidth: '150',
      buttonHeight: '150'
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Material Icons';
  font-style: normal;
  font-weight: 400;
  src: url(https://fonts.gstatic.com/s/materialicons/v47/flUhRq6tzZclQEJ-Vdg-IuiaDsNcIhQ8tQ.woff2) format('woff2');
}

.material-icons {
  font-family: 'Material Icons';
  font-weight: normal;
  font-style: normal;
  font-size: 120px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  -webkit-font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
  color: white;
}

i.material-icons {
  line-height: 150px;
  vertical-align: bottom;
}

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

#nav-bar {
  width: 100%;
  display: inline-flex;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>

