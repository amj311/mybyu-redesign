<template>
  <div id="app">
    <NavBar />
    <b-button variant="primary">Primary</b-button>
    <div class="home-wrapper">
      <div class="home-panel"><Dashboard /></div>
      <div class="home-panel"><QuickLinks /></div>
    </div>
  </div>
</template>

<script>
import NavBar from './components/Nav/NavBar.vue'
import Dashboard from './components/Dashboard/Dashboard.vue'
import QuickLinks from './components/QuickLinks/QuickLinks.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Dashboard,
    QuickLinks,
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
}

.content-width {
  max-width:var(--content-max-width);
  margin: 0 auto;
}

h3 {
  border-bottom: .1em solid;
}

.home-panel {
  margin: 1em;
}
</style>
