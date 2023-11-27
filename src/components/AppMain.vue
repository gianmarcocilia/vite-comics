<script>
import {store} from '../store';
import AppButton from './AppButton.vue';
import AppCard from './AppCard.vue';

export default {
    data() {
        return {
            store,
        };
    },
    components: { AppCard, AppButton }
}
</script>

<template>
    <main>
        <div class="container">
            <div class="top-button">
                <AppButton :isOutline="false" text="current series" />
            </div>
            <div class="row">
                <div class="col" v-for="item in store.comics">
                    <AppCard :title="item.series" :image="item.thumb" />
                </div>
            </div>
            <div class="button">
                <AppButton :isOutline="false" text="load more" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

main {
    background-color: $main_bg_color;
    padding: 3rem 0;
    position: relative;

    .container {
        @include response('md') {
            width: 95%;
        }
    }

    .top-button {
        position: absolute;
        left: 10%;
        top: 0;
        transform: translateY(-50%);
        font-size: 18px;
        font-weight: bold;

        @include response('md') {
            font-size: 14px;
        }

        @include response('sm') {
            font-size: 12px;
            left: 5%
        }
    }

    .row {
        @include flex (row, space-between, stretch);
        flex-wrap: wrap;
        width: 100%;
        gap: 1rem;

        .col {
            width: calc((100% / 6) - 5rem / 6);

            @include response('md') {
                width: calc((100% / 4) - 3rem / 4);
            }

            @include response('sm') {
                width: calc((100% / 2) - 1rem / 2);
            }
        }
    }

    .button {
        padding-top: 1.5rem;
        display: flex;
        justify-content: center;
        font-size: 14px;
    }
}
</style>