<template>
  <h1 class="title">
    <slot></slot>
  </h1>
</template>

<script>
export default {
  name: 'TheTitle',
}
</script>

<style lang="scss" scoped>
.title {
  font-size: $font-l;
  line-height: 42px;
  font-weight: 700;
  color: $text-strong;
}
</style>
