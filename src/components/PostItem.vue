<template>
  id: {{ post.id }}<br />
  title: {{ post.title }}<br />
  body: {{ post.body }}<br />
  <button @click="getComments()">View Comments</button>
  <p v-for="comm in comments" :key="comm">
    {{ comm.body }}<br />
    {{ comm.email }}
  </p>
  <hr />
</template>
<script>
export default {
  name: 'PostItem',
  props: {
    post: Object,
  },
  data() {
    return {
      comments: Array,
    }
  },
  mounted() {
    this.getComments()
  },
  methods: {
    getComments() {
      fetch(`https://jsonplaceholder.typicode.com/posts/${this.post.id}/comments`)
        .then((response) => response.json())
        .then((data) => {
          this.comments = data
        })
        .catch((error) => {
          console.error('Error fetching comments:', error)
        })
    },
  },
}
</script>
<style scoped></style>
