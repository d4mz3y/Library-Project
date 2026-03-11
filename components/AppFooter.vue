<template>
  <footer class="bg-white border-t border-gray-100 pt-16 pb-8">
    <div class="max-w-7xl mx-auto px-8 grid grid-cols-1 md:grid-cols-4 gap-8 mb-12">
      <!-- Logo column -->
      <div>
        <div class="font-bold text-primary text-2xl tracking-tighter mb-6">
          LBB
        </div>
        <div class="flex space-x-4">
          <a href="#" class="text-gray-400 hover:text-primary transition-colors">
            <IconBrandInstagram class="w-6 h-6" />
          </a>
          <a href="#" class="text-gray-400 hover:text-primary transition-colors">
            <IconBrandTwitter class="w-6 h-6" />
          </a>
          <a href="#" class="text-gray-400 hover:text-primary transition-colors">
            <IconBrandLinkedin class="w-6 h-6" />
          </a>
        </div>
      </div>

      <!-- Links Column 1 -->
        <div>
          <h4 class="font-bold text-gray-900 mb-4">Company</h4>
          <ul class="space-y-3">
            <li><NuxtLink to="/about" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">About Us</NuxtLink></li>
            <li><NuxtLink to="/contact" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">Contact Us</NuxtLink></li>
          </ul>
        </div>

        <!-- Support -->
        <div>
          <h4 class="font-bold text-gray-900 mb-4">Support</h4>
          <ul class="space-y-3">
            <li><NuxtLink to="/faq" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">FAQs</NuxtLink></li>
            <li><NuxtLink to="/contact" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">Help Center</NuxtLink></li>
          </ul>
        </div>

        <!-- Legal -->
        <div>
          <h4 class="font-bold text-gray-900 mb-4">Legal</h4>
          <ul class="space-y-3">
            <li><NuxtLink to="/terms" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">Terms of Service</NuxtLink></li>
            <li><NuxtLink to="/privacy" class="text-gray-500 hover:text-primary transition-colors cursor-pointer">Privacy Policy</NuxtLink></li>
          </ul>
        </div>
    </div>
    <div class="max-w-7xl mx-auto px-8 text-center text-gray-400 text-sm">
      &copy; {{ new Date().getFullYear() }} LBB. All rights reserved.
    </div>
  </footer>
</template>

<script setup lang="ts">
import { IconBrandInstagram, IconBrandTwitter, IconBrandLinkedin } from '@tabler/icons-vue'
</script>
