<template>
  <h1>Posts Page</h1>
  <PostItem :post="elem" v-for="elem in posts" :key="elem.id" />
</template>
<script>
import PostItem from '@/components/PostItem.vue'
export default {
  name: 'PostsPage',
  components: {
    PostItem,
  },
  data() {
    return {
      posts: Array,
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((data) => {
        console.log(data)
        console.log(data.length)
        this.posts = data
      })
      .catch((error) => {
        console.error('Error fetching posts:', error)
      })
  },
}
</script>
<style scoped></style>
