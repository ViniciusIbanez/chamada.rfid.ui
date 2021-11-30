<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <main-area></main-area>
  </div>
</template>

<script>
import mainArea from './main-area.vue'

export default {
  name: 'App',
  components: {
    mainArea
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
</style>
