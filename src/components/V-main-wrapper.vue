<template>
  <div class="v-main-wrapper">
    <p>{{title}}</p>
    <v-catalog />
    <v-cart />
  </div>
</template>

<script>
import vCatalog from "./V-catalog";
import vCart from "./V-cart";
export default {
  name: "V-main-wrapper",
  components: {
    vCatalog,
    vCart
  },
  props: {},
  data() {
    return {
      title: "Main wrapper"
    };
  },
  computed: {},
  methods: {},
  watch: {},
  mounted() {
    console.log("Hello i am ufefgl");
  }
};
</script>

<style lang="scss">
.v-main-wrapper {
  max-width: 900px;
  margin: 0 auto;
}
</style>
