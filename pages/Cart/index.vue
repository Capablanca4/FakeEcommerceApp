<template>
  <section class="container">
    <CartResume class="resume" />
    <hr>
    <SuggestionsContent />
  </section>
</template>

<script>
import CartResume from "../../components/Cart/CartResume";
import SuggestionsContent from "../../components/Shared/SuggestionsContent";

export default {
  components: {
    CartResume,
    SuggestionsContent
  }
};
</script>

<style lang="scss" scoped>

.resume{
  margin: 2em auto !important;
}

</style>