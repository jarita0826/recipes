<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img :src="recipe.thumbnail" :alt="recipe.title">
    </div>
     <p>{{ $route.params.id }}</p>
     <h1>{{ recipe.descriptonText }}</h1>
  </section>
 
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve,reject)=>{
      setTimeout(()=>{
        resolve({
          recipe:[{
            id:"1",
            thumbnail:"https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=700%2C636",
            title:"Mozzarella gnocchi bake",
            previewText:"Very tasty indeed!",
            descriptonText:"Upgrade cheesy tomato pasta with gnocchi, chorizo and mozzarella for a comforting bake that makes an excellent midweek meal",
          },{
            id:"2",
            thumbnail:"https://images.immediate.co.uk/production/volatile/sites/30/2020/08/butter-chicken-cf6f9e2.jpg?quality=90&webp=true&resize=375,341",
            title:"Butter chicken",
            previewText:"Awesome chicken!!",
            descriptonText:"Fancy a healthy version of your favourite Friday night chicken curry? The chicken can be marinaded the day before so you can get ahead on your prep",
          }].find(el=>el.id === context.params.id)
        })
      },1500)
    })
  }
}
</script>

<style scoped>

.single-recipe{
  display: flex;
  flex-flow:column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipe-image{
  width:100%;
  
}
</style>