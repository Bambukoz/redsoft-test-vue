<template>
  <form>
    <label
      class="search__label visually-hidden"
      for="search-text"
    >Поиск</label>
    <input
      class="search__input"
      id="search-text"
      type="text"
      placeholder="Поиск по названию картины"
    >
    <button
      class="btn search-btn"
      type="submit"
    >
      Найти
    </button>
  </form>
</template>

<script>
export default {
  name: 'Search'
}

</script>
