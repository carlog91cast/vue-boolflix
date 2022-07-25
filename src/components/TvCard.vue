<template>
    <li class="list-group-item bg-dark mt-3">
        <div class="poster-film">
            <img :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`" alt="">
        </div>
        <div class="series-text d-none">
            <div class="title">
                <h3>Titolo:{{ item.name }}</h3>
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
                <h5><i v-for="index in setNumStar(item.vote_average)" :key="index" class="fa-solid fa-star"></i></h5>
            </div>
            <div class="overview">
                <h5>Overview:{{ item.overview }}</h5>
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

main {
    width: 60%;
    margin: 0 auto;
    background-color: #434343;
}
</style>
