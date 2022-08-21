<template>
  <PageWrapper class="flex flex-col justify-center items-center">
    <PageHeader>
      <PageTitle :text="$t('pages.about.title')" class="capitalize" />
    </PageHeader>
    <PageBody>
      <div class="flex flex-col items-center">
        <Avatar size="100" history>
          <img src="https://avatars.githubusercontent.com/u/56217606?v=4" class="inline-block rounded-full" alt="tuongmengleang"/>
        </Avatar>
        <a href="https://github.com/tuongmengleang">
          <Button size="sm" color="secondary" class="font-extrabold mt-4">
            Tuong Mengleang (@tuongmengleang)
          </Button>
        </a>
      </div>
    </PageBody>
  </PageWrapper>
</template>

<script lang="ts" setup>
definePageMeta({
  layout: 'page',
})
</script>
