<template>
  <h1 v-if="heading === 1"><slot /></h1>
  <h2 v-if="heading === 2"><slot /></h2>
  <h3 v-if="heading === 3"><slot /></h3>
  <h4 v-if="heading === 4"><slot /></h4>
  <h5 v-if="heading === 5"><slot /></h5>
  <h6 v-if="heading === 6"><slot /></h6>
</template>

<style scoped lang="scss">
  h1{ font-size: 3rem; }
  h2{ font-size: 2.25rem; }
  h3{ font-size: 1.5rem; }
  h4{ font-size: 1.15rem; text-transform: uppercase; }
  h5{ font-size: 1rem; }
  h6{ font-size: 0.85rem; }

  *{
    font-family: 'Rock Salt', cursive;
  }
</style>

<script>
export default {
  name: 'Typography',
  props: {
    heading: Number,
  },
};

</script>