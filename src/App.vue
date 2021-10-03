<template>
  <div id="app">
   <breeds></breeds>
  </div>
</template>

<script>
import Breeds from './components/Breeds.vue'

export default {
  name: 'App',
  components: {
    Breeds
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
