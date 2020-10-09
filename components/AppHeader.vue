<template>
  <header>
    <HeaderBars />
    <nuxt-link class="logo" to="/">
      <font-awesome-icon :icon="['fab', 'vuejs']" />
    </nuxt-link>
    <HeaderSearchBar />
    <HeaderUser />
    <HeaderCart v-bind:itemCount="itemCount" />
  </header>
</template>

<script>
import HeaderBars from "./HeaderBars";
import HeaderSearchBar from "./HeaderSearchBar";
import HeaderUser from "./HeaderUser";
import HeaderCart from "./HeaderCart";

export default {
  name: "AppHeader",
  components: {
    HeaderBars,
    HeaderSearchBar,
    HeaderUser,
    HeaderCart,
  },
  data() {
    return {
      itemCount: 0,
    };
  },
};
</script>

<style scoped>
header {
  display: flex;
  position: relative;
  justify-content: space-between;
  height: var(--header-height);
  background-color: var(--blue-Color);
}

.logo {
  font-size: 2.2em;
  padding: 0.3em;
  color: white;
}
</style>
