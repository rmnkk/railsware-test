<template>
  <button
    class="button"
    :class="{
      button_style_primary: primary,
      button_style_secondary: secondary,
    }"
    :style="{
      width,
      maxWidth,
      padding,
      fontSize,
      fontWeight,
      letterSpacing,
      color,
      backgroundColor,
      borderRadius,
    }"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'TheButton',
  props: {
    variant: {
      type: String,
      default: 'primary',
    },
    width: {
      type: String,
      default: null,
    },
    maxWidth: {
      type: String,
      default: null,
    },
    padding: {
      type: String,
      default: null,
    },
    fontSize: {
      type: String,
      default: null,
    },
    fontWeight: {
      type: String,
      default: null,
    },
    letterSpacing: {
      type: String,
      default: null,
    },
    color: {
      type: String,
      default: null,
    },
    backgroundColor: {
      type: String,
      default: null,
    },
    borderRadius: {
      type: String,
      default: null,
    },
  },
  computed: {
    primary() {
      return this.variant === 'primary'
    },
    secondary() {
      return this.variant === 'secondary'
    },
  },
}
</script>

<style lang="scss" scoped>
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: auto;
  padding: 15px;
  color: $text-main;
  cursor: pointer;

  &_style_primary {
    background-color: $default;

    &:hover {
      background-color: $button-primary-hover;
    }

    &:active {
      background-color: $button-primary-active;
    }
  }

  &_style_secondary {
    background-color: $accent;

    &:hover {
      background-color: $button-secondary-hover;
    }

    &:active {
      background-color: $button-secondary-active;
    }
  }
}
</style>
