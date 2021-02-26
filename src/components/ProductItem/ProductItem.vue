<template>
  <li
    :class="{'products__item--sold' : product.sold}"
  >
    <router-link
      class="products__link"
      to="#nowhere"
    >
      <picture>
        <source
          type="image/webp"
          :srcset="require(`@/assets/img/webp/${product.img}.webp`)"
        >
        <img
          :src="require(`@/assets/img/${product.img}.jpg`)"
          :alt="product.alt"
        >
      </picture>
    </router-link>
    <h2 class="products__title">
      {{ product.title }}
    </h2>
    <p class="products__author">
      {{ product.author }}
    </p>
    <div
      class="products__price-container"
      :class="{'products__price-container--sold' : product.sold}"
    >
      <div
        class="products__wrapper"
        :class="{'products__wrapper--sale' : product.oldPrice}"
      >
        <p
          class="products__sold-text"
          v-if="product.sold"
        >
          Продана на аукционе
        </p>
        <template v-else>
          <span
            class="products__price products__price--old"
            v-if="product.oldPrice"
          >{{ product.oldPrice }}
          </span>
          <span class="products__price products__price--current">{{ product.price }}</span>
        </template>
      </div>
      <button
        class="btn buy-btn"
        v-if="!product.sold"
        :class=" {'buy-btn--in-basket' : inCart} "
        @click="GetResponse"
      >
        {{ buttonContent }}
        <Preloader v-if="showPreloader === true" />
      </button>
    </div>
  </li>
</template>

<script>

import axios from 'axios'
import Preloader from '../common/Preloader'

export default {
  name: 'ProductItem',
  components: {
    Preloader
  },
  props: {
    product: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      inCart: {
        default: false,
        type: Boolean
      },
      showPreloader: {
        default: false,
        type: Boolean
      },
      response: null
    }
  },
  methods: {
    GetResponse: function () {
      axios.get('https://reqres.in/api/products/3')
        .then((response) => {
          this.response = response.data
          this.showPreloader = response.status === 200
        })
        .then(() => {
          this.AddItemToCart()
          this.showPreloader = false
        })
        .catch((error) => {
          console.log(error)
          return error
        })
    },
    AddItemToCart: function () {
      if (localStorage.getItem(this.product.id) === this.product.id) {
        localStorage.removeItem(this.product.id)
        this.inCart = false
      } else {
        localStorage.setItem(this.product.id, this.product.id)
        this.inCart = true
      }
    }
  },
  computed: {
    buttonContent: function () {
      return this.inCart ? 'В корзине' : 'Купить'
    }
  },

  mounted () {
    this.inCart = !!localStorage.getItem(this.product.id)
  }
}

</script>
