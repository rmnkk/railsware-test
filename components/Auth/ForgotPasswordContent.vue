<template>
  <PageContentWrapper>
    <template #image>
      <img src="~assets/images/Forgot-password- illustration.svg" />
    </template>

    <template #title>Forgot Password</template>

    <template #form>
      <ForgotPasswordForm />
    </template>
  </PageContentWrapper>
</template>

<script>
import PageContentWrapper from '../Common/PageContentWrapper.vue'
import ForgotPasswordForm from './ForgotPasswordForm.vue'
export default {
  name: 'ForgotPasswordContent',
  components: { PageContentWrapper, ForgotPasswordForm },
}
</script>

<style lang="scss" scoped></style>
