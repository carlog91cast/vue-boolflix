<template>
    <nav>
        <input type="text"
                placeholder="search movies,series"
                v-model="searchInput">
        <button class="btn btn-primary m-1" @click="$emit('search',searchInput)">Search</button>
    </nav>
</template>

<script>
export default {
    name: 'FlixHeader',
    data() {
        return {
            searchInput: ''
        }
    }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
