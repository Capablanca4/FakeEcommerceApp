<template>
  <div class="bars" v-on:click="toggleMenu">
    <div class="bars__icon">
      <font-awesome-icon :icon="['fas', 'bars']" />
    </div>
    <ul class="sidebar" v-bind:class="{ hidden: hideMenu }">
      <li>
        <nuxt-link to="/">
          <font-awesome-icon :icon="['fas', 'bars']" />Home
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/Home/logIn">
          <font-awesome-icon :icon="['fas', 'sign-in-alt']" />logIn
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/Cart/">
          <font-awesome-icon :icon="['fas', 'shopping-cart']" />Cart
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/Store/">
          <font-awesome-icon :icon="['fas', 'store']" />Store
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HeaderBars",
  data() {
    return {
      hideMenu: true,
    };
  },
  methods: {
    toggleMenu: function () {
      this.hideMenu = !this.hideMenu;
    },
  },
};
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.bars__icon {
  font-size: 2.2em;
  padding: 0.3em;
  color: white;
}

.sidebar {
  position: fixed;
  z-index: 99999;
  left: 0;
  top: height(header);
  width: 10em;
  height: calc(100vh - #{height(header)});
  background-color: color(lighter-blue);
  transition-property: left;
  transition-duration: 1s;
  transition-timing-function: ease;

  &.hidden {
    left: -10em;
  }
}

li a {
  display: block;
  box-sizing: border-box;
  user-select: none;
  color: white;
  line-height: 4em;
  padding-left: 1.2em;
  font-size: 1.2em;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  border-bottom: 1px solid black;
  transition-duration: 0.4s;

  &:hover {
    padding-left: 1.6em;
  }
}
</style>
