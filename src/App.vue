<script>
import axios from 'axios';
import PostList from './components/posts/PostList.vue';
export default {
  data() {
    return {
      posts: [],
      api: {
        baseUrl: 'http://127.0.0.1:8000/api/',
      }
    }

  },
  components: {
    PostList
  },
  methods: {
    fetchPosts(uri = this.api.baseUrl + 'posts') {
      axios.get(uri).then((response) => {
        this.posts = response.data.data;
      });
    }
  },
  created() {
    this.fetchPosts();
  }
}
</script>


<template>
  <h1>hello world</h1>
  <hr>
  <PostList :posts="posts"></PostList>
</template>


<style lang="scss"></style>