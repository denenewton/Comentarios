<template>
  <div id="app">
    <Comentarios />
  </div>
</template>

<script>
import Comentarios from './components/Comentarios.vue'

export default {
  name: 'App',
  components: {
    Comentarios
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  margin-right: 30%;
  margin-left: 30%;
}
</style>
