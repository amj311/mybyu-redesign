<template>
  <div id="navBar">
  <b-navbar toggleable="md" type="dark" class="content-width">
    <b-navbar-brand href="#"><Logo /></b-navbar-brand>

    <!-- <b-navbar-toggle target="nav-collapse"></b-navbar-toggle> -->

    <!-- <b-collapse id="nav-collapse" is-nav> -->
      <b-navbar-nav class="ml-auto">      
        <b-nav-item-dropdown right id="profile-button">
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <ProfPic :size="'30px'" />
            <span class="welcome-msg">Welcome, Cougar!</span>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    <!-- </b-collapse> -->
  </b-navbar>
</div>
</template>


<script>
import ProfPic from './ProfPic.vue'
import Logo from './Logo.vue'

export default {
  name: 'NavBar',
  props: {
    msg: String
  },
  components: {
    Logo,
    ProfPic,
  }
}
</script>

<style>
#navBar {
  color: #fff;
  background:var(--shade)
}

#profile-button .dropdown-toggle {
  display: inline-flex;
  align-items: center;
  justify-content: space-between;
}
#profile-button .welcome-msg {
  margin-left: .5em;
}
#profile-button ul {
  position: absolute;
}
</style>