<template>
  <div v-if="col === 1" class="col col--1">
    <slot></slot>
  </div>
  <div v-if="col === 2" class="col col--2">
    <slot></slot>
  </div>
  <div v-if="col === 3" class="col col--3">
    <slot></slot>
  </div>
  <div v-if="col === 4" class="col col--4">
    <slot></slot>
  </div>
  <div v-if="col === 6" class="col col--6">
    <slot></slot>
  </div>
  <div v-if="col === 8" class="col col--8">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Grid",
  props: {
    col: Number,
  }
}
</script>

<style scoped lang="scss">
*, ::after, ::before {
  box-sizing: border-box;
}

.col {
  padding-left: 1rem;
  padding-right: 1rem;
}

.col--1 {
  flex: 0 0 8.3333%;
  max-width: 8.3333%;
}

.col--2 {
  flex: 0 0 16.6666%;
  max-width: 16.6666%;
}

.col--3 {
  flex: 0 0 25%;
  max-width: 25%;
}

.col--4 {
  flex: 0 0 33.3333%;
  max-width: 33.3333%;
}

.col--6 {
  flex: 0 0 50%;
  max-width: 50%;
}

.col--8 {
  flex: 0 0 66.6666%;
  max-width: 66.6666%;
}

@media(max-width: 767px){
  .col{
    flex: 0 0 100%;
    max-width: 100%;
    margin-bottom: 2rem;
  }
}

</style>