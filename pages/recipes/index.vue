<template>
  <section class="recipes">

    <Recipe v-for="recipe in recipes" :key="recipe.id" :thumbnail ="recipe.thumbnail" :title="recipe.title" :id="recipe.id" :previewText ="recipe.previewText"/>
  
    
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
  components:{
    Recipe
  },
  asyncData() {
    return new Promise((resolve,reject)=>{
      setTimeout(()=>{
        resolve({
          recipes:[{
            id:"1",
            thumbnail:"https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=700%2C636",
            title:"Mozzarella gnocchi bake",
            previewText:"Very tasty indeed!",
          },{
            id:"2",
            thumbnail:"https://images.immediate.co.uk/production/volatile/sites/30/2020/08/butter-chicken-cf6f9e2.jpg?quality=90&webp=true&resize=375,341",
            title:"Butter chicken",
            previewText:"Awesome chicken!!",
          }]
        })
      },1500)
    })
  }
}

</script>

<style scoped>

.recipes{
  display: flex;
  flex-flow:row wrap;
  justify-content: center;
  align-items: center;
}

</style>

