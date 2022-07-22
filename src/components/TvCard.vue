<template>
    <div class="row">
        <li class="list-group-item">
            <div class="poster-film">
                <img :src="`https://image.tmdb.org/t/p/w154/${info.poster_path}`" alt="">
            </div>
            <div class="title">
                <h3> {{ item.name }}</h3>
            </div>
            <div class="origin-title">
                <h4>{{ item.original_name }}</h4>
            </div>
            <div class="lang">
                <img v-if="langArray.includes(info.original_language)"
                    :src="`../assets/img/${info.original_language}.png'`" alt="info.original_language" />
                <div v-else>{{ info.original_language }}</div>
            </div>
            <div class="vote">
                <h5>{{ item.vote_average }}</h5>
            </div>
        </li>
    </div>
</template>

<script>
export default {
    name: 'TvCard',
    data: function () {
        return {

        }
    },
    props: ['item'],

    methods: {


    }

}

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

main {
    width: 60%;
    margin: 0 auto;
}
</style>
