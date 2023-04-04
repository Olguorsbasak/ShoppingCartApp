<template>
  <div>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.recipe.uri">
        <h2>{{ recipe.recipe.label }}</h2>
        <img :src="recipe.recipe.image" alt="Recipe Image" />
        <div v-html="recipe.recipe.healthLabels"></div>
        <div v-html="recipe.recipe.ingredientLines"></div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      recipes: {},
    };
  },
  async created() {
    const id = import.meta.env.VITE_ID;
    const apiKey = import.meta.env.VITE_API_KEY;
    const recipeUrl = `https://api.edamam.com/search?r=http://www.edamam.com/ontologies/edamam.owl%23recipe_${id}&app_id=1f1f1f1f&app_key=${apiKey}`;
    console.log(apiKey, id);
    const recipeData = await this.fetchRecipeData(recipeUrl);
    this.updateRecipeData(recipeData);
  },

  methods: {
    async fetchRecipeData(url) {
      const response = await fetch(url);
      const data = await response.json();
      return data;
    },
    updateRecipeData(data) {
      this.recipes = data;
    },
  },
};
</script>
