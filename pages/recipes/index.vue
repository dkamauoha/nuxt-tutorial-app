<template>
  <section class='recipes'>
    <Recipe
      v-for='recipe in recipes'
      :key='recipe.id'
      :thumbnail="recipe.thumbnail"
      :title='recipe.title'
      :id='recipe.id'
      :previewText='recipe.previewText'
    />
  </section>
</template>

<script>
  import Recipe from '@/components/Recipe'

  export default {
    components: {
      Recipe
    },
    asyncData() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            recipes: [
              {
                id: '1',
                title: 'Delicious Dish',
                previewText: 'Awesome Dish',
                thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
              },
              {
                id: '2',
                title: 'French Fries',
                previewText: 'Everyone Loves Them!',
                thumbnail: "https://www.rd.com/wp-content/uploads/2018/04/9-Foods-You-Should-Never-Eat-Before-Bed-760x506.jpg"
              }
            ]
          })
        },1500)
      })
    }
  }
</script>

<style scoped>
  .recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
  }
</style>