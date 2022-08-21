<template>
  <PageWrapper class="py-5">
    <PageHeader class="pb-5">
      <PageTitle :text="$t('pages.post.title')" class="capitalize" />
    </PageHeader>
    <PageBody>
      <PageSection>
        <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-5">
          <template v-if="pending">
            <li v-for="n in 16" :key="n">
              <div role="status" class="animate-pulse p-6 max-full bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
                <div class="h-6 bg-gray-200 rounded-md dark:bg-gray-700 w-48 mb-4"></div>
                <div class="h-30 bg-gray-200 rounded-md dark:bg-gray-700 max-w-[360px] mb-2.5"></div>
                <div class="h-10 bg-gray-200 rounded-md dark:bg-gray-700 w-48 mb-4 mt-10"></div>
                <span class="sr-only">Loading...</span>
              </div>
            </li>
          </template>
          <template v-else>
            <li v-for="(post, i) in posts" :key="i">
              <div class="p-6 max-full bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
                <a href="#">
                  <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ post.title }}</h5>
                </a>
                <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ post.body }}</p>
                <a href="#" class="inline-flex items-center py-2 px-3 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                  Read more
                  <svg aria-hidden="true" class="ml-2 -mr-1 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                </a>
              </div>
            </li>
          </template>
        </ul>
      </PageSection>
    </PageBody>
  </PageWrapper>
</template>

<script lang="ts" setup>

definePageMeta({
  layout: 'page',
})
const {t} = useLang()
// Fetch data
const { pending,data: posts } = useLazyAsyncData('posts', () => $fetch('https://jsonplaceholder.typicode.com/posts'))
console.log('posts :', posts.value)
// watch(posts, (newPosts) => {
//   console.log('newPosts :', newPosts)
// })


</script>
