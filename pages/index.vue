<template>
  <div class="container">
    <Carroussel />
    <IndexContent />
  </div>
</template>

<script>
import Carroussel from "../components/Home/Carroussel";
import IndexContent from "../components/Home/IndexContent.vue";

export default {
  components: {
    Carroussel,
    IndexContent
  },
};
</script>

<style scoped>
.container {
  width: 100vw;
  padding: 0 3vw 3vh 3vw;
}

.container > *{
  margin-top: 3vh;
}
</style>