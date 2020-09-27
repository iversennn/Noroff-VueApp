<template>
        <div class="card-info">
          <img :src="recipeImg" class="img"/>
          <p>Title:{{title}} </p>
          <p>Ingredients: {{ingredients}}</p>
          <a class="link" rel="noreferrer noopener" :href="website" target="_blank">Click Here for recipe</a> 
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
.img{
  border-radius: 15px;
}
.link:hover{
  background:black;
  color: white;
}
</style>