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
        <div v-for="book in filteredBooks" :key="book.title" class="group cursor-pointer">
          <div class="aspect-[2/3] bg-gray-200 rounded-2xl mb-4 overflow-hidden shadow-sm group-hover:shadow-xl transition-all relative">
            <img :src="book.image" 
                 :alt="book.title" 
                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
            <div class="absolute inset-0 bg-black/0 group-hover:bg-black/10 transition-colors duration-300"></div>
          </div>
          <h3 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">{{ book.title }}</h3>
          <p class="text-gray-500 text-sm">{{ book.author }}</p>
          <div class="mt-2 text-xs font-bold text-primary bg-primary/10 inline-block px-2 py-1 rounded-md">
            {{ book.category }}
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

useHead({
  title: 'Bookshelves - LeadByBooks'
})

const tabs = ['ALL', 'Business', 'Romance', 'Autobiography', 'Science', 'Fiction']
const activeTab = ref('ALL')

const libraryBooks = [
  // Original Figma Extracts
  { title: "The Intelligent Investor", author: "Benjamin Graham", image: "https://books.google.com/books/content?id=-NdcCSt8t_YC&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Business" },
  { title: "This Is the Story of a Happy Marriage", author: "Ann Patchett", image: "https://books.google.com/books/content?id=efE_AQAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Romance" },
  { title: "Just Tyrus", author: "Tyrus", image: "https://books.google.com/books/content?id=kRtdEAAAQBAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Autobiography" },
  { title: "Under the Banner of Heaven", author: "Jon Krakauer", image: "https://books.google.com/books/content?id=c_8DHAAACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Science" }, /* Changed to Science for demonstration */
  { title: "Stop Chasing Happy", author: "Phil Waldrep", image: "https://books.google.com/books/content?id=LYE-EAAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Autobiography" },
  { title: "The Women of the Bible Speak", author: "Shannon Bream", image: "https://books.google.com/books/content?id=PPuTEAAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Fiction" }, /* Added Fiction */
  { title: "The 5 Love Languages", author: "Gary D. Chapman", image: "https://books.google.com/books/content?id=cVYB4RHJDgcC&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Romance" },
  { title: "The Mothers and Daughters", author: "Shannon Bream", image: "https://books.google.com/books/content?id=fpk6zwEACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Science" },
  { title: "Find Your People", author: "Jennie Allen", image: "https://books.google.com/books/content?id=7dv2zgEACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Business" },
  { title: "Universal Principles of Design", author: "William Lidwell", image: "https://books.google.com/books/content?id=l0QPECGQySYC&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Science" },
  { title: "The Making of a Manager", author: "Julie Zhuo", image: "https://books.google.com/books/content?id=malkEQAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Business" },

  // New Additions
  { title: "Steve Jobs", author: "Walter Isaacson", image: "https://books.google.com/books/publisher/content?id=8U2oAAAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&imgtk=AFLRE710Y48B5iV4C2-fN2mO4lH1W2u0J-qW7q2V6mRkYtG8Y_L2o3r10oK6-6_x9p85xXl0m7yP8l4n_G87C-Z8_U9n3-M6d32-vL1wT02jV4s4rW5j7T3qL2k_v3E10u2l_1-m7-O4X&source=gbs_api", category: "Autobiography" },
  { title: "A Brief History of Time", author: "Stephen Hawking", image: "https://books.google.com/books/content?id=-P24CgAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Science" },
  { title: "Pride and Prejudice", author: "Jane Austen", image: "https://books.google.com/books/content?id=s1gVAAAAYAAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Romance" },
  { title: "Dune", author: "Frank Herbert", image: "https://books.google.com/books/content?id=B1hSG45JCX4C&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api", category: "Fiction" },
  { title: "Zero to One", author: "Peter Thiel", image: "https://books.google.com/books/publisher/content?id=YQ1xAwAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&imgtk=AFLRE70H5F8L02-kR6I48y98xG9Q8zN0M_-W8O0I01oF7q_uL8V4Y4k92e8W_49C4_kC-_sK_nK0Iq-x0M_7cZ_D1o9q-t-_3lQ0nO8Q9T8wV_-B4j7w_1D-_X_36wKV3W5p-29hH2-p_1_2q120s110A&source=gbs_api", category: "Business" },
  { title: "Thinking, Fast and Slow", author: "Daniel Kahneman", image: "https://books.google.com/books/content?id=ZuHTvQEACAAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api", category: "Science" },
  { title: "The Great Gatsby", author: "F. Scott Fitzgerald", image: "https://books.google.com/books/publisher/content?id=Vf0NEAAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&imgtk=AFLRE73s_X_wZ0B6iX5A9h7C5n9N_G59d33z95R_Y92U-_d8s_s4i5y5vE5j5B79s_xK1k_58L2V4n9X9K3r-i-_X-X4t_V47M_E43k7I6V7b5K-n3yP_3f1O9p4q2T2u-_Z__v3O_M2x7Y4w159V&source=gbs_api", category: "Fiction" }
]

const filteredBooks = computed(() => {
  if (activeTab.value === 'ALL') return libraryBooks
  return libraryBooks.filter(book => book.category === activeTab.value)
})
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
