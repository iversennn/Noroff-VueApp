<template class="card">
        <div class="card">
          <img :src="recipeImg" />
          <p>Title: </p>{{title}}
          <p>Ingredients: </p>{{ingredients}}
          <p>Company Website: </p><a :href="website" target="_blank">Click Here for recipe</a> 
        </div>
</template>

<script>
export default {
    name: 'RecipeComponent',
    props: ['recipeImg','title','ingredients','website']
}
</script>

<style>
.card{
  display: inline-block;
  width: 400px;
  border: 2px solid black;
}
</style>