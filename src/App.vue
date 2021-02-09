<template>
  <div id="app">
    <NavBar />
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<style>
:root {
  --base: #1164D9;
  --tint: #2E85FF;
  --shade: #14315A;
  --accent: #D99511;
  --accent-dark: #8C5C00;
  --content-max-width: 80rem;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
  margin-top: 60px;
}


</style>
