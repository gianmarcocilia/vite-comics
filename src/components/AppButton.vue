<script>
export default {
    props: {
        text: String,
        isOutline: Boolean
    }
}
</script>

<template>

<a :class="isOutline ? 'outline' : ''" href="">{{ text }}</a>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
a {
    text-align: center;
    color: white;
    text-transform: uppercase;
    background-color: $primary_color;
    display: inline-block;
    width: fit-content;
    border: none;
    padding: .5rem 1rem;
    font-size: 14px;

    &.outline {
        background-color: transparent;
        border: 1px solid $primary_color;
    }
}
</style>