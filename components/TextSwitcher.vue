<template>
  <div class="flex items-center gap-3 text-4xl md:text-6xl font-semibold">
    <h1 class="text-[#41b883]">Nuxt 3</h1>
    <h1 class="text"></h1>
  </div>
</template>

<script lang="ts" setup>
import Typed from 'typed.js';
onMounted(() => {
  setTimeout(() => {
    const typed = new Typed(".text", {
      strings: ["",
        "<span class='text-emerald-600'>Lighter</span>",
        "<span class='text-rose-600'>Faster</span>",
        "<span class='text-cyan-600'>Universal</span>",
        "<span class='text-red-600'>Awesome</span>"
      ],
      typeSpeed: 100,
      backSpeed: 40,
      loop: true
    })
  }, 500)
})
</script>

<style lang="scss" scoped>

</style>