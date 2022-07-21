<template>
    <div class="container">
        <ul class="row list-group">
            <li class=" col-4 list-group-item">{{ film.title }}</li>
            <li class=" col-4 list-group-item">{{ film.original_title }}</li>
            <li class=" col-4 list-group-item">{{ setFlagLang(film) }}</li>
            <li class=" col-4 list-group-item">{{ film.vote_average }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    props: ['film'],

    methods: {
        setFlagLang(movie) {
            const img = `../assets/img/it.png`;
            if (movie.original_language == "it") {
                "it" === img;
            }
        }
    }

}

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
