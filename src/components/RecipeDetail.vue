
<template lang="html">
  <div v-if="recipe">
    <h1>{{recipe.title}}</h1>

  </div>
</template>

<script>
export default {
  name: 'recipe-detail',
  props: ['recipe']
}
</script>

<style lang="css" scoped>
  img {
    width: 50%
  }
</style>
