<template>
  <div id="app">
    <Background/>
    <ClockWidget id="clock"/>
    
    <div id="launcher-container" @click="openLauncher = false" v-show="openLauncher">
      <div id="app-launcher" ref="appLauncher" @click.stop="stopPropagation">
        <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
        <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      </div>
    </div>

    <div id="nav-bar">
      <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
      <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='buttonColor' />
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
    ImageButtonWidget,
    stopPropagation: (event) => event.stopPropagation()
  },
  data() {
    return {
      buttonColor: 'rgba(128,128,128,0.5)',
      buttonWidth: '10vw',
      buttonHeight: '10vw',
      openLauncher: false
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
  font-size: 7vw;
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
  line-height: 10vw;
  vertical-align: bottom;
  user-select: none;
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

::-webkit-scrollbar {
  width: 6px;
}

::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background: rgb(189, 189, 189);
  transition: all .15s ease-in-out;
}

::-webkit-scrollbar-thumb:hover {
  background: rgb(170, 170, 170);
  transition: all .15s ease-in-out;
}
</style>

<style scoped>
#clock {
  padding-top: 30vh;
}

#launcher-container {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
  margin: auto;
  background-color: rgba(255, 255, 255, 0.2);
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
}

#app-launcher {
  display: grid;
  position: absolute;
  width: 84.5vw;
  height: 80%;
  box-shadow: 5px 5px 5px rgba(128,128,128,0.5);
  z-index: 20;
  margin: auto;
  background-color: rgba(255, 255, 255, 0.9);
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  overflow-y: scroll;
  grid-template-columns: repeat(auto-fill, 14vw);
}

#nav-bar {
  width: 100%;
  display: inline-flex;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>

