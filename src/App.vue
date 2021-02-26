<template>
  <div
    class="page"
    id="app"
  >
    <Header class="page__header header" />
    <router-view />
    <Footer class="page__footer footer" />
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import Footer from './components/Footer/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">
@import 'assets/styles/style.scss';
</style>
