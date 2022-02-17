<template>
  <div id="app">
   <Navbar :logoUrl="'https://drive.google.com/uc?export=view&id=1IXY8IZai07UAj0yamXUTTy-RA8baWN2I'" 
   :NavbarTitle="'Sport'" 
   :MenuItems="['Home', 'About']"
   :NavBarColor="'#a23'"
   @swapComponent="loadComponent"
   />
    <div class="container">
      <div :is="currentComponent"></div>
    </div>
  </div>
</template>
<script>
import Navbar from './components/Navbar.vue'
import Home from './views/Home.vue'
import About from './views/About.vue'
export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    About
  },
    data() {
      return {
        currentComponent: null,
      }
    },
    methods: {
    loadComponent: function(component)
    {
       this.currentComponent = component
    }
  }
}
</script>
<style>
#app {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav a {
  font-weight: bold;
  color: #000;
}

#nav a.router-link-exact-active {
  color: #fff;
}
</style>
