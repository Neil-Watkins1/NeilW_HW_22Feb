
<template lang="html">
  <div class="">
    <ul>
      <list-component  v-for="(title, index) in recipes" :title="title" :key="index"></list-component>
    </ul>
  </div>

</template>

<script>
import ListComponent from './ListComponent.vue'
export default {
  name: 'recipes-list',
  props: ['recipes'],
  components: {
    "list-component": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
