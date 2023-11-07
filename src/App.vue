<script>
import axios from 'axios';
import PostList from './components/posts/PostList.vue';
export default {
  data() {
    return {
      posts: [],
    }

  },
  components: {
    PostList
  },
  created() {
    axios.get('http://127.0.0.1:8000/api/posts').then((response) => {
      // console.log(response.data.data);
      this.posts = response.data.data;
    });
  }
}
</script>


<template>
  <h1>hello world</h1>
  <hr>
  <PostList></PostList>
</template>


<style lang="scss"></style>