<template>
    <main>
        <ul class="list-group">
            <li v-for="movie in movies" :key="movie.id" class="list-group-item">
                {{ movie.title }} - {{ movie.original_title }} - {{ movie.original_language }} - {{ movie.vote_average }}
            </li>
        </ul>
    </main>
</template>

<script>
export default {
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
