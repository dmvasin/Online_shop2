<template>
  <div class="v-catalog">
    <h1>Catalog</h1>
    <v-catalog-item />
  </div>
</template>

<script>
import vCatalogItem from "./V-catalog-item";
export default {
  name: "V-catalog",
  components: {
    vCatalogItem
  },
  props: {},
  data() {
    return {};
  },
  mounted() {},
  beforeDestroy() {},
  methods: {}
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
