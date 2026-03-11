<template>
  <div class="min-h-screen flex flex-col">
    <AppNavbar />
    <main class="min-h-screen pt-20">
      <slot />
    </main>
    <AppFooter v-if="route.path !== '/chatrooms'" />
  </div>
</template>

<script setup lang="ts">
import { useRoute } from 'vue-router'

const route = useRoute()
</script>
