<template>
  <nuxt-link class="cart" to="/Cart/">
    <font-awesome-icon :icon="['fas','shopping-cart']" />
    <div class="cart__counter">{{ itemCount }}</div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    itemCount: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style scoped>
.cart {
  position: relative;
  color: white;
  font-size: 2.2em;
  padding: 0.3em;
}

.cart__counter {
  position: absolute;
  color: black;
  font-weight: 700;
  font-size: 0.6em;
  top: 16px;
  left: 32px;
}
</style>