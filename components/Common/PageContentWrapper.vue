<template>
  <div class="content">
    <div class="container">
      <slot name="image"></slot>

      <TheTitle class="title">
        <slot name="title"></slot>
      </TheTitle>

      <slot name="form"></slot>
    </div>
  </div>
</template>

<script>
import TheTitle from './TheTitle.vue'
export default {
  name: 'PageContentWrapper',
  components: { TheTitle },
}
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  justify-content: center;
}

.container {
  width: 100%;
  max-width: 344px;
  display: flex;
  align-items: center;
  flex-direction: column;
}

.title {
  margin-bottom: 36px;
}
</style>
