<template>
  <div class="min-h-screen flex flex-row-reverse">
    <!-- Right Pattern/Image Side -->
    <div class="hidden lg:flex lg:w-1/2 bg-gray-50 relative overflow-hidden items-center justify-center border-l border-gray-100">
      <div class="relative w-full h-full p-20 flex items-center justify-center">
        <!-- Floating Image Collage simulating readers -->
        <div class="relative w-full max-w-lg aspect-square">
          <div class="absolute top-0 right-0 w-2/3 h-2/3 rounded-[3rem] overflow-hidden shadow-2xl z-20 hover:-translate-y-2 transition-transform duration-500">
             <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Readers" class="w-full h-full object-cover">
          </div>
          <div class="absolute bottom-0 left-0 w-1/2 h-1/2 rounded-[2rem] overflow-hidden shadow-xl z-30 border-4 border-white hover:-translate-y-2 transition-transform duration-500">
             <img src="https://images.unsplash.com/photo-1517486808906-6ca8b3f04846?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Discussion" class="w-full h-full object-cover">
          </div>
          <!-- Purple Accent Blob -->
          <div class="absolute top-1/4 left-1/4 w-32 h-32 bg-primary/20 rounded-full blur-2xl -z-10"></div>
        </div>
      </div>
    </div>

    <!-- Left Form Side -->
    <div class="w-full lg:w-1/2 flex items-center justify-center p-8 sm:p-12 lg:p-24 bg-white relative">
      
      <!-- Back button -->
      <NuxtLink to="/" class="absolute top-8 left-8 text-gray-400 hover:text-primary transition-colors flex items-center space-x-2">
        <IconArrowLeft class="w-5 h-5" />
        <span class="font-medium">Back to Home</span>
      </NuxtLink>

      <div class="w-full max-w-md mt-12 lg:mt-0">
        <h1 class="text-4xl font-bold text-gray-900 mb-2">Welcome back</h1>
        <p class="text-gray-500 mb-10 text-lg">Please enter your details to sign in.</p>

        <!-- Social Login -->
        <div class="space-y-4 mb-8">
          <button class="w-full flex items-center justify-center space-x-3 border border-gray-200 hover:bg-gray-50 hover:border-gray-300 transition-all px-4 py-3.5 rounded-2xl text-gray-700 font-medium">
            <svg class="w-5 h-5" viewBox="0 0 24 24">
              <path d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z" fill="#4285F4"/>
              <path d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z" fill="#34A853"/>
              <path d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z" fill="#FBBC05"/>
              <path d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z" fill="#EA4335"/>
            </svg>
            <span>Log in with Google</span>
          </button>
        </div>

        <div class="flex items-center mb-8">
          <div class="flex-1 border-t border-gray-200"></div>
          <span class="px-4 text-sm text-gray-400">or</span>
          <div class="flex-1 border-t border-gray-200"></div>
        </div>

        <!-- Form -->
        <form @submit.prevent class="space-y-5">
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1.5">Email</label>
            <input type="email" placeholder="Enter your email" class="w-full px-4 py-4 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
          </div>
          
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1.5">Password</label>
            <input type="password" placeholder="••••••••" class="w-full px-4 py-4 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-all bg-gray-50 focus:bg-white" />
          </div>

          <div class="flex items-center justify-between mt-4">
            <label class="flex items-center space-x-2 cursor-pointer group">
              <input type="checkbox" class="w-4 h-4 rounded border-gray-300 text-primary focus:ring-primary/20 cursor-pointer" />
              <span class="text-sm text-gray-600 group-hover:text-gray-900 transition-colors">Remember me for 30 days</span>
            </label>
            <a href="#" class="text-sm text-primary font-semibold hover:underline">Forgot password?</a>
          </div>

          <button type="submit" class="w-full bg-primary hover:bg-primary-dark text-white font-medium py-4 rounded-xl shadow-lg shadow-primary/30 transition-all mt-8 text-lg">
            Log In
          </button>
        </form>

        <p class="mt-8 text-center text-gray-600 text-sm">
          Don't have an account? 
          <NuxtLink to="/signup" class="text-primary font-bold hover:underline">Sign up for free</NuxtLink>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconArrowLeft } from '@tabler/icons-vue'

definePageMeta({
  layout: false // Hide default navbar/footer
})

useHead({
  title: 'Log In - LeadByBooks'
})
</script>
