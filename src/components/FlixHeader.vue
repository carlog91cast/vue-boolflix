<template>
    <nav>
        <input type="text"
                placeholder="search movies,series"
                v-model="searchInput"
                @keydown.enter="$emit('search', searchInput)">
        <button @click="$emit('search',searchInput)">Search</button>
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
