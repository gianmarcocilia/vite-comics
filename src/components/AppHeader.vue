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
                    <li v-for="(item, index) in navItems" :key="item.title" :class="{ 'active': item.isActive }"><a
                            href="">{{ item.title }}</a></li>
                </ul>
                <img class="hamburger" src="../assets/img/hamburger-menu.svg" alt="">
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

header {
    height: calc($header_height + $header_top_height);

    @include response('sm') {
        height: $header_height;
    }

    .header-top {
        background-color: black;
        height: $header_top_height;

        @include response('sm') {
            display: none;
        }
    }

    .container {
        @include response('l') {
            width: 100%;
            padding: 0 1rem;
        }
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

        @include response('md') {
            display: none;
        }

        li {
            position: relative;

            &::after {
                content: '';
                display: block;
                background-color: $primary_color;
                position: absolute;
                width: 100%;
                bottom: 0;
                left: 0;
            }

            &:hover::after {
                height: 5px;
            }

            &:hover {
                color: $primary_color;
            }

            &.active::after {
                height: 5px;
            }

            &.active {
                color: $primary_color;

                @include response('l') {
                    display: none;
                }
            }

            a {
                text-transform: uppercase;
                font-weight: bold;
                line-height: calc($header_height);
                font-size: 14px;
                color: inherit;
            }

        }
    }

    .hamburger {
        display: none;
        cursor: pointer;

        @include response('md') {
            display: block;
        }
    }
}</style>