<template>
  <div class="wrapper container mt-5 flex items-center justify-center flex-1">
<!--    <div class="circle-1 w-20 h-20 absolute top-30 left-30 rounded-full bg-gradient-to-r from-yellow-200 to-amber-400"></div>-->
<!--    <div class="circle-2 w-30 h-30 absolute bottom-30 right-30 <sm:bottom-10 <sm:right-70 rounded-full bg-gradient-to-r from-red-200 to-pink-400"></div>-->
<!--    <div class="circle-3 w-20 h-20 absolute top-50 right-80 <sm:top-20 <sm:right-10 bg-gradient-to-r from-cyan-500 to-blue-500" style="border-radius: 30% 70% 67% 33% / 45% 56% 44% 55%"></div>-->
<!--    <div class="circle-4 w-20 h-20 absolute bottom-50 <sm:bottom-40 left-2/3 bg-gradient-to-r from-purple-200 to-violet-500" style="border-radius: 57% 43% 51% 49% / 46% 27% 73% 54%"></div>-->

    <div class="w-full">
      <div class="relative flex items-center justify-center">
        <TextSwitcher/>
      </div>
      <div class="flex items-center justify-center gap-5 mt-5">
        <Anchor
            href="https://v3.nuxtjs.org/"
            title="Github"
        >
          <Button>
            <IconLogos:nuxt-icon class="w-5 h-5 mr-2"/>
            Nuxt 3
          </Button>
        </Anchor>
        <Anchor
            href="https://github.com/tuongmengleang/nuxt3-boilerplate"
            title="Github"
        >
          <Button color="secondary">
            <IconLogos:github-icon class="w-5 h-5 mr-2"/>
            Github
          </Button>
        </Anchor>

      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

definePageMeta({
  layout: 'page',
})

const features: [string, string, string, string] = [
    "Lighter ⚡",
    "Faster 💨",
    "Universal 🪐",
    "Awesome 🔥"
]

</script>

<style lang="scss" scoped>

</style>
