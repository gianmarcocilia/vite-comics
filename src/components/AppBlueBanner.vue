<script>
export default {
    data() {
        return {
            bannerItems: [
                {
                    title: "digital comics",
                    image: "digital-comics"
                },
                {
                    title: "dc merchandise",
                    image: "merchandise"
                },
                {
                    title: "subscription",
                    image: "subscriptions"
                },
                {
                    title: "comic shop locator",
                    image: "shop-locator"
                },
            ]
        }
    },
    methods: {
        getImagePath(imgName) {
            return new URL(`../assets/img/buy-comics-${imgName}.png`, import.meta.url).href;
        }
    }
}
</script>

<template>
<section>
    <div class="container">
        <ul>
            <li v-for="item in bannerItems">
            <img :src="getImagePath(item.image)" alt="">
            <a href="">{{ item.title }}</a>
            </li>
            <li>
                <img src="../assets/img/buy-dc-power-visa.svg" alt="">
                <a href="">dc power visa</a>
            </li>
        </ul>
    </div>
</section>
</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
    background-color: $primary_color;
    .container {
        padding: 2rem 3rem;
        ul {
            @include flex(row, space-between, center);
            li {
                @include flex(row, center, center);
                gap: .5rem;
                img {
                    height: 50px;
                    max-width: 50px;
                }
                a {
                    text-transform: uppercase;
                    color: white;
                    font-size: 12px;
                }
            }
        }
    }
}
</style>