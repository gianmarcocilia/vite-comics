<script>
export default {
    data() {
        return {
            navItems: [
                {
                    title: "characters",
                },
                {
                    title: "comics",
                },
                {
                    title: "movies",
                },
                {
                    title: "tv",
                },
                {
                    title: "games",
                },
                {
                    title: "collectibles",
                },
                {
                    title: "videos",
                },
                {
                    title: "fans",
                },
                {
                    title: "news",
                },
                {
                    title: "shop",
                },
            ]
        }
    }
}
</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-1">
                    <img src="../assets/img/dc-logo.png" alt="">
                </div>
                <div class="col-2">
                    <ul>
                        <li v-for="(item, index) in navItems" :key="item.title"><a href="">{{ item.title }}</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;

.row {
    @include flex (row, space-between, center);
    padding: 1.5rem 0;

    .col-1 {
        width: fit-content;

        img {
            max-width: 80px;
        }
    }

    ul {
        @include flex (row, space-between, center);
        gap: 1rem;

        li a {
            text-transform: uppercase;
            color: black;
            font-weight: bold
        }
    }

}
</style>