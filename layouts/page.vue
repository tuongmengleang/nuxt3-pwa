<template>
  <main id="main" class="main">
    <!-- App Before -->
    <slot name="app-before" />
    <div id="app-before"></div>

    <!-- App Content -->
    <div class="flex flex-col min-h-screen">
      <slot name="header">
        <PageNavbar />
      </slot>
      <div class="container flex-1 w-full h-full flex flex-col sm:pb-16 <sm:pb-16 md:pb-0">
        <div class="relative flex-1 flex flex-col mx-auto max-w-8xl w-full h-full">
          <slot />
        </div>
      </div>
      <slot name="footer">
        <PageFooter class="hidden md:block" />
      </slot>
    </div>

    <!-- App After -->
    <slot name="app-after" />
    <div id="app-after"></div>
  </main>
</template>
