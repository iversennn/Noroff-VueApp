<template>
        <div class="card-info">
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
.card-info{
  padding: 20px;
}
</style>