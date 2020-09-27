<template>
        <div class="card-info">
          <img :src="recipeImg" class="img"/>
          <h2>{{title}}</h2>
          <div class="ingredient-box">
            <p>{{ingredients}}</p>
            <a class="link" rel="noreferrer noopener" :href="website" target="_blank">Click Here for recipe</a>
          </div>
           
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
  box-shadow: 0px 0px 6px 2px rgba(0, 0, 0, 0.611);
}
.ingredient-box{
  position: relative;
  background: rgba(48, 48, 48, 0.864);
  color: white;
  height: 150px;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 0px 4px 1px rgba(0, 0, 0, 0.611);
}
p{
  margin: 0;
}
.link{
  color: white;
  position: absolute;
  bottom: 15px;
  left: 8px;
}
.link:hover{
  background:black;
  color: white;
}
h2{
  font-size: 16px;
  height: 30px;
}
</style>