<template>
    <div class="container">
        <ul class="row">
            <li>
                <h1>{{ film.title }}</h1>
                <h2>{{ film.original_title }}</h2>
                <h3>{{ film.original_language }}</h3>
                <h3>{{ film.vote_average }}</h3>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: ['film'],

}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
