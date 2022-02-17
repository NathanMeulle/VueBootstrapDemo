<template>
  <b-container>
    <h3>Classement</h3>
    <Tableau />
  </b-container>
</template>

<script>
import Tableau from './Tableau.vue'
export default {
  name: 'Classement',
  components: {
    Tableau
  }
}
</script>