<template>
  <div>
  <h1>Posts</h1>
  {{posts}}
  </div>
</template>

<script>
import PostsService from '@/services/PostsService'
export default {
  name: 'PostsPage',
  data () {
    return {
      posts: []
    }
  },
  methods: {
    async getPosts () {
      const response = await PostsService.fetchPosts()
      this.posts = response.data
    }
  },
  mounted () {
    this.getPosts()
  }
}
</script>
