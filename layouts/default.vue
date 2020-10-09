<template>
  <div>
    <AppHeader />
    <Nuxt />
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader";

export default {
  components: {
    AppHeader,
  },
};
</script>

<style>
:root {
  --blue-Color: #003049;
  --blue-Color-lighter: #00507a;
  --orange-Color-darker: #d46e01;
  --orange-Color: #f77f00;
  --yellow-Color: #fcbf49;
  --limon-Color: #eae2b7;
  --grey-Color: #c4c4c4;
  --header-height: 70px;
}

html {
  font-family: Arial, sans-serif;
  font-size: 18px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
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
</style>
