<template>
  <div class="caixa" @click="goPosts()">
    <h1 v-if="qtdPosts > 0">{{ qtdPosts }} posts</h1>
    <h1 v-else>Não há posts</h1>
    <RouterLink to="/posts" v-if="qtdPosts > 0">View all posts</RouterLink>
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
  methods: {
    goPosts() {
      this.$router.push('/posts')
    },
  },
}
</script>
<style scoped>
.caixa {
  cursor: pointer;
  border: solid 1px black;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 10px 10px 5px #888888;
}
</style>
