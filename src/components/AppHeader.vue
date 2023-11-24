<script>
export default {
    data() {
        return {
            navItems: [
                {
                    title: "characters",
                    isActive: false
                },
                {
                    title: "comics",
                    isActive: true
                },
                {
                    title: "movies",
                    isActive: false
                },
                {
                    title: "tv",
                    isActive: false
                },
                {
                    title: "games",
                    isActive: false
                },
                {
                    title: "collectibles",
                    isActive: false
                },
                {
                    title: "videos",
                    isActive: false
                },
                {
                    title: "fans",
                    isActive: false
                },
                {
                    title: "news",
                    isActive: false
                },
                {
                    title: "shop",
                    isActive: false
                },
            ]
        }
    },
    methods: {

    }
}
</script>

<template>
    <header>
        <div class="header-top"></div>
        <div class="container">
            <div class="row">
                <img src="../assets/img/dc-logo.png" alt="">
                <ul>
                    <li v-for="(item, index) in navItems" :key="item.title"><a :class="{'active': item.isActive}" href="">{{ item.title }}</a></li>
                </ul>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

header {
    height: calc($header_height + $header_top_height);
    .header-top {
        background-color: black;
        height: $header_top_height;
    }
}

.row {
    @include flex (row, space-between, center);
    height: $header_height;

    img {
        width: calc($header_height - 20px)
    }

    ul {
        @include flex (row, space-between, center);
        gap: 1rem;

        li a {
            text-transform: uppercase;
            color: black;
            font-weight: bold;
            line-height: calc($header_height - 5px);
            font-size: 14px;

            &:hover {
                color: $primary_color;
            }

            &::after {
                content: '';
                display: block;
                height: 5px;
                width: 0;
                background-color: $primary_color;
            }

            &:hover::after {
                width: 100%;
            }

            &.active {
                color: $primary_color;
            }

            &.active::after {
                width: 100%;
            }
        }
    }

}
</style>