<template>
  <div class="min-h-screen flex">
    <!-- Left Pattern/Image Side -->
    <div class="hidden lg:flex lg:w-1/2 bg-primary relative overflow-hidden items-center justify-center">
      <!-- Decorative Background Elements -->
      <div class="absolute -top-32 -left-32 w-96 h-96 bg-white/10 rounded-full blur-3xl"></div>
      <div class="absolute -bottom-32 -right-32 w-96 h-96 bg-white/10 rounded-full blur-3xl"></div>
      
      <div class="z-10 p-16 text-white max-w-lg text-center">
        <div class="mb-12 flex justify-center">
          <div class="w-24 h-24 bg-white/20 backdrop-blur-sm rounded-3xl flex items-center justify-center p-6 shadow-2xl">
            <IconBooks class="w-full h-full text-white" />
          </div>
        </div>
        <h2 class="text-4xl font-bold mb-6 leading-tight">Join the ultimate reading community</h2>
        <p class="text-primary-light text-lg">Connect with thousands of active readers, share your thoughts, and discover your next favorite book.</p>
      </div>

      <!-- Connecting Lines Pattern -->
      <div class="absolute inset-0 opacity-20 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxwYXRoIGQ9Ik0zNiAzNHYtbGgxNXYtbDExem0tMTIgMHYtbGgtMTV2LWwxMXptMTIgMHYxbDE1djFsLTExem0tMTIgMHYxbC0xNXYxbDExeiIgZmlsbD0iI2ZmZmZmZiIvPjwvZz48L3N2Zz4=')]"></div>
    </div>

    <!-- Right Form Side -->
    <div class="w-full lg:w-1/2 flex items-center justify-center p-8 sm:p-12 lg:p-24 bg-white">
      <div class="w-full max-w-md">
        
        <div class="mb-10 lg:hidden">
          <div class="font-bold text-primary text-3xl tracking-tighter">LBB</div>
        </div>

        <h1 class="text-3xl font-bold text-gray-900 mb-2">Create an account</h1>
        <p class="text-gray-500 mb-8">Start your reading journey with LeadByBooks today.</p>

        <!-- Social Signup -->
        <div class="space-y-4 mb-8">
          <button class="w-full flex items-center justify-center space-x-3 border border-gray-200 hover:bg-gray-50 hover:border-gray-300 transition-all px-4 py-3.5 rounded-2xl text-gray-700 font-medium">
            <svg class="w-5 h-5" viewBox="0 0 24 24">
              <path d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z" fill="#4285F4"/>
              <path d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z" fill="#34A853"/>
              <path d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z" fill="#FBBC05"/>
              <path d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z" fill="#EA4335"/>
            </svg>
            <span>Sign up with Google</span>
          </button>
        </div>

        <div class="flex items-center mb-8">
          <div class="flex-1 border-t border-gray-200"></div>
          <span class="px-4 text-sm text-gray-400">or sign up with email</span>
          <div class="flex-1 border-t border-gray-200"></div>
        </div>

        <!-- Form -->
        <form @submit.prevent class="space-y-5">
          <div class="grid grid-cols-2 gap-4">
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1.5">First Name</label>
              <input type="text" placeholder="John" class="w-full px-4 py-3.5 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1.5">Last Name</label>
              <input type="text" placeholder="Doe" class="w-full px-4 py-3.5 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
            </div>
          </div>
          
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1.5">Email Address</label>
            <input type="email" placeholder="john@example.com" class="w-full px-4 py-3.5 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
          </div>
          
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1.5">Password</label>
            <input type="password" placeholder="••••••••" class="w-full px-4 py-3.5 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
            <p class="text-xs text-gray-500 mt-2">Must be at least 8 characters long.</p>
          </div>

          <button type="submit" class="w-full bg-primary hover:bg-primary-dark text-white font-medium py-4 rounded-xl shadow-lg shadow-primary/30 transition-all mt-4">
            Create Account
          </button>
        </form>

        <p class="mt-8 text-center text-gray-600 text-sm">
          Already have an account? 
          <NuxtLink to="/login" class="text-primary font-bold hover:underline">Log in here</NuxtLink>
        </p>

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconBooks } from '@tabler/icons-vue'

definePageMeta({
  layout: false // Hide default navbar/footer for auth pages
})

useHead({
  title: 'Sign Up - LeadByBooks'
})
</script>
