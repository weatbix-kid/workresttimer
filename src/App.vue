<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <Timer />
</template>

<script>
import Timer from './components/Timer.vue'

export default {
  name: 'App',
  components: {
    Timer
  }
}
</script>

<style>
html {
  height: 100%; 
  width: 100%
}

body {
  margin: 0;
  height: 100%;
  width: 100%;
}

#app {
  height: 100%;
  width: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app .timer-container {
  height: 100%;
  width: 100%;
}

#app .timer-container .settings {
  color: white;
  font-weight: 700;
  position: absolute;
}

#app .timer-container .settings .settings-modal {
  display: none;
}

#app .timer-container .settings.open .settings-modal {
  display: block;
}

#app .timer-container .timer {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  background-color: #8c00ff;
  user-select: none;
}

#app .timer-container .timer.work {
  background-color: #21b61c;
}

#app .timer-container .timer.rest {
  background-color: #0059ff;
}

#app .timer-container .timer.pause {
  background-color: #8c00ff;
}

#app .timer span {
  font-size: 50vw;
  color: white;
  /* color: #2c3e50; */
}
</style>
