<template>
    <div>
        <li class="list-group-item">
            <div class="container">

            </div>
            {{ movie.title }} - {{ movie.original_title }} - {{ movie.original_language }} - {{ movie.vote_average }}
        </li>
    </div>
</template>

<script>
export default {
    name: 'MovieCard',
    props: ['movies'],

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
