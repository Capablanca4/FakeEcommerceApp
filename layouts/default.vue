<template>
  <div class="default">
    <AppHeader />
    <Nuxt class="content" />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";

export default {
  components: {
    AppHeader,
    AppFooter
  },
};
</script>

<style lang="scss">

html {
  font-family: Arial, sans-serif;
  font-size: 18px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  overflow-x: hidden;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

* {
  list-style: none;
  margin: 0;
  padding: 0;
}

.default{
  min-height: 100vh;
  position: relative;
}

.content{
  width: 100vw;
  padding: 0 3vw 3vh 3vw;

  & > *{
    margin: 2vh 0 2vh 0;
  }
}
</style>
