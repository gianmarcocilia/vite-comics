<script>
export default {
   
}
</script>

<template>
    <img src="../assets/img/jumbotron.jpg" alt="">
</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
img {
    width: 100%;
    display: block;
    object-fit: cover;
    object-position: top;
    max-height: 350px;

    @include response('md') {
            max-height: 250px;
        }

        @include response('md') {
            max-height: 150px;
        }
}
</style>