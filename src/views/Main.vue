<template>
  <main class="page__main main">
    <h1 class="main__title">
      Картины эпохи Возрождения
    </h1>
    <section class="main__products products">
      <ul class="products__list">
        <ProductItem
          class="products__item"
          v-for="productItem in cards"
          :key="productItem.id"
          :product="productItem"
        />
      </ul>
    </section>
  </main>
</template>

<script>
import ProductItem from '../components/ProductItem/ProductItem'

export default {
  name: 'Main',
  components: {
    ProductItem
  },
  data () {
    return {
      cards: [
        {
          id: '1',
          title: '«Рождение Венеры»',
          author: 'Сандро Боттичелли',
          alt: 'Картина Сандро Боттичелли - «Рождение Венеры»',
          price: '1 000 000 $',
          oldPrice: '2 000 000 $',
          sold: false,
          img: 'img1@1x'
        },
        {
          id: '2',
          title: '«Тайная вечеря»',
          author: 'Леонардо да Винчи',
          alt: 'Картина Леонардо да Винчи - «Тайная вечеря»',
          price: '3 000 000 $',
          oldPrice: false,
          sold: false,
          img: 'img2@1x'
        },
        {
          id: '3',
          title: '«Сотворение Адама»',
          author: 'Микеланджело',
          alt: 'Картина Микеланджело - «Сотворение Адама»',
          price: '5 000 000 $',
          oldPrice: '6 000 000 $',
          sold: false,
          img: 'img3@1x'
        },
        {
          id: '4',
          title: '«Урок анатомии»',
          author: 'Рембрандт',
          alt: 'Картина Рембрандта - «Урок анатомии»',
          price: false,
          oldPrice: false,
          sold: true,
          img: 'img4@1x'
        }
      ]
    }
  },
  mounted () {
    document.title = 'Алексей Ежов | тестовое задание для Redsoft'
  }
}

</script>
