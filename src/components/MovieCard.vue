<template>
    <li @mouseover="upHere = false" @mouseleave="upHere = true" class="bg-dark mt-3 p-2 m-2">
        <div v-show="upHere" class="poster-film">
            <img class="w-100" :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="">
        </div>
        <div v-show="!upHere" class="movie-text mt-3">
            <div class="title">
                <h5>Titolo : {{ info.title }}</h5>
            </div>
            <div class="origin-title">
                <h5>Titolo originale : {{ info.original_title }}</h5>
            </div>
            <div class="lang mt-1 mb-1">
                <img v-if="langArray.includes(info.original_language)"
                    :src="require(`../assets/img/${info.original_language}.png`)" alt="info.original_language" />
                <div v-else>{{ info.original_language }}</div>
            </div>
            <div class="vote d-flex mt-2">
                <span>Voto:</span>
                <i v-for="index in setNumStar(info.vote_average)" :key="index" class="fa-solid fa-star"></i>
            </div>
            <div class="overview">
                <h6>Overview:{{ info.overview }}</h6>
            </div>
        </div>
    </li>
</template>

<script>
export default {
    name: 'MovieCard',
    data: function () {
        return {
            langArray: ["it", "en", "ja", "es", "de", "pt"],
            upHere : true
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

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap";

li {
    width: calc(100% / 6);
    list-style: none;

    .movie-text {
        color: white;
        
        h5{
            font-size: 18px;
        }
        .overview{
            h6{
                font-size: 12px;
            }
        }


        .lang img {
            width: 30px;
        }

        .vote i {
            color: yellow;
        }
    }
   


}
</style>
