<template>
  <b-container>
    <b-row>
      <b-col>
        <Title :title="BodyTitle"/>
      </b-col>
      </b-row>
  </b-container>
</template>

<script>
import Title from './Title.vue'
export default {
  name: 'Navbar',
  components: {
    Title
  },
  props: ['BodyTitle']
}
</script>
