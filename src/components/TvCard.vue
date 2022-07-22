<template>
    <div class="row">
        <li class="list-group-item">
            <div class="title">
                <h3> {{ item.title }}</h3>
            </div>
            <div class="origin-title">
                <h4>{{ item.original_title }}</h4>
            </div>
            <!-- <div class="lang">
                <img v-if="langArray.includes(info.original_language)" 
                :src="`..assets/img/${info.original_language}.png'`" 
                alt="info.original_language" />
                <div v-else>{{info.original_language}}</div>
            </div> -->
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
