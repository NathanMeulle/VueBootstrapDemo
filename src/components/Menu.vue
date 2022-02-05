<template>
    <b-navbar-nav>
        <b-nav-item v-for="item in menuItems" :key="item.message">
            <MenuItem :title="item"/>
        </b-nav-item>
    </b-navbar-nav>
</template>

<script>
import MenuItem from './MenuItem.vue'
export default {
  name: 'Menu',
  components: {
      MenuItem
  },
  props: ['menuItems']

}
</script>
