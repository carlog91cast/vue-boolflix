<template>
    <li class="list-group-item">
        <div class="poster-film">
            <img :src="`https://image.tmdb.org/t/p/w154/${info.poster_path}`" alt="">
        </div>
        <div class="title">
            <h3> {{ info.title }}</h3>
        </div>
        <div class="origin-title">
            <h4>{{ info.original_title }}</h4>
        </div>
        <div class="lang mt-1 mb-1">
            <img v-if="langArray.includes(info.original_language)"
                :src="require(`../assets/img/${info.original_language}.png`)" alt="info.original_language" />
            <div v-else>{{ info.original_language }}</div>
        </div>
        <div class="vote mt-2">
            <h5><i v-for="index in setNumStar(info.vote_average)" :key="index" class="fa-solid fa-star"></i></h5>
        </div>
    </li>
</template>

<script>
export default {
    name: 'MovieCard',
    data: function () {
        return {
            langArray: ["it", "en", "ja", "es", "de", "pt"]
        }
    },
    props: ['info'],

    methods: {
        setNumStar(number) {
            return Math.round(number / 2)

        },

    }
 }

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

main {
    width: 60%;
    margin: 0 auto;

    .lang img {
        width: 5%;
    }
}
</style>
