<template>
  <div class="v-catalog-item">
    <v-popup />

    <img
      class="v-catalog-item__image"
      v-bind:src="require('../../assets/images/' + product_data.image)"
      alt="img"
    />
    <p class="v-catalog-item__name">{{ product_data.name }}</p>
    <p class="v-catalog-item__price">{{ product_data.price }} P.</p>
    <button class="v-catalog-iten__show-info" @click="showPoputInfo">
      Show info
    </button>
    <button class="v-catalog-item__add_to_cart_btn btn" @click="addToCart">
      Добавить в корзину
    </button>
  </div>
</template>

<script>
import vPopup from "../popup/v-popup";

export default {
  name: "v-catalog-item",
  components: {
    vPopup,
  },
  props: {
    product_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {};
  },
  mounted() {},
  beforeDestroy() {},
  methods: {
    showPoputInfo() {},
    addToCart() {
      this.$emit("addToCart", this.product_data);
    },
  },
};
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: $padding * 2;
  margin-bottom: $margin * 2;
  &__image {
    width: 100px;
  }
}
</style>
