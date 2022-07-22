<template>
    <div class="row">
        <li class="list-group-item">
            <div class="title">
                <h4> {{ info.title }}</h4>
            </div>
            <div class="origin-title">{{ info.original_title }}</div>
            <div class="lang">{{ info.original_language }}</div>
            <div class="vote">{{ info.vote_average }}</div>
        </li>
    </div>
</template>

<script>
export default {
    name: 'MovieCard',
    data: function(){
        return{
            langArray : ["it", "en", "ja", "es", "de", "pt"]
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
