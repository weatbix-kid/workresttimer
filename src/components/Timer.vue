<template>
  <div class="timer-container">
    <div 
      class="settings" 
      :class="settingsOpen ? 'open' : ''"
      @click.self="settingsOpen = !settingsOpen"
    >
      Settings
      <div class="settings-modal">
        <input type="number" name="endCountOne" v-model="endCountOne">
        <input type="number" name="endCountTwo" v-model="endCountTwo">
      </div>
    </div>
    <div 
      class="timer" 
      :class="pause ? 'pause' : mode"
      @click="pause = !pause"
    >
      <span>{{ count }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Timer',
  data () {
    return {
      count: 0,
      mode: 'work',
      pause: true,
      endCountOne: 3,
      endCountTwo: 2,
      settingsOpen: false,
      timer: setInterval(() => {
        if (!this.pause) {
          this.count++
          if (this.mode === 'work' && this.count > this.endCountOne) {
            this.count = 0
            this.mode = 'rest'
          } else if (this.mode === 'rest' && this.count > this.endCountTwo) {
            this.count = 0
            this.mode = 'work'
          }
        }
      }, 1000)
    }
  }
}
</script>
