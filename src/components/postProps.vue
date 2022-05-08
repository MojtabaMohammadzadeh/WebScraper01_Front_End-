<template>
  <div class="cards">
    <postsOfScraper v-for="post in posts" :key="post.id" :post='post'></postsOfScraper>
  </div>
</template>

<script>
import postsOfScraper from './posts.vue'
export default {

  name: 'postProps',
  components: {
    postsOfScraper
  },
  data: function () {
    return {
      posts: [
        { id: '1', title: 'Data Scince', univer: 'cambridge', city: 'paris' },
        { id: '2', title: 'IT', univer: 'MIT', city: 'USA' }, { id: '3', title: 'Chemical Egineering', univer: 'Ferdowsi', city: 'USA' }
      ]
    }
  }
}
</script>

<style scoped>

@media screen and (min-width: 480px) {

.cards{
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1em;
}
}

</style>
