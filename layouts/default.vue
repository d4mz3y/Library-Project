<template>
  <div class="min-h-screen flex flex-col pt-20">
    <AppNavbar />
    <main class="flex-grow">
      <slot />
    </main>
    <AppFooter />
  </div>
</template>

<script setup lang="ts">
// Default layout
</script>
