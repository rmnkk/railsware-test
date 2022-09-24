<template>
  <div class="content login">
    <div class="login__container">
      <img
        src="~/assets/images/Login-illustration.svg"
        alt="woman with phone in front of login form"
        class="login__item"
      />

      <TheTitle class="login__item"> Welcome Back!</TheTitle>

      <LoginForm />
    </div>
  </div>
</template>

<script>
import TheTitle from '~/components/Common/TheTitle.vue'
import LoginForm from '~/components/Auth/LoginForm.vue'
export default {
  name: 'LoginContent',
  components: { LoginForm, TheTitle },
}
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  justify-content: center;
}

.login {
  &__container {
    width: 100%;
    max-width: 344px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__item {
    margin-bottom: 36px;
  }
}
</style>
