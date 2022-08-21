<template>
  <PageWrapper>
    <PageHeader>
      <PageTitle :text="$t('pages.setting.title')" class="capitalize" />
    </PageHeader>
    <PageBody class="py-4">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-5">
        <div class="col-span-1 lg:col-span-4 shadow-xl rounded-lg">
          <div class="relative w-full h-40">
            <img class="w-full h-full rounded-t-lg" src="https://wallpapercave.com/wp/wp5848920.png" alt="">
            <div class="absolute -bottom-8 left-1/2 transform -translate-x-1/2 p-1 rounded-full">
              <Avatar size="100">
                <img src="https://avatars.githubusercontent.com/u/56217606?v=4" class="inline-block rounded-full" alt="tuongmengleang"/>
              </Avatar>
            </div>
          </div>
          <div class="w-full p-5 mt-5 text-center">
            <h1 class="text-xl font-bold text-blue-600">Tuong Mengleang</h1>
            <span class="text-md font-normal text-gray-400">Full-Stack developer</span>
          </div>
        </div>
        <div class="col-span-1 lg:col-span-8 shadow-xl rounded-lg">
          <div class="w-full p-5 bg-transparent">
            <h1 class="text-xl font-bold text-gray-600 dark:text-gray-200">Account</h1>
            <form class="py-5">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-10">

                <div class="form-group -mt-5">
                  <label class="label">
                    <span class="label-text dark:text-gray-200">First name</span>
                  </label>
                  <FormInput type="text" v-model="firstName" placeholder="Tuong" class="input w-full bg-gray-100 dark:bg-gray-700" />
                </div>

                <div class="form-group -mt-5">
                  <label class="label">
                    <span class="label-text dark:text-gray-200">Last name</span>
                  </label>
                  <FormInput type="text" v-model="lastName" placeholder="Mengleang" class="input w-full bg-gray-100 dark:bg-gray-700" />
                </div>

                <div class="form-group -mt-5">
                  <label class="label">
                    <span class="label-text dark:text-gray-200">Email address</span>
                  </label>
                  <FormInput type="text" v-model="email" placeholder="leang.dev@gmail" class="input w-full bg-gray-100 dark:bg-gray-700" />
                </div>

                <div class="form-group -mt-5">
                  <label class="label">
                    <span class="label-text dark:text-gray-200">Phone number</span>
                  </label>
                  <FormInput type="text" v-model="phone" placeholder="(+855) 968 255 313" class="input w-full bg-gray-100 dark:bg-gray-700" />
                </div>

              </div>

              <div class="flex items-center mt-5">
                <Button class="ml-auto">
                  <span>Save</span>
                </Button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </PageBody>
  </PageWrapper>
</template>

<script lang="ts" setup>
definePageMeta({
  layout: 'page',
})

const firstName = ref('Tuong')
const lastName = ref('Mengleang')
const email = ref('leang.dev@gmail.com')
const phone = ref('(+855) 968 255 313')
</script>
