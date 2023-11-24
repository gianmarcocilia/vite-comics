<script>
export default {
    props: {
        title: String,
        image: String
    }
}

</script>

<template>
    <div class="card">
        <img :src="image" alt="">
        <h5>{{title}}</h5>
    </div>

</template>

<style lang="scss" scoped>
.card {
    overflow: hidden;
    
    img {
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
        object-position: top;
        margin-bottom: 1rem;
    }
    h5 {
        text-transform: uppercase;
        color: white;
        font-size: 12px;
    }
}
</style>