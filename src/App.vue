<template>
  <div id="app">
    <NavBar />
    <b-button variant="primary">Primary</b-button>
    <div class="home-wrapper content-width">
      <div class="home-panel"><Dashboard /></div>
      <div class="home-panel quick-links"><QuickLinks /></div>
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
.home-wrapper {
  width: 100%;
  display: flex;
}
.home-panel {
  width: 100%;
  margin: 1em;
}
.home-panel.quick-links {
  max-width: 15em;
}

.home-panel h5 {
border-bottom: .1em solid;
}

@media screen and (max-width: 500px) { 
  .home-wrapper {
    width: 100%;
    display: block;
  }
  .home-panel {
    width: auto;
    margin: 1em;
  }
  .home-panel.quick-links {
    max-width: none;
  }

}
</style>
