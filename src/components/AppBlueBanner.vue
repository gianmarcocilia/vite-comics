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
@use "../style/partials/_variables" as *;

section {
    background-color: $primary_color;

    .container {
        padding: 2rem 3rem;

        @include response('l') {
            padding: 2rem 0;
            width: 90%;
        }

        @include response('md') {
            width: 98%;
        }

        ul {
            @include flex(row, space-between, center);

            @include response('sm') {
                @include flex(column, space-between, center);
                gap: 1rem;
            }

            li {
                @include flex(row, center, center);
                gap: .5rem;

                @include response('l') {
                    @include flex(column, center, center);
                    text-align: center;
                }

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