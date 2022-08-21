<template>
  <div ref="navbar" class="navbar top-0 z-40 w-full">
    <div
      class="container w-full flex flex-row items-center justify-between px-5 py-3"
    >
      <!-- Logo App -->
      <NuxtLink to="/" class="logo flex items-center gap-3">
        <img src="/favicon.ico" alt="nuxt3 boilerplate"/>
        <h1 class="sm:hidden <sm:hidden md:block">{{ app.name }}</h1>
      </NuxtLink>
      <!-- Menu Navbar -->
      <ul class="navbar-menu sm:hidden <sm:hidden md:flex items-center">
        <li v-for="(item, i) in menus" :key="i">
          <NuxtLink
            :to="item.route ? item.route : undefined"
            class="inline-block w-full h-full px-5 py-2 text-gray-500 dark:text-gray-300 hover:text-black dark:hover:text-white capitalize"
          >
            {{ item.text }}
          </NuxtLink>
        </li>
      </ul>
      <!-- Actions Navbar -->
      <div class="flex items-center gap-3">
        <LanguageSwitcher />
        <ThemeSwitcher />
        <a
          href="https://github.com/tuongmengleang/nuxt3-boilerplate"
          target="_blank"
          class="w-10 h-10 rounded-full overflow-hidden"
        >
          <img
            class="w-full h-full"
            src="https://avatars.githubusercontent.com/u/56217606?v=4"
            alt=""
          />
        </a>
      </div>
    </div>
    <!-- Navigation BottomBar -->
    <ClientOnly>
      <Teleport to="#app-after">
        <Transition name="slide-fade-form-up hidden" mode="out-in">
          <PageMobileNavbar />
        </Transition>
      </Teleport>
    </ClientOnly>
  </div>
</template>

<script lang="ts" setup>
import { IApp } from '~/utils/app'
import { useSticky } from '~/composables/useSticky'
export interface IMenuItem {
  type: 'link' | 'button'
  text: string
  href?: any
  route?: any
}

const { t } = useLang()
const app = useState<IApp>('app')
const menus = computed((): IMenuItem[] => [
  { type: 'link', text: t('pages.home.nav'), route: { name: 'index' } },
  { type: 'link', text: t('pages.test.nav'), route: { name: 'test' } },
  { type: 'link', text: t('pages.post.nav'), route: { name: 'post' } },
  { type: 'link', text: t('pages.setting.nav'), route: { name: 'setting' } },
  { type: 'link', text: t('pages.about.nav'), route: { name: 'about' } },
])

const navbar = ref(null)

onMounted(() => {
  if (!navbar.value) return
  const { onScroll } = useSticky(navbar.value, 0)
  setTimeout(() => onScroll(), 50)
})
</script>

<style lang="scss" scoped>
.navbar-menu {
  li {
    a.router-link-active {
      @apply font-semibold text-blue-500;
    }
  }
}
</style>
