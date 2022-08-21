<script lang="ts" setup>
const props = defineProps({
  type: {
    type: String,
    default: 'button',
  },
  form: {
    type: String,
    default: '',
  },
  color: {
    type: String,
    default: 'primary',
  },
  size: {
    type: String,
    default: 'md',
  },
  loading: {
    type: Boolean,
    default: false,
  },
})

// state:styles
const defaultStyle = `
  relative box-border relative inline-flex items-center justify-center w-auto overflow-hidden font-bold text-white transition-all duration-300 rounded-md cursor-pointer group ring-offset-2 ring-1 ease focus:outline-none
`
const styles = reactive<{
  [key: string]: string
}>({
  primary:
    'text-white bg-[#41b883] hover:bg-green-500 border-green-500 ring-green-300 ring-offset-green-200 hover:ring-offset-green-500',
  secondary:
    'text-gray-600 bg-gray-300 hover:bg-gray-200 border-gray-200 ring-gray-200 ring-offset-gray-200 hover:ring-offset-gray-200',
  danger:
    'text-white bg-red-600 hover:bg-red-500 border-red-500 ring-red-300 ring-offset-red-200 hover:ring-offset-red-500',
})

const sizes = reactive<{
  [key: string]: string
}>({
  lg: 'h-12 px-8 text-lg',
  md: 'h-10 px-6 text-base',
  sm: 'h-8 px-4 text-sm',
  xs: 'h-6 px-3 text-xs',
})

const selectedStyle = computed(() => styles[props.color] || styles.primary)
const selectedSize = computed(() => sizes[props.size] || sizes.lg)

</script>

<template>
  <button
    :type="`${props.type}`"
    :form="props.form"
    :class="`${defaultStyle} ${selectedStyle} ${selectedSize}`"
    :disabled="props.loading"
    :title="props.loading ? 'Loading' : ''"
  >
    <span
      class="absolute bottom-0 right-0 w-8 h-20 -mb-8 -mr-5 transition-all duration-300 ease-out transform rotate-45 translate-x-1 bg-white opacity-10 group-hover:translate-x-0"
    ></span>
    <span
      class="absolute top-0 left-0 w-20 h-8 -mt-1 -ml-12 transition-all duration-300 ease-out transform -rotate-45 -translate-x-1 bg-white opacity-10 group-hover:translate-x-0"
    ></span>
    <span v-if="!props.loading" class="relative z-20 flex items-center text-sm">
      <slot />
    </span>
    <span v-else class="spinner">
      <span class="dot"></span>
      <span class="dot"></span>
      <span class="dot"></span>
      <span class="dot"></span>
      <span class="dot"></span>
    </span>
  </button>
</template>

<style lang="scss" scoped>
.spinner {
  width: 25px;
  height: 25px;
  position: relative;
  .dot {
    position: absolute;
    inset: 0;

    display: flex;
    align-items: flex-end;
    justify-content: center;
    animation: spin 2s infinite;

    &:nth-child(2) {
      animation-delay: 100ms;
    }
    &:nth-child(3) {
      animation-delay: 200ms;
    }
    &:nth-child(4) {
      animation-delay: 300ms;
    }
    &:nth-child(5) {
      animation-delay: 400ms;
    }

    &::after {
      content: '';
      width: 3px;
      height: 3px;
      border-radius: 2px;
      @apply bg-blue-200;
    }
  }
}
@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
