<template>
  <header>
    <div class="header__wrapper">
      <router-link
        class="header__logo"
        to="#nowhere"
        aria-label="Логотип The Famous"
      >
        <img
          src="@/assets/img/logo-museum-1.png"
          width="48"
          height="48"
          alt="Логотип The Famous"
        >
      </router-link>
      <Nav class="header__nav nav" />
      <Search class="header__search search" />
    </div>
  </header>
</template>

<script>
import Nav from '../Nav/Nav'
import Search from './Search'

export default {
  name: 'Header',
  components: {
    Nav,
    Search
  }
}
</script>
