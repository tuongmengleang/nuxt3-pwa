<template>
  <div
    ref="navigationBottomBar"
    class="fixed bottom-0 w-full bg-white dark:bg-gray-900 md:hidden sm:block <sm:block rounded-t-xl z-20"
  >
    <ul class="flex flex-row items-center justify-around py-4">
      <li v-for="(item, i) in menus" :key="i" class="text-center">
        <NuxtLink
          :to="item.route ? item.route : undefined"
          class="navbar-mobile w-full text-gray-500 dark:text-gray-300 hover:text-black dark:hover:text-white text-sm capitalize"
        >
          <span class="mx-auto" v-html="item.icon"></span>

          {{ item.text }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
export interface IMenuItem {
  type: 'link' | 'button'
  text: string
  href?: any
  route?: any
  icon?: string
}

const { t } = useLang()
const menus = computed((): IMenuItem[] => [
  {
    type: 'link',
    text: t('pages.home.nav'),
    route: { name: 'index' },
    icon: '<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" /></svg>',
  },
  {
    type: 'link',
    text: t('pages.test.nav'),
    route: { name: 'test' },
    icon: '<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" /></svg>',
  },
  {
    type: 'link',
    text: t('pages.post.nav'),
    route: { name: 'post' },
    icon: '<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>',
  },
  {
    type: 'link',
    text: t('pages.setting.nav'),
    route: { name: 'setting' },
    icon: '<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" /><path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" /></svg>',
  },
  {
    type: 'link',
    text: t('pages.about.nav'),
    route: { name: 'about' },
    icon: '<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>',
  },
])
</script>

<style lang="scss" scoped>
.navbar-mobile.router-link-active {
  @apply font-semibold text-blue-500;
}
</style>
