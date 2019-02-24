<template lang="html">
  <div>
    <h1>Recipes</h1>
    <div class="main-container">
      <recipe-list :recipes="recipes"></recipe-list>
      <recipe-detail :recipe="selectedRecipe"></recipe-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import RecipeDetail from './components/RecipeDetail.vue'
import RecipesList from './components/RecipesList.vue'

export default {
  data(){
    return {
      recipes: [],
      selectedRecipe: null    }
  },
  components: {
    recipeList: RecipesList,
    recipeDetail: RecipeDetail
  },
  mounted(){

    fetch('http://www.recipepuppy.com/api/')
    .then(res => res.json())
    .then(recipes => this.recipes = recipes)

    eventBus.$on('recipe-selected', (recipe) => {
      this.selectedRecipe = recipe
    })

  }
}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
