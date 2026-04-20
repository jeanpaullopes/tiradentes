<template>
  <div class="center">
    <h1>You did it!</h1>
    <PostsCard qtdPosts="0" />
    <p>
      Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
      documentation
    </p>
  </div>
</template>
<script>
import PostsCard from './components/PostsCard.vue'
export default {
  name: 'App',
  components: {
    PostsCard,
  },
}

//https://jsonplaceholder.typicode.com/posts
</script>
<style scoped>
.center {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>
