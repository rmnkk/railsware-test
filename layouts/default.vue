<template>
  <div class="container">
    <header class="header">
      <Nuxt-link to="/">
        <img src="~/assets/images/Logo-circle.png" class="header__image" />
      </Nuxt-link>

      <Nuxt-link class="header__link" to="/login">Log In</Nuxt-link>
    </header>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style scoped lang="scss">
.container {
  padding-top: 75px;
  min-height: 100vh;
}

.header {
  position: fixed;
  top: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 10px;
  background-color: $default;

  &__image {
    width: 150px;
  }

  &__link {
    color: $text-main;
    cursor: pointer;
  }
}
</style>
