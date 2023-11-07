<script>
export default {
    data() {
        return {

        }
    },
    props: {
        post: Object
    }
}
</script>

<template>
    <div class="col-4">
        <div class="card h-100">
            <div class="card-body">
                <h4>{{ post.title }}</h4>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>