<template>
  <div class="v-popup">
    <div class="v-popup__header">
      <span>Popup name</span>
      <span>
        <i class="mayerial-icons">close</i>
      </span>
    </div>
    <div class="v-popup__content">
      <slot></slot>
    </div>
    <div class="v popup__footer">
      <button class="close_model">Close</button>
      <button class="submit_btn">Add to cart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "V-popup",
  components: {},
  props: {},
  data() {
    return {};
  },
  mounted() {},
  beforeDestroy() {},
  methods: {},
};
</script>

<style lang="css">
.v-popup {
  padding: 16px;
  position: fixed;
  top: 50px;
  right: 0;
  left: 0;
  width: 400px;
  &__header,
  &__footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__content {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .submit_btn {
    padding: 8px;
    color: #ffffff;
    background: #26ae68;
  }
  .close_modal {
    padding: 8px;
    color: #ffffff;
    background: red;
  }
}
</style>
