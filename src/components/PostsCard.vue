<template>
  <div class="caixa">
    <h1 v-if="qtdPosts > 0">{{ qtdPosts }} posts</h1>
    <h1 v-else>Não há posts</h1>
    <p v-if="qtdPosts > 0">View all posts</p>
  </div>
</template>
<script>
export default {
  name: 'PostsCard',
  props: {
    qtdPosts: {
      type: Number,
      default: 0,
    },
  },
}
</script>
<style scoped>
.caixa {
  border: solid 1px black;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 10px 10px 5px #888888;
}
</style>
