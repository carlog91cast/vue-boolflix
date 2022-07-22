<template>
    <main>
        <ul class="list-group">
            <MovieCard v-for="movie in movies" :key="movie.id" :info="movie" class="list-group-item" />
        </ul>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue';
export default {
    props: ["movies"],
    methods: {

    },
    components: { MovieCard }
}

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

main {
    width: 60%;
    height: 100%;
    margin: 0 auto;
}
</style>
