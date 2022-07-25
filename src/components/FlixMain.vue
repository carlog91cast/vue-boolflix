<template>
    <main>
        <div class="container">
            <div class="movies-card">
                <h2>Films</h2>
                <ul class="list-group d-flex flex-wrap">
                    <MovieCard v-for="movie in movies" :key="movie.id" :info="movie" class="d-flex" />
                </ul>
            </div>
            <div class="series-card">
                <h2>TV serie</h2>
                <ul class="list-group d-flex flex-wrap">
                    <TvCard v-for="serie in series" :key="serie.id" :item="serie" class="d-flex" />
                </ul>
            </div>
        </div>
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

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap";

main {
    width: 100%;
    height: 100%;
    margin: 0 auto;
    background-color: #434343;
}

.movies-card {
    h2 {
        font-weight: 300;
        color: red;
    }
}

.series-card {
    h2 {
        font-weight: 300;
        color: red;
    }
}
</style>
