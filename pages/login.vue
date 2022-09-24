<template>
  <LoginContent />
</template>

<script>
import LoginContent from '~/components/Auth/LoginContent.vue'
export default {
  name: 'LoginPage',
  components: { LoginContent },
  data() {
    return {
      email: '',
      password: '',
    }
  },
}
</script>

<style lang="scss" scoped></style>
