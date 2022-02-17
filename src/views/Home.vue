<template>
  <div class="home">
    <h1>Home page</h1>
    <Classement />
  </div>
</template>

<script>
import Classement from '../components/Classement.vue'
export default {
  name: 'Home',
  components: {
    Classement,
  },
}
</script>
