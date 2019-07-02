<template>
  <div id="app">
    <Background/>
    <ClockWidget id="clock"/>
    
    <div id="launcher-container" @click="openLauncher = false" v-show="openLauncher">
      <div id="app-launcher" ref="appLauncher" @click.stop="stopPropagation">
        <div id="launcher-nav">
          <i class="material-icons small-material-icons selectable" @click="openLauncher = false">close</i>
        </div>
        <div id="app-view">
          <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='"purple"' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="cloud" :width='buttonWidth' :height='buttonHeight' :tint='"green"' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="wb_sunny" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="highlight" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
          <ImageButtonWidget icon="settings" :width='buttonWidth' :height='buttonHeight' :tint='defaultButtonColor' />
        </div>
      </div>
    </div>

    <div id="nav-bar">
      <ImageButtonWidget icon="wb_sunny" :width='favButtonWidth' :height='favButtonHeight' :tint='"purple"' />
      <ImageButtonWidget icon="cloud" :width='buttonWidth' :height='buttonHeight' :tint='"green"' />
      <ImageButtonWidget icon="highlight" :width='favButtonWidth' :height='favButtonHeight' :tint='"#ff9800"' />
      <ImageButtonWidget icon="security" :width='favButtonWidth' :height='favButtonHeight' :tint='"#f44336"' />
      <ImageButtonWidget icon="nature" :width='favButtonWidth' :height='favButtonHeight' :tint='"#ffeb3b"' />
      <ImageButtonWidget @click.native="openLauncher = true" icon="dashboard" :width='favButtonWidth' :height='favButtonHeight' :tint='defaultButtonColor' />
      <ImageButtonWidget icon="settings" :width='favButtonWidth' :height='favButtonHeight' :tint='"#2196f3"' />
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
      defaultButtonColor: 'rgba(128,128,128,0.5)',
      favButtonWidth: '10vw',
      favButtonHeight: '10vw',
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
  line-height: 10vw;
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
  vertical-align: bottom;
  user-select: none;
}

.small-material-icons {
  color: grey;
  line-height: 1;
  font-size: 2.4vw;
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

.selectable {
  cursor: pointer;
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
  position: absolute;
  width: fit-content;
  height: 80vh;
  box-shadow: 5px 5px 5px rgba(128,128,128,0.5);
  z-index: 20;
  margin: auto;
  background-color: rgba(255, 255, 255, 0.9);
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
}

#launcher-nav {
  width: 100%;
  height: 6vh;
  box-shadow: 2px 2px 5px rgba(128, 128, 128, 0.5);
}

#app-view {
  display: grid;
  height: 74vh;
  
  overflow-y: auto;
  grid-template-columns: repeat(5, 14vw);
  grid-template-rows: repeat(auto-fill, 14vw);
}

#nav-bar {
  width: 100%;
  display: inline-flex;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>

