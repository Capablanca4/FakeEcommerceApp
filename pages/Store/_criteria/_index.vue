<template>
  <section class="container">
    <h1>Research in Store</h1>
    <p>{{ test }}</p>
  </section>
</template>

<script>
export default {
  validate({ params }) {
    return (
      params.criteria === "all" ||
      params.criteria === "categories" ||
      params.criteria === "product"
    );
  },
  data() {
    return {
      test: this.$route.params,
    };
  },
};
</script>