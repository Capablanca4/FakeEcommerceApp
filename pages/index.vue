<template>
  <div class="container">
    <Carroussel />
    <SuggestionsContent />
  </div>
</template>

<script>
import Carroussel from "../components/Home/Carroussel";
import SuggestionsContent from "../components/Shared/SuggestionsContent.vue";

export default {
  components: {
    Carroussel,
    SuggestionsContent
  },
};
</script>