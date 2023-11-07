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
            <div class="card-header d-flex justify-content-between align-items-start">
                <span class="badge mx-1" :style="{ backgroundColor: post.type.color }">{{ post.type.name }}</span>
                <div>
                    <span class="badge rounded-pill mx-1" v-for="technology in post.technologies"
                        :style="{ backgroundColor: technology.color }">{{ technology.label }}</span>
                </div>
            </div>
            <div class="card-body">
                <h4>{{ post.title }}</h4>
            </div>
            <div class="card-footer">
                <a href="#" class="btn btn-primary">Vedi</a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>