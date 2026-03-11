<template>
  <div class="bg-gray-50 min-h-screen py-24">
    <div class="max-w-7xl mx-auto px-8">
      
      <!-- Community Banner -->
      <div class="bg-primary rounded-3xl p-8 mb-12 text-white flex flex-col md:flex-row items-center justify-between shadow-lg shadow-primary/30">
        <div>
          <h2 class="text-3xl font-bold mb-2">Join a team today</h2>
          <p class="text-primary-light">Start collaborating and reading alongside other enthusiastic members.</p>
        </div>
        <button class="mt-6 md:mt-0 bg-white text-primary hover:bg-gray-100 transition-colors px-8 py-3 rounded-full font-bold shadow-md">
          Find Teams
        </button>
      </div>

      <!-- Library Header and Filters -->
      <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-6">
        <div>
          <h1 class="text-4xl font-bold text-gray-900 mb-2">Bookshelves</h1>
          <p class="text-gray-500">Explore the complete library collection.</p>
        </div>
        
        <!-- Tabs -->
        <div class="flex space-x-2 bg-white p-1.5 rounded-2xl shadow-sm border border-gray-100 overflow-x-auto hide-scrollbar">
          <button 
            v-for="tab in tabs" 
            :key="tab"
            @click="activeTab = tab"
            :class="[
              'px-6 py-2 rounded-xl text-sm font-medium transition-colors whitespace-nowrap',
              activeTab === tab 
                ? 'bg-primary text-white shadow' 
                : 'text-gray-600 hover:bg-gray-50'
            ]"
          >
            {{ tab }}
          </button>
        </div>
      </div>

      <!-- Books Grid -->
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-x-6 gap-y-10">
        <div v-for="i in 10" :key="i" class="group cursor-pointer">
          <div class="aspect-[2/3] bg-gray-200 rounded-2xl mb-4 overflow-hidden shadow-sm group-hover:shadow-xl transition-all relative">
            <img :src="`https://images.unsplash.com/photo-${1512820790803 + i * 10}-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80`" 
                 alt="Book cover" 
                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
            <div class="absolute inset-0 bg-black/0 group-hover:bg-black/10 transition-colors duration-300"></div>
          </div>
          <h3 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">Creative Process {{ i }}</h3>
          <p class="text-gray-500 text-sm">Author Name</p>
          <div class="mt-2 text-xs font-bold text-primary bg-primary/10 inline-block px-2 py-1 rounded-md">
            {{ tabs[i % tabs.length] || 'Business' }}
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

useHead({
  title: 'Bookshelves - LeadByBooks'
})

const tabs = ['ALL', 'Business', 'Romance', 'Autobiography', 'Science', 'Fiction']
const activeTab = ref('ALL')
</script>

<style scoped>
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
