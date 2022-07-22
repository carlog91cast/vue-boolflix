<template>
    <div class="row">
        <li class="list-group-item">
            <div class="title">
                <h3> {{ info.title }}</h3>
            </div>
            <div class="origin-title">
                <h4>{{ info.original_title }}</h4>
            </div>
            <div class="lang">
                <img v-if="langArray.includes(info.original_language)" 
                :src="require(`.assets/img/${info.original_language}.png`)" 
                alt="info.original_language" />
                <div v-else>{{info.original_language}}</div>
            </div>
            <div class="vote">
                <h5>{{ info.vote_average }}</h5>
            </div>
        </li>
    </div>
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
