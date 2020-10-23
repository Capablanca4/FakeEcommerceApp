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