<script>
import PostCard from './PostCard.vue';
import axios from 'axios';

export default {
    data() {
        return {
            posts: [],
            api: {
                baseUrl: 'http://127.0.0.1:8000/api/',
            }
        }
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
    },
    components: {
        PostCard
    }
}
</script>

<template>
    <div class="container">
        <h2>PostList</h2>
        <div class="row g-3">
            <PostCard v-for="post in posts" :post="post"></PostCard>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>