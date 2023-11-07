<script>
import PostCard from './PostCard.vue';
import axios from 'axios';
import { store } from '../../data/store';
export default {
    data() {
        return {
            posts: [],
            pagination: {
                next: null,
                prev: null,
                links: null
            }
        }
    },
    methods: {
        fetchPosts(uri = store.api.baseUrl + 'posts') {
            axios.get(uri).then((response) => {
                this.posts = response.data.data;

                this.pagination.prev = response.data.prev_page_url;
                this.pagination.next = response.data.next_page_url;
                this.pagination.links = response.data.links;
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
            <nav aria-label="Page navigation example">
                <ul class="pagination">
                    <li class="page-item" v-for="link in pagination.links" @click="fetchPosts(link.url)"><a
                            class="page-link" href="#" v-html="link.label"></a></li>
                </ul>
            </nav>
            <!-- <div>
                <a href="#" class="btn btn-primary" @click="fetchPosts(pagination.prev)">Prev</a>
                <a href="#" v-for="link in pagination.links" class="btn btn-primary" @click="fetchPosts(link.url)">{{
                    link.label }}</a>
                <a href="#" class="btn btn-primary" @click="fetchPosts(pagination.next)">Next</a>
            </div> -->
        </div>
    </div>
</template>

<style lang="scss" scoped></style>