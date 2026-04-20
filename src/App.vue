<template>
  <div class="center">
    <h1>You did it!</h1>
    <PostsCard :qtdPosts="nPosts" />
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
  data() {
    return {
      nPosts: 0,
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((data) => {
        console.log(data)
        console.log(data.length)
        this.nPosts = data.length
      })
      .catch((error) => {
        console.error('Error fetching posts:', error)
      })
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
