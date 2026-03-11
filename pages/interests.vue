<template>
  <div class="bg-white min-h-screen py-24">
    <div class="max-w-7xl mx-auto px-8">
      
      <!-- Interests Grid -->
      <section class="mb-20">
        <h1 class="text-4xl font-bold text-gray-900 mb-4">Select your Interests</h1>
        <p class="text-gray-600 mb-8 max-w-2xl">
          Choose topics you're passionate about to discover the perfect reading groups and book recommendations.
        </p>
        
        <div class="flex flex-wrap gap-4">
          <button 
            v-for="interest in interests" 
            :key="interest.name"
            @click="interest.selected = !interest.selected"
            :class="[
              'px-6 py-3 rounded-xl font-medium transition-all duration-300 border-2',
              interest.selected 
                ? 'bg-primary border-primary text-white shadow-md shadow-primary/20 scale-105' 
                : 'bg-white border-gray-200 text-gray-600 hover:border-primary hover:text-primary'
            ]"
          >
            {{ interest.name }}
          </button>
        </div>
      </section>

      <!-- Chatrooms Section -->
      <section>
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-3xl font-bold text-gray-900">Join Chatroom</h2>
          <button class="text-primary font-medium hover:underline">View All</button>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <!-- Chatroom Card 1 -->
          <div class="bg-white border border-gray-100 rounded-[2rem] p-6 shadow-xl shadow-gray-200/50 hover:-translate-y-2 transition-transform duration-300">
            <div class="h-48 rounded-2xl mb-6 overflow-hidden relative">
              <img src="https://images.unsplash.com/photo-1532094349884-543bc11b234d?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Science Room" class="w-full h-full object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
              <div class="absolute bottom-4 left-4 text-white">
                <span class="bg-primary/90 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-wider">Active</span>
              </div>
            </div>
            <h3 class="text-2xl font-bold text-gray-900 mb-2">Science Explorer</h3>
            <p class="text-gray-500 mb-6 line-clamp-2">Dive into discussions on quantum mechanics, biology, and space exploration.</p>
            <div class="flex items-center justify-between">
              <div class="flex -space-x-2">
                <div class="w-8 h-8 rounded-full bg-gray-200 border-2 border-white"></div>
                <div class="w-8 h-8 rounded-full bg-gray-300 border-2 border-white"></div>
                <div class="w-8 h-8 rounded-full bg-gray-400 border-2 border-white flex items-center justify-center text-xs text-white font-medium">+12</div>
              </div>
              <button class="bg-primary/10 text-primary hover:bg-primary hover:text-white transition-colors px-6 py-2.5 rounded-full font-medium">
                Join Now
              </button>
            </div>
          </div>

          <!-- Chatroom Card 2 -->
          <div class="bg-white border border-gray-100 rounded-[2rem] p-6 shadow-xl shadow-gray-200/50 hover:-translate-y-2 transition-transform duration-300">
            <div class="h-48 rounded-2xl mb-6 overflow-hidden relative">
              <img src="https://images.unsplash.com/photo-1474932430478-367d16b99231?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Literature Room" class="w-full h-full object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
              <div class="absolute bottom-4 left-4 text-white">
                <span class="bg-primary/90 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-wider">Trending</span>
              </div>
            </div>
            <h3 class="text-2xl font-bold text-gray-900 mb-2">Classic Literature</h3>
            <p class="text-gray-500 mb-6 line-clamp-2">Discussing timeless masterpieces from Shakespeare to Dostoevsky.</p>
            <div class="flex items-center justify-between">
              <div class="flex -space-x-2">
                <div class="w-8 h-8 rounded-full bg-gray-200 border-2 border-white"></div>
                <div class="w-8 h-8 rounded-full bg-gray-300 border-2 border-white"></div>
                <div class="w-8 h-8 rounded-full bg-gray-400 border-2 border-white flex items-center justify-center text-xs text-white font-medium">+40</div>
              </div>
              <button class="bg-primary/10 text-primary hover:bg-primary hover:text-white transition-colors px-6 py-2.5 rounded-full font-medium">
                Join Now
              </button>
            </div>
          </div>

           <!-- Chatroom Card 3 -->
           <div class="bg-white border border-gray-100 rounded-[2rem] p-6 shadow-xl shadow-gray-200/50 hover:-translate-y-2 transition-transform duration-300">
            <div class="h-48 rounded-2xl mb-6 overflow-hidden relative">
              <img src="https://images.unsplash.com/photo-1461360370896-922624d12aa1?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="History Room" class="w-full h-full object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
            </div>
            <h3 class="text-2xl font-bold text-gray-900 mb-2">World History</h3>
            <p class="text-gray-500 mb-6 line-clamp-2">Uncovering the events that shaped our modern world across all continents.</p>
            <div class="flex items-center justify-between">
              <div class="flex -space-x-2">
                <div class="w-8 h-8 rounded-full bg-gray-200 border-2 border-white"></div>
                <div class="w-8 h-8 rounded-full bg-gray-300 border-2 border-white"></div>
              </div>
              <button class="bg-primary/10 text-primary hover:bg-primary hover:text-white transition-colors px-6 py-2.5 rounded-full font-medium">
                Join Now
              </button>
            </div>
          </div>

        </div>
      </section>

    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

useHead({
  title: 'Select Interests - LeadByBooks'
})

const interests = ref([
  { name: 'Career', selected: false },
  { name: 'Growth', selected: false },
  { name: 'Business', selected: false },
  { name: 'Art', selected: false },
  { name: 'Politics', selected: false },
  { name: 'Sports', selected: false },
  { name: 'Travel', selected: false },
  { name: 'Crime', selected: false },
  { name: 'Fiction', selected: false },
  { name: 'History', selected: true },
  { name: 'Science', selected: false },
  { name: 'Technology', selected: false },
  { name: 'Lifestyle', selected: false },
])
</script>
