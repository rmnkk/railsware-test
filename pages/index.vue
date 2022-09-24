<template>
  <div class="container">
    <h1>
      Please <Nuxt-link to="login" class="link">Log In</Nuxt-link> to proceed
    </h1>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style scoped lang="scss">
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.link {
  color: $default;
}
</style>
