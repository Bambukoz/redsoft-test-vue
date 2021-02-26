<template>
  <footer>
    <div class="footer__wrapper">
      <router-link
        class="footer__logo"
        to="#nowhere"
        aria-label="Логотип The Famous"
      >
        <img
          src="@/assets/img/logo-museum-2.png"
          width="48"
          height="48"
          alt="Логотип The Famous"
        >
      </router-link>
      <Nav class="footer__nav nav nav--footer" />
      <Contacts class="footer__contacts contacts" />
    </div>
  </footer>
</template>

<script>
import Nav from '../Nav/Nav.vue'
import Contacts from './Contacts.vue'

export default {
  name: 'Footer',
  components: {
    Nav,
    Contacts
  }
}
</script>
