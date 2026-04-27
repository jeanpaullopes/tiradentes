<template>
  <div class="center cor">
    <h1>You did it!</h1>
    <PostsCard @clicado="goPosts()" :qtdPosts="nPosts" titulo="Posts" />
    <PostsCard @clicado="goTodos()" :qtdPosts="nTodos" titulo="Todos" />
    <input v-model="nPosts" />
    <input v-model="nTodos" />

    <p>
      Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
      documentation
    </p>
  </div>
</template>
<script>
import PostsCard from '../components/PostsCard.vue'

export default {
  name: 'HomePage',
  components: {
    PostsCard,
  },
  data() {
    return {
      nPosts: 0,
      nTodos: 0,
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

    fetch('https://jsonplaceholder.typicode.com/todos')
      .then((response) => response.json())
      .then((data) => {
        console.log(data)
        console.log(data.length)
        this.nTodos = data.length
      })
      .catch((error) => {
        console.error('Error fetching todos:', error)
      })
  },
  methods: {
    goPosts() {
      this.$router.push('/posts')
    },
    goTodos() {
      this.$router.push('/todos')
    },
  },
}
</script>
<style scoped>
.cor {
  background-color: #d2c8c9;
}
</style>
