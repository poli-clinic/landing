<script>

export default {
  name: 'Typography',
  props: {
    color: Number,
  },
};
</script>

<template>
  <div class="circle"></div>
</template>

<style scoped lang="scss">
.circle {
  display: block;
  width: 65px;
  height: 65px;
  border-radius: 100%;
  margin-left: 1rem;
  background: v-bind(color);
}
@media (max-width: 600px){
  .circle {
    margin: 1rem 0 0 0;
  }
}
</style>
