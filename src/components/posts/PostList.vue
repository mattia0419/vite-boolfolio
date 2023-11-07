<script>
import PostCard from './PostCard.vue';
export default {
    data() {
        return {

        }
    },
    props: {
        posts: Array
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