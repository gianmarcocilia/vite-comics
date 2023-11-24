<script>
import AppButton from './AppButton.vue';

export default {
    data() {
        return {
            footerTopLinks: [
                {
                    title: "dc comics",
                    subtitle: [
                        {
                            link: "Characters",
                        },
                        {
                            link: "Comics",
                        },
                        {
                            link: "Movies",
                        },
                        {
                            link: "TV",
                        },
                        {
                            link: "Games",
                        },
                        {
                            link: "Videos",
                        },
                        {
                            link: "News",
                        },
                    ],
                },
                {
                    title: "shop",
                    subtitle: [
                        {
                            link: "Shop DC",
                        },
                        {
                            link: "Shop DC Collectibles"
                        },
                    ],
                },
                {
                    title: "dc",
                    subtitle: [
                        {
                            link: "Terms Of Use",
                        },
                        {
                            link: "Privacy Policy (New)",
                        },
                        {
                            link: "Ad Choices",
                        },
                        {
                            link: "Advertising",
                        },
                        {
                            link: "Jobs",
                        },
                        {
                            link: "Subscriptions",
                        },
                        {
                            link: "Talent Workshops",
                        },
                        {
                            link: "CPSC Certidicates",
                        },
                        {
                            link: "Ratings",
                        },
                        {
                            link: "Shop Help",
                        },
                        {
                            link: "Contact Us",
                        },
                    ],
                },
                {
                    title: "sites",
                    subtitle: [
                        {
                            link: "DC",
                        },
                        {
                            link: "MAD Magazine",
                        },
                        {
                            link: "DC Kids",
                        },
                        {
                            link: "DC Universe",
                        },
                        {
                            link: "DC Power Visa",
                        },
                    ]
                },
            ],
            footerBotLinks: [
                {
                    link: "facebook"
                },
                {
                    link: "periscope"
                },
                {
                    link: "pinterest"
                },
                {
                    link: "twitter"
                },
                {
                    link: "youtube"
                }
            ]
        };
    },
    methods: {
        getImagePath(imgName) {
            return new URL(`../assets/img/footer-${imgName}.png`, import.meta.url).href;
        }
    },
    components: { AppButton }
}
</script>

<template>
    <footer>
        <div class="container">
            <section class="footer-top">
                <div class="row">
                    <div class="col" v-for="titleLink in footerTopLinks">
                        <h4>{{ titleLink.title }}</h4>
                        <ul>
                            <li v-for="link in titleLink.subtitle"><a href="">{{ link.link }}</a></li>
                        </ul>
                    </div>
                </div>
            </section>
        </div>
        <section class="footer-bottom">
            <div class="container">
                <div class="row">
                    <AppButton :isOutline="true" text="sign up" />
                    <ul>
                        <li>
                            <h4>FOLLOW US</h4>
                        </li>
                        <li v-for="img in footerBotLinks"><a href=""><img :src="getImagePath(img.link)" alt=""></a></li>
                    </ul>
                </div>
            </div>
        </section>
    </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

footer {
    background-image: url(../assets/img/footer-bg.jpg);

    .container {
        @include response('md') {
            width: 95%;
        }
    }

    .footer-top {
        background-image: url(../assets/img/dc-logo-bg.png);
        background-repeat: no-repeat;
        background-position: right;

        @include response('l') {
            background-size: 350px;
        }

        @include response('md') {
            background-size: 50%;
        }

        .row {
            padding: 2rem 0;
            @include flex(column, space-between, stretch);
            flex-wrap: wrap;
            height: 314px;
            width: 45%;

            @include response('sm') {
                height: auto;
                width: 100%;
                @include flex(row, space-between, stretch);
            }

            .col {
                width: fit-content;

                @include response('sm') {
                    width: calc(100% / 4);
                    text-align: center;
                }

                h4 {
                    text-transform: uppercase;
                    color: white;
                    margin-bottom: .5rem;
                }

                li {
                    padding: .2rem 0;
                    font-size: 12px;

                    a {
                        color: rgb(142 144 146);
                    }
                }
            }
        }

    }

    .footer-bottom {
        background-color: $footer_bg_color;

        .row {
            @include flex (row, space-between, center);
            padding: 1.5rem 0;

            ul {
                @include flex (row, space-between, center);
                gap: 1rem;

                @include response('sm') {
                    display: none;
                }

                h4 {
                    color: $primary_color;
                    @include response('md') {
                    display: none;
                }
                }
            }
        }
    }
}
</style>