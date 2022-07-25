<template>
    <header class="bg-dark">
        <nav class="navbar m-3">
            <div class="text-danger fw-5">
                <h1>BOOLFLIX</h1>
            </div>
            <div class="d-flex mb-2">
                <input class="form-control me-2" type="text" placeholder="search movies,series" v-model="searchInput">
                <button class="btn btn-danger" @click="$emit('search', searchInput)">Search</button>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'FlixHeader',
    data() {
        return {
            searchInput: '',
        }
    }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

</style>
