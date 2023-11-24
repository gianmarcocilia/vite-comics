<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import AppBlueBanner from './components/AppBlueBanner.vue';
import AppJumbo from './components/AppJumbo.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter,
    AppBlueBanner,
    AppJumbo
},
}
</script>

<template>
  <AppHeader />
  <AppJumbo />
  <AppMain />
  <AppBlueBanner />
  <AppFooter />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
