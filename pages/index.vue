<template>
  <div class="container">
    <Carroussel />
  </div>
</template>

<script>
import Carroussel from "../components/Home/Carroussel";

export default {
  components: {
    Carroussel,
  },
};
</script>

<style scoped>
.container {
  width: 100vw;
  padding: 3vh 3vw 3vh 3vw;
}
</style>