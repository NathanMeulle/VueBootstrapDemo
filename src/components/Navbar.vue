<template>
 <b-navbar :style="cssProps" id="nav" toggleable="lg" class="navbar navbar-dark justify-content-left">
      <Logo :imgSrc="logoUrl" class=""/>
      <b-navbar-brand href="#"><h2>{{NavbarTitle}}</h2></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav class="d-lg-block">
        <b-navbar-nav>
          <b-nav-item v-for="item in MenuItems" :key="item.message">
            <b-nav-item @click="swapComponent(item)">{{item}}</b-nav-item>
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
</template>

<script>
import Logo from './Logo.vue'

export default {
  name: 'Navbar',
  components: {
    Logo,
  },
  props: ['logoUrl', 'MenuItems', 'NavbarTitle', "NavBarColor"],
  computed: {
    cssProps() {
      return {
        '--navbar-color': this.NavBarColor,
      }
    }
  },
  methods: {
    swapComponent: function(component)
    {
       this.$emit('swapComponent', component)
    }
  }
}
</script>
<style scoped>
  .navbar{
    background-color: var(--navbar-color);
  } 
</style>

