<template>
  <div>
    <div class="input-wrapper">
      <input
        class="input"
        :class="{
          'input_with-icon': withIcon,
        }"
        :value="value"
        :placeholder="placeholder"
        :type="isPasswordVisible ? 'text' : type"
        :autocomplete="autocomplete"
        @input="$emit('input', $event.target.value)"
      />

      <svg
        v-if="type === 'password' && !isPasswordVisible && value"
        class="password-icon"
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        @click="togglePasswordVisibility"
      >
        <g clip-path="url(#clip0_1746_23642)">
          <path
            d="M0.666687 7.99996C0.666687 7.99996 3.33335 2.66663 8.00002 2.66663C12.6667 2.66663 15.3334 7.99996 15.3334 7.99996C15.3334 7.99996 12.6667 13.3333 8.00002 13.3333C3.33335 13.3333 0.666687 7.99996 0.666687 7.99996Z"
            stroke="#8295AB"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M8 10C9.10457 10 10 9.10457 10 8C10 6.89543 9.10457 6 8 6C6.89543 6 6 6.89543 6 8C6 9.10457 6.89543 10 8 10Z"
            stroke="#8295AB"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </g>
        <defs>
          <clipPath id="clip0_1746_23642">
            <rect width="16" height="16" fill="white" />
          </clipPath>
        </defs>
      </svg>
      <svg
        v-else-if="type === 'password' && isPasswordVisible && value"
        class="password-icon"
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        @click="togglePasswordVisibility"
      >
        <g clip-path="url(#clip0_1746_23643)">
          <path
            d="M9.41335 9.41331C9.23025 9.60981 9.00945 9.76741 8.76412 9.87673C8.51879 9.98604 8.25395 10.0448 7.98541 10.0496C7.71687 10.0543 7.45013 10.0049 7.20109 9.9043C6.95206 9.80371 6.72583 9.654 6.53592 9.46408C6.346 9.27416 6.19628 9.04794 6.09569 8.7989C5.9951 8.54987 5.9457 8.28312 5.95044 8.01458C5.95518 7.74604 6.01396 7.48121 6.12327 7.23587C6.23258 6.99054 6.39019 6.76974 6.58669 6.58664M11.96 11.96C10.8204 12.8286 9.43276 13.3099 8.00002 13.3333C3.33335 13.3333 0.666687 7.99998 0.666687 7.99998C1.49595 6.45457 2.64611 5.10438 4.04002 4.03998L11.96 11.96ZM6.60002 2.82664C7.05891 2.71923 7.52873 2.66554 8.00002 2.66664C12.6667 2.66664 15.3334 7.99998 15.3334 7.99998C14.9287 8.75705 14.4461 9.4698 13.8934 10.1266L6.60002 2.82664Z"
            stroke="#8295AB"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M0.666687 0.666626L15.3334 15.3333"
            stroke="#8295AB"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </g>
        <defs>
          <clipPath id="clip0_1746_23643">
            <rect width="16" height="16" fill="white" />
          </clipPath>
        </defs>
      </svg>

      <slot name="prepend"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CustomInput',
  props: {
    value: {
      type: [String, Number],
      default: '',
    },
    placeholder: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text',
    },
    autocomplete: {
      type: Boolean,
      default: false,
    },
    withIcon: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      isPasswordVisible: false,
    }
  },
  methods: {
    togglePasswordVisibility() {
      this.isPasswordVisible = !this.isPasswordVisible
    },
  },
}
</script>

<style lang="scss" scoped>
.input-wrapper {
  position: relative;
  width: 100%;
}

.input {
  width: 100%;
  padding: 12px;
  outline: none;
  border: 1px solid $input-border-void;
  border-radius: 5px;
  font-size: 16px;
  color: $default;

  &_with-icon {
    padding-left: 45px;
  }

  &::placeholder {
    color: $text-placeholder;
  }

  &:hover {
    border-color: $input-border-hover;

    & ~ svg {
      filter: brightness(0) saturate(100%) invert(63%) sepia(29%) saturate(466%)
        hue-rotate(171deg) brightness(87%) contrast(85%);
    }
  }

  &:focus {
    border-color: $default;

    & ~ svg {
      filter: brightness(0) saturate(100%) invert(28%) sepia(13%)
        saturate(4755%) hue-rotate(181deg) brightness(88%) contrast(95%);
    }
  }
}

.password-icon {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}

svg {
  &.prepend {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
  }
}
</style>
