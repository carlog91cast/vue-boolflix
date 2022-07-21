<template>
    <div class="container">
        <div class="row">
            <ul>
                <li>{{films.title}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props: ['films'],

}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
