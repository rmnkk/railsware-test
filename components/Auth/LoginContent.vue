<template>
  <PageContentWrapper>
    <template #image>
      <img
        src="~/assets/images/Login-illustration.svg"
        alt="woman with phone in front of login form"
        class="login__item"
      />
    </template>

    <template #title> Welcome Back! </template>

    <template #form>
      <LoginForm />
    </template>
  </PageContentWrapper>
</template>

<script>
import PageContentWrapper from '~/components/Common/PageContentWrapper.vue'
import LoginForm from '~/components/Auth/LoginForm.vue'
export default {
  name: 'LoginContent',
  components: { LoginForm, PageContentWrapper },
}
</script>

<style lang="scss" scoped></style>
