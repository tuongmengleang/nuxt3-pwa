<template>
  <PageWrapper>
    <PageHeader>
      <PageTitle :text="$t('pages.test.title')" class="capitalize" />
    </PageHeader>
    <PageBody>
      <PageSection>
        <PageSectionTitle :text="$t('pages.test.counter')" class="capitalize" />
        <div>
          <div class="w-full py-5 @sm:text-center <sm:text-center text-lg font-semibold">Counter {{ counter.count }}</div>
          <div class="flex flex-col items-center justify-items-center space-y-4 md:space-y-0 md:flex-row md:space-x-4 <sm:px-10">
            <Button class="w-full md:w-auto capitalize" @click.prevent="counter.increment">
              {{ $t('pages.test.increment') }}
            </Button>
            <Button class="w-full md:w-auto capitalize" @click.prevent="counter.increment2x">
              {{ $t('pages.test.increment')  }} 2x
            </Button>
            <Button class="w-full md:w-auto capitalize" @click.prevent="counter.decrement">
              {{ $t('pages.test.decrement') }}
            </Button>
            <Button class="w-full md:w-auto capitalize" @click.prevent="counter.reset">
              {{ $t('pages.test.reset') }}
            </Button>
          </div>
        </div>
      </PageSection>
    </PageBody>
  </PageWrapper>
</template>

<script lang="ts" setup>
definePageMeta({
  layout: 'page',
})
import {useCounter} from "~/stores/counter";
const counter = useCounter()

const {t} = useLang()
useHead(() => ({
  title: t('pages.test.title'),
  meta: [
    {
      name: 'description',
      content: t('pages.test.description'),
    },
  ],
}))
</script>
