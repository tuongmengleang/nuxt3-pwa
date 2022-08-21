<script lang="ts" setup>
const props = defineProps({
  color: {
    type: String,
    default: '',
  },
  size: {
    type: String,
    default: '40',
  },
  circle: {
    type: Boolean,
    default: false,
  }
})

// state:styles
const defaultStyle = `
  w-10 h-10 rounded-full overflow-hidden transition-all}
`

// const avatarSize = computed(() => props.size + 'px')
const avatarSize = props.size + 'px'
</script>

<template>
  <div class="avatar" :class="`${defaultStyle}`">
    <slot />
  </div>
</template>

<style lang="scss" scoped>
.avatar {
  position: relative;
  width: v-bind(avatarSize);
  height: v-bind(avatarSize);
}
</style>
