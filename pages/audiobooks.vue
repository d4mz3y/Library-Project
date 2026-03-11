<template>
  <div class="max-w-7xl mx-auto py-12 px-8">
    <div class="mb-12 flex flex-col md:flex-row md:items-end justify-between gap-6 relative">
      <div>
        <h1 class="text-4xl font-bold text-gray-900 mb-2 font-serif tracking-tight">Audiobooks Library</h1>
        <p class="text-gray-500 text-lg">Listen to the world's greatest thinkers on the go.</p>
      </div>
      
      <!-- Search and Filter (Mock) -->
      <div class="flex gap-4 w-full md:w-auto">
        <div class="relative w-full md:w-64">
           <input type="text" placeholder="Search audiobooks..." class="w-full bg-gray-50 border border-gray-200 rounded-full py-2.5 pl-10 pr-4 focus:outline-none focus:ring-2 focus:ring-primary/20">
           <IconSearch class="w-5 h-5 text-gray-400 absolute left-3.5 top-3" />
        </div>
      </div>
    </div>

    <!-- Featured Audiobook Banner -->
    <div class="bg-gray-900 rounded-3xl p-8 md:p-12 text-white mb-16 relative overflow-hidden flex flex-col md:flex-row items-center gap-10 shadow-2xl">
       <div class="absolute inset-0 bg-primary/20 bg-[url('https://images.unsplash.com/photo-1516280440502-8f15b4ebf55c?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80')] bg-cover bg-center mix-blend-overlay opacity-30"></div>
       <div class="z-10 w-48 h-48 md:w-64 md:h-64 flex-shrink-0 bg-gray-800 rounded-2xl overflow-hidden shadow-2xl border-4 border-white/10">
          <img src="https://books.google.com/books/content?id=ZuHTvQEACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api" alt="Thinking Fast and Slow" class="w-full h-full object-cover">
       </div>
       <div class="z-10 flex-1">
          <div class="bg-white/20 backdrop-blur-md text-xs font-bold px-3 py-1 rounded-full inline-block mb-4 uppercase tracking-wider">Featured Release</div>
          <h2 class="text-3xl md:text-5xl font-bold mb-4 leading-tight">Thinking, Fast and Slow</h2>
          <p class="text-gray-300 text-lg mb-6">Narrated by Patrick Egan. The international bestseller that changes the way you think about thinking.</p>
          <div class="flex items-center gap-4">
            <button class="bg-primary hover:bg-primary-light transition-colors text-white font-bold py-3 px-8 rounded-full flex items-center gap-2">
              <IconPlayerPlay class="w-5 h-5" />
              Listen Now (14h 55m)
            </button>
          </div>
       </div>
    </div>

    <!-- Collection Grid -->
    <h3 class="text-2xl font-bold text-gray-900 mb-6">Trending This Week</h3>
    <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-x-6 gap-y-10">
      <div v-for="(book, index) in audiobooks" :key="index" class="group cursor-pointer">
        <div class="aspect-square bg-gray-200 rounded-2xl mb-4 overflow-hidden shadow-sm group-hover:shadow-xl transition-all relative">
          <img :src="book.image" :alt="book.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          <div class="absolute inset-0 bg-black/0 group-hover:bg-black/40 transition-colors duration-300 flex items-center justify-center">
             <div class="w-12 h-12 bg-white rounded-full flex items-center justify-center text-primary opacity-0 group-hover:opacity-100 transform scale-50 group-hover:scale-100 transition-all duration-300 shadow-xl">
               <IconPlayerPlay class="w-6 h-6 ml-1" />
             </div>
          </div>
          <!-- Duration Badge -->
          <div class="absolute bottom-3 right-3 bg-black/70 backdrop-blur-md text-white text-xs font-bold px-2 py-1 rounded-md">
            {{ book.duration }}
          </div>
        </div>
        <h3 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">{{ book.title }}</h3>
        <p class="text-gray-500 text-sm line-clamp-1 mb-2">By {{ book.author }}</p>
        <p class="text-gray-400 text-xs flex items-center gap-1">
          <IconMicrophone class="w-3.5 h-3.5" />
          {{ book.narrator }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconSearch, IconPlayerPlay, IconMicrophone } from '@tabler/icons-vue'

useHead({
  title: 'Audiobooks - LeadByBooks'
})

const audiobooks = [
  { title: "The Intelligent Investor", author: "Benjamin Graham", narrator: "Bill McGowan", duration: "17h 48m", image: "https://books.google.com/books/content?id=-NdcCSt8t_YC&printsec=frontcover&img=1&zoom=0&source=gbs_api" },
  { title: "Atomic Habits", author: "James Clear", narrator: "James Clear", duration: "5h 35m", image: "https://images.unsplash.com/photo-1589829085413-56de8ae18c73?auto=format&fit=crop&w=400&q=80" },
  { title: "Sapiens", author: "Yuval Noah Harari", narrator: "Derek Perkins", duration: "15h 17m", image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?auto=format&fit=crop&w=400&q=80" },
  { title: "Steve Jobs", author: "Walter Isaacson", narrator: "Dylan Baker", duration: "25h 11m", image: "https://books.google.com/books/publisher/content?id=8U2oAAAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&imgtk=AFLRE710Y48B5iV4C2-fN2mO4lH1W2u0J-qW7q2V6mRkYtG8Y_L2o3r10oK6-6_x9p85xXl0m7yP8l4n_G87C-Z8_U9n3-M6d32-vL1wT02jV4s4rW5j7T3qL2k_v3E10u2l_1-m7-O4X&source=gbs_api" },
  { title: "Zero to One", author: "Peter Thiel", narrator: "Blake Griffin", duration: "4h 49m", image: "https://books.google.com/books/publisher/content?id=YQ1xAwAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&imgtk=AFLRE70H5F8L02-kR6I48y98xG9Q8zN0M_-W8O0I01oF7q_uL8V4Y4k92e8W_49C4_kC-_sK_nK0Iq-x0M_7cZ_D1o9q-t-_3lQ0nO8Q9T8wV_-B4j7w_1D-_X_36wKV3W5p-29hH2-p_1_2q120s110A&source=gbs_api" },
  { title: "Dune", author: "Frank Herbert", narrator: "Scott Brick, et al.", duration: "21h 2m", image: "https://books.google.com/books/content?id=B1hSG45JCX4C&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api" },
  { title: "A Brief History of Time", author: "Stephen Hawking", narrator: "John Sackville", duration: "5h 44m", image: "https://books.google.com/books/content?id=-P24CgAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api" },
  { title: "The Making of a Manager", author: "Julie Zhuo", narrator: "Julie Zhuo", duration: "6h 15m", image: "https://books.google.com/books/content?id=malkEQAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api" },
  { title: "Find Your People", author: "Jennie Allen", narrator: "Jennie Allen", duration: "7h 1m", image: "https://books.google.com/books/content?id=7dv2zgEACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api" },
  { title: "Just Tyrus", author: "Tyrus", narrator: "Tyrus", duration: "8h 12m", image: "https://books.google.com/books/content?id=kRtdEAAAQBAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api" },
]
</script>
