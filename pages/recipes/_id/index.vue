<template>
  <section section class='single-recipe'>
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class='recipe-image' :src='recipe.thumbnail' alt=''>
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
  export default {
    asyncData(context) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            recipe: [
              {
                id: '1',
                title: 'Delicious Dish',
                previewText: 'Awesome Dish',
                descriptionText: 'This is really a delicious meal!',
                thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
              },
              {
                id: '2',
                title: 'French Fries',
                previewText: 'Everyone Loves Them!',
                descriptionText: 'This is really a delicious side dish!',
                thumbnail: "https://www.rd.com/wp-content/uploads/2018/04/9-Foods-You-Should-Never-Eat-Before-Bed-760x506.jpg"
              }
            ].find(el => el.id === context.params.id)
          })
        },1500)
      })
    }
  }
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
}
</style>
