<template>
  <div id="app">
    <h1>Vue Toolkit</h1>
    <Toolkit />
  </div>
</template>

<script>
import Toolkit from "./components/Toolkit.vue"

export default {
  name: 'app',
  components: {
    Toolkit
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  font-size: 4em;
}
</style>
