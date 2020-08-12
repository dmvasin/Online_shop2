<template>
  <div class="v-catalog">
    <h1>Каталог</h1>
    <div class="v-catalog__list">
      <v-catalog-item
        v-for="product in PRODUCTS"
        :key="product.article"
        v-bind:product_data="product"
        @addToCart="addToCart"
      />
    </div>
  </div>
</template>

<script>
import vCatalogItem from "./v-catalog-item";
import { mapActions, mapGetters } from "vuex";
export default {
  name: "v-catalog",
  components: {
    vCatalogItem,
  },
  props: {},
  data() {
    return {
      // products: [
      //   {
      //     image: "1.jpg",
      //     name: "T-shirt 1",
      //     price: 2100,
      //     article: "T1",
      //     available: true,
      //     category: "Мужские",
      //   },
      //   {
      //     image: "2.jpg",
      //     name: "T-shirt 2",
      //     price: 3150,
      //     article: "T2",
      //     available: true,
      //     category: "Женские",
      //   },
      //   {
      //     image: "3.jpg",
      //     name: "T-shirt 3",
      //     price: 4200,
      //     article: "T3",
      //     available: false,
      //     category: "Женские",
      //   },
      //   {
      //     image: "4.jpg",
      //     name: "T-shirt 4",
      //     price: 5300,
      //     article: "T4",
      //     available: true,
      //     category: "Мужские",
      //   },
      //   {
      //     image: "5.jpg",
      //     name: "T-shirt 5",
      //     price: 6500,
      //     article: "T5",
      //     available: false,
      //     category: "Женские",
      //   },
      //   {
      //     image: "6.jpeg",
      //     name: "T-shirt 6",
      //     price: 8700,
      //     article: "T6",
      //     available: true,
      //     category: "Женские",
      //   },
      // ],
    };
  },

  beforeDestroy() {},
  computed: {
    ...mapGetters(["PRODUCTS"]),
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API", "ADD_TO_CART"]),
    addToCart(data) {
      this.ADD_TO_CART(data);
    },
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API().then((response) => {
      if (response.data) {
        console.log("Data arrived!");
      }
    });
  },
};
</script>

<style lang="scss">
.v-catalog {
  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
