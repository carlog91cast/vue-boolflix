<template>
    <li class="bg-dark mt-3 p-2 m-2">
        <div class="poster-film">
            <img class="w-100" :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`" alt="">
        </div>
        <div class="series-text">
            <div class="title">
                <h4>Titolo:{{ item.name }}</h4>
            </div>
            <div class="origin-title">
                <h4>Titolo originale:{{ item.original_name }}</h4>
            </div>
            <div class="lang mt-1 mb-1">
                <img v-if="langArray.includes(item.original_language)"
                    :src="require(`../assets/img/${item.original_language}.png`)" alt="info.original_language" />
                <div v-else>{{ item.original_language }}</div>
            </div>
            <div class="vote d-flex mt-2">
                <span>Voto:</span>
                <i v-for="index in setNumStar(item.vote_average)" :key="index" class="fa-solid fa-star"></i>
            </div>
            <div class="overview">
                <h6>Overview:{{ item.overview }}</h6>
            </div>
        </div>
    </li>
</template>

<script>
export default {
    name: 'TvCard',
    data: function () {
        return {
            langArray: ["it", "en", "ja", "es", "de", "pt"]
        }
    },
    props: ['item'],

    methods: {
        // ripeto la stellina per un numero pari al risultato che mi dara la funzione che mi divide i decimani in numeri interi con un v for dentro l'i della stellina
        setNumStar(number) {
            return Math.round(number / 2)


        }
    }

}

</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap";

li {
    width: calc(100% / 6);
    list-style: none;

    .series-text {
        color: white;
        display: none;

        .lang img {
            width: 20px;
        }

        .vote i {
            color: yellow;
        }
    }

    .series-text:hover {
        display: block;
    }
}
</style>
