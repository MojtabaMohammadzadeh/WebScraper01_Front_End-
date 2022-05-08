<template>
  <div class="cardsStyle">
    <q-card class="my-card" align="center">
      <q-card-section class="bg-primary text-white">
        <div class="text-h6">{{post.title}}</div>
        <div class="text-subtitle2">{{post.univer}}</div>
      </q-card-section>

      <q-separator />

      <q-card-actions align="left">
        <q-btn flat>{{post.city}}</q-btn>

      </q-card-actions>
    </q-card>

  </div>
</template>

<script>
export default {
  name: 'postsOfScraper',

  props: {
    post: Object
  },
  setup () {
    return {
    }
  }
}
</script>

<style scoped>

@media screen and (min-width: 480px) {

.cardsStyle{
  width: 30vw;
  margin: 1em;
}
}
@media screen and (max-width: 480px) {

.cardsStyle{
  width: 90%;
  margin: 1em;
}
}

</style>
