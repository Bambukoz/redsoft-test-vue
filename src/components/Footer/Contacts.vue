<template>
  <div>
    <div class="contacts__tel">
      <img
        src="@/assets/img/svg/icon-phone.svg"
        alt="Иконка телефона"
      >
      <a
        class="contacts__tel-link"
        href="tel:+74955555555"
      >+7 (495) 555-55-55</a>
    </div>
    <div class="contacts__address">
      <img
        src="@/assets/img/svg/icon-address.svg"
        alt="Иконка пин"
      >
      <address class="contacts__address-text">
        г. Москва, ул. Расплетина, 24
      </address>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contacts'
}
</script>
