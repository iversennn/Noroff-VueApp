<template>
        <div id="app">
            <div v-for="recipe in recipes" :key="recipe.title + recipe.ingredients">
                <recipeComponent        v-bind:title="recipe.title"
                                        v-bind:website="recipe.href"
                                        v-bind:ingredients="recipe.ingredients"
                                        v-bind:recipeImg="recipe.thumbnail"                    
                ></recipeComponent>
            </div>
        </div>
</template>

<script>
import RecipeComponent from './components/RecipeComponent.vue'

export default {
  name: 'App',
  components: {
    RecipeComponent
  },
  data(){
        return{
            recipes:[]
        }
    },
    beforeMount: function(){
        const app = this;
        const conversionUrl = 'https://cors-anywhere.herokuapp.com/';
        const url = 'http://www.recipepuppy.com/api/';

            fetch(conversionUrl + url)
            .then(function(response){
                return response.json();
            })
            .then(function(result){
                app.recipes = result.results;
            })
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
