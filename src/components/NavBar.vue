<template>
  <div id="navBar">
    <div id="nav-wrapper" class="content-width">
      <Logo />
    </div>
  </div>
</template>

<script>
import Logo from './Logo.vue'

export default {
  name: 'NavBar',
  props: {
    msg: String
  },
  components: {
    Logo,
  }
}
</script>

<style>
#navBar {
  color: #fff;
  background:var(--shade)
}
</style>