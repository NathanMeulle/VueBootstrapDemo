<template>
  <b-navbar toggleable="lg" class="navbar navbar-dark bg-primary justify-content-left">
      <Logo :imgSrc="logoUrl" class=""/>
      <b-navbar-brand href="#"><Title :title="NavbarTitle"/></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav class="d-lg-block">
        <Menu :menuItems="MenuItems"/>
      </b-collapse>
  </b-navbar>
</template>

<script>
import Logo from './Logo.vue'
import Title from './Title.vue'
import Menu from './Menu.vue'

export default {
  name: 'Navbar',
  components: {
    Logo,
    Title,
    Menu
  },
  props: ['logoUrl', 'MenuItems', 'NavbarTitle']
}
</script>
