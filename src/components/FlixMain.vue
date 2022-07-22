<template>
    <main>
        <ul class="list-group row">
            <MovieCard v-for="movie in movies" :key="movie.id" :info="movie" class="list-group-item" />
            <TvCard v-for="serie in series" :key="serie.id" :item="serie" class="list-group-item" />
        </ul>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue';
import TvCard from './TvCard.vue';
export default {
    props: ["movies",
            "series"],
    methods: {

    },
    components: {
        MovieCard,
        TvCard,
    }
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
