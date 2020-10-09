<template>
  <div>
    <h1>{{ error.statusCode }} Not Found</h1>
    <p>{{ error.message }}</p>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
};
</script>
