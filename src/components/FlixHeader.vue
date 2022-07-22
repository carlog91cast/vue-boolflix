<template>
    <header class="container">
        <nav class="d-flex justify-content-around m-3">
            <img src="" alt="">
            <input type="text" placeholder="search movies,series" v-model="searchInput">
            <button class="btn btn-primary m-1" @click="$emit('search', searchInput, searchCommand)">Search</button>
        </nav>
    </header>

</template>

<script>
export default {
    name: 'FlixHeader',
    data() {
        return {
            searchInput: '',
            searchCommand: '',
        }
    }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
