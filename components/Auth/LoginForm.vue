<template>
  <form class="form" @submit.prevent="onSubmit">
    <CustomInput
      v-model="form.email"
      type="email"
      class="form__input"
      placeholder="email"
      autocomplete
    >
      <template #prepend>
        <svg
          width="26"
          height="26"
          viewBox="0 0 26 26"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="prepend"
        >
          <mask
            id="mask0_1_882"
            style="mask-type: alpha"
            maskUnits="userSpaceOnUse"
            x="0"
            y="0"
            width="26"
            height="26"
          >
            <rect
              x="0.0349731"
              y="0.5"
              width="25.0729"
              height="25"
              fill="white"
            />
          </mask>
          <g mask="url(#mask0_1_882)">
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M12.5714 3.625C9.55056 3.625 7.08673 6.08166 7.08673 9.09375C7.08673 10.9645 8.04165 12.6246 9.48628 13.6104C6.68272 14.8005 4.73615 17.5776 4.73615 20.8125H6.3032C6.3032 17.3243 9.07309 14.5625 12.5714 14.5625C16.0698 14.5625 18.8396 17.3243 18.8396 20.8125H20.4067C20.4067 17.5776 18.4601 14.8005 15.6566 13.6104C17.1012 12.6246 18.0561 10.9645 18.0561 9.09375C18.0561 6.08166 15.5923 3.625 12.5714 3.625ZM12.5714 5.1875C14.7445 5.1875 16.4891 6.927 16.4891 9.09375C16.4891 11.2605 14.7445 13 12.5714 13C10.3984 13 8.65379 11.2605 8.65379 9.09375C8.65379 6.927 10.3984 5.1875 12.5714 5.1875Z"
              fill="#AEAEAE"
            />
          </g>
        </svg>
      </template>
    </CustomInput>

    <CustomInput
      v-model="form.password"
      type="password"
      placeholder="password"
      autocomplete
    >
      <template #prepend>
        <svg
          width="26"
          height="26"
          viewBox="0 0 26 26"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="prepend"
        >
          <mask
            id="mask0_1_890"
            style="mask-type: alpha"
            maskUnits="userSpaceOnUse"
            x="0"
            y="0"
            width="26"
            height="26"
          >
            <rect
              x="0.0349731"
              y="0.5"
              width="25.0729"
              height="25"
              fill="white"
            />
          </mask>
          <g mask="url(#mask0_1_890)">
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M12.5714 2.84375C9.55974 2.84375 7.08673 5.30957 7.08673 8.3125V10.6562H4.73615V23.1562H20.4067V10.6562H18.0561V8.3125C18.0561 5.30957 15.5831 2.84375 12.5714 2.84375ZM12.5714 4.40625C14.7292 4.40625 16.4891 6.16101 16.4891 8.3125V10.6562H8.65379V8.3125C8.65379 6.16101 10.4137 4.40625 12.5714 4.40625ZM6.30321 12.2188H18.8396V21.5938H6.30321V12.2188Z"
              fill="#AEAEAE"
            />
          </g>
        </svg>
      </template>
    </CustomInput>

    <div class="form__link">
      <Nuxt-link to="/forgot-password">Forgot Password?</Nuxt-link>
    </div>

    <TheButton
      width="100%"
      border-radius="8px"
      font-size="16px"
      letter-spacing="-0.41px"
    >
      LOG IN
    </TheButton>

    <div class="form__divider">
      <span>Or connect with social</span>
    </div>

    <div class="form__social-buttons">
      <TheButton width="50%" border-radius="5px" font-size="16px">
        Facebook
      </TheButton>

      <TheButton
        variant="secondary"
        width="50%"
        border-radius="5px"
        font-size="16px"
      >
        Google
      </TheButton>
    </div>
  </form>
</template>

<script>
import CustomInput from '@/components/Inputs/CustomInput.vue'
import TheButton from '@/components/Common/TheButton.vue'
export default {
  name: 'LoginForm',
  components: { CustomInput, TheButton },
  data() {
    return {
      form: {
        email: '',
        password: '',
      },
    }
  },
  methods: {
    onSubmit() {
      console.log('submitted')
    },
  },
}
</script>

<style lang="scss" scoped>
.form {
  width: 100%;

  &__input {
    margin-bottom: 36px;
  }

  &__link {
    display: flex;
    justify-content: flex-end;
    margin-top: 10px;
    margin-bottom: 50px;

    a {
      color: $default;
    }
  }

  &__divider {
    display: flex;
    justify-content: center;
    margin-top: 50px;
    margin-bottom: 36px;

    span {
      color: $text-secondary;
    }
  }

  &__social-buttons {
    display: flex;

    button:first-child {
      margin-right: 14px;
    }
  }
}
</style>
