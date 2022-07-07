<template>
  <div id="app">
    <CheckGrid />
  </div>
</template>

<script>
import CheckGrid from './components/check-grid.vue'
export default {
  name: 'App',
  components: {
    CheckGrid
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
