<template>
  <nav class="fixed top-0 w-full bg-white z-50 border-b border-gray-100 h-20 px-8 flex items-center justify-between">
    <!-- Logo -->
    <div class="font-bold text-primary text-2xl tracking-tighter">
      LBB
    </div>

    <!-- Navigation Links -->
    <div class="hidden md:flex items-center space-x-8 text-gray-600 font-medium">
      <NuxtLink to="/books" class="flex items-center space-x-2 hover:text-primary transition-colors cursor-pointer group">
        <IconBook class="w-5 h-5 text-gray-400 group-hover:text-primary transition-colors" />
        <span>Books</span>
      </NuxtLink>
      <NuxtLink to="/audiobooks" class="flex items-center space-x-2 hover:text-primary transition-colors cursor-pointer group">
        <IconHeadphones class="w-5 h-5 text-gray-400 group-hover:text-primary transition-colors" />
        <span>Audioboks</span>
      </NuxtLink>
      <NuxtLink to="/podcasts" class="flex items-center space-x-2 hover:text-primary transition-colors cursor-pointer group">
        <IconMicrophone class="w-5 h-5 text-gray-400 group-hover:text-primary transition-colors" />
        <span>Podcasts</span>
      </NuxtLink>
      <NuxtLink to="/chess" class="flex items-center space-x-2 hover:text-primary transition-colors cursor-pointer group">
        <IconChess class="w-5 h-5 text-gray-400 group-hover:text-primary transition-colors" />
        <span>Chess</span>
      </NuxtLink>
      <NuxtLink to="/articles" class="flex items-center space-x-2 hover:text-primary transition-colors cursor-pointer group">
        <IconFileText class="w-5 h-5 text-gray-400 group-hover:text-primary transition-colors" />
        <span>Articles</span>
      </NuxtLink>
    </div>

    <!-- Actions -->
    <div class="flex items-center space-x-4">
      <NuxtLink to="/login" class="text-gray-600 font-medium hover:text-primary transition-colors">Log In</NuxtLink>
      <button class="bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-6 py-2.5 rounded-full">
        Sign Up
      </button>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { IconBook, IconHeadphones, IconMicrophone, IconChess, IconFileText } from '@tabler/icons-vue'
</script>
