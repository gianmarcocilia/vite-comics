<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import AppBlueBanner from './components/AppBlueBanner.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter,
    AppBlueBanner,
  },
  data() {
    return {
      
    }
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
  <AppBlueBanner />
  <AppFooter />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
