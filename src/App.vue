<template>
        <div id="app">
            <div v-for="recipe in recipes" :key="recipe.title + recipe.ingredients" class="card">
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
body{
  background: rgb(203,251,63);
  background: linear-gradient(43deg, rgba(203,251,63,1) 0%, rgba(84,227,204,1) 48%, rgba(255,0,232,1) 100%);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

.card{
  background: rgb(231,255,160);
  background: linear-gradient(43deg, rgba(231,255,160,1) 0%, rgba(148,255,238,1) 48%, rgba(204,255,190,1) 81%, rgba(199,255,180,1) 100%);
  display: inline-block;
  width: 200px;
  height: 400px;
  border-radius: 10px;
  vertical-align: top;
  margin: 10px;
  box-shadow: 0px 0px 10px 4px rgba(0, 0, 0, 0.5);
}
</style>
