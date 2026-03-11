<template>
  <div class="max-w-7xl mx-auto py-12 px-8">
    <div class="mb-12 flex flex-col md:flex-row md:items-end justify-between gap-6">
      <div>
        <h1 class="text-4xl font-bold text-gray-900 mb-2 font-serif tracking-tight">Podcasts</h1>
        <p class="text-gray-500 text-lg">Deep dive interviews, literary analysis, and author Q&As.</p>
      </div>
      
      <div class="flex gap-4 w-full md:w-auto">
        <div class="relative w-full md:w-64">
           <input type="text" placeholder="Search episodes..." class="w-full bg-gray-50 border border-gray-200 rounded-full py-2.5 pl-10 pr-4 focus:outline-none focus:ring-2 focus:ring-primary/20">
           <IconSearch class="w-5 h-5 text-gray-400 absolute left-3.5 top-3" />
        </div>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
      <div v-for="(podcast, index) in featuredPodcasts" :key="index" class="bg-white rounded-3xl border border-gray-100 shadow-sm hover:shadow-xl transition-shadow overflow-hidden group">
        <div class="h-48 relative overflow-hidden bg-gray-100">
          <img :src="podcast.image" :alt="podcast.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700">
          <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
          <div class="absolute bottom-4 left-4 right-4 flex items-center justify-between">
             <div class="bg-primary/90 backdrop-blur-sm text-white text-xs font-bold px-3 py-1.5 rounded-full">
               {{ podcast.category }}
             </div>
             <span class="text-white text-sm font-medium">{{ podcast.duration }}</span>
          </div>
        </div>
        <div class="p-6">
          <h3 class="font-bold text-gray-900 text-xl mb-2 line-clamp-2 leading-tight">{{ podcast.title }}</h3>
          <p class="text-gray-500 text-sm mb-6 line-clamp-3">{{ podcast.description }}</p>
          <div class="flex items-center justify-between">
             <div class="flex items-center gap-3">
               <div class="w-10 h-10 rounded-full overflow-hidden bg-gray-200">
                 <img :src="podcast.hostImage" alt="Host" class="w-full h-full object-cover">
               </div>
               <div>
                 <p class="text-sm font-bold text-gray-900 leading-none">{{ podcast.host }}</p>
                 <p class="text-xs text-gray-500">Host</p>
               </div>
             </div>
             <button class="w-10 h-10 rounded-full bg-gray-50 text-primary flex items-center justify-center hover:bg-primary hover:text-white transition-colors">
               <IconPlayerPlay class="w-5 h-5 ml-1" />
             </button>
          </div>
        </div>
      </div>
    </div>

    <h3 class="text-2xl font-bold text-gray-900 mb-6">Recent Episodes</h3>
    <div class="space-y-4">
       <div v-for="(episode, index) in recentEpisodes" :key="index" class="bg-white border border-gray-100 rounded-2xl p-4 flex items-center gap-6 hover:shadow-md transition-shadow group cursor-pointer">
          <div class="w-20 h-20 rounded-xl overflow-hidden bg-gray-100 flex-shrink-0 relative">
             <img :src="episode.image" class="w-full h-full object-cover">
             <div class="absolute inset-0 bg-black/40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity">
               <IconPlayerPlay class="w-8 h-8 text-white ml-1" />
             </div>
          </div>
          <div class="flex-1">
             <div class="flex items-center gap-3 mb-1">
               <span class="text-xs font-bold text-primary bg-primary/10 px-2 py-0.5 rounded-md">{{ episode.date }}</span>
               <span class="text-xs text-gray-400 font-medium">{{ episode.duration }}</span>
             </div>
             <h4 class="font-bold text-gray-900 text-lg mb-1 group-hover:text-primary transition-colors">{{ episode.title }}</h4>
             <p class="text-sm text-gray-500 line-clamp-1">{{ episode.description }}</p>
          </div>
       </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconSearch, IconPlayerPlay } from '@tabler/icons-vue'

useHead({
  title: 'Podcasts - LeadByBooks'
})

const featuredPodcasts = [
  {
    title: "The Architecture of a Happy Marriage with Ann Patchett",
    description: "Ann Patchett sits down to discuss the non-fiction essays that make up her acclaimed collection, diving deep into the realities of lifelong commitment and the writing process.",
    category: "Author Interview",
    duration: "1h 15m",
    image: "https://images.unsplash.com/photo-1478147424096-ad939fc739ab?auto=format&fit=crop&w=800&q=80",
    host: "Sarah Koenig",
    hostImage: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "Decoding the Market: Graham's Principles Today",
    description: "Financial analysts break down Benjamin Graham's 'The Intelligent Investor' and discuss how his depression-era value investing principles apply to modern tech stocks.",
    category: "Literary Analysis",
    duration: "54m",
    image: "https://images.unsplash.com/photo-1590283603385-17ffb3a7f29f?auto=format&fit=crop&w=800&q=80",
    host: "Michael Lewis",
    hostImage: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "Religious Extremism and 'Under the Banner of Heaven'",
    description: "A deep dive into Jon Krakauer's investigative masterpiece, exploring the psychological mechanisms behind fundamentalism and true crime narrative structures.",
    category: "Deep Dive",
    duration: "1h 30m",
    image: "https://images.unsplash.com/photo-1585829365295-ab7cd400c167?auto=format&fit=crop&w=800&q=80",
    host: "Ira Glass",
    hostImage: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=150&q=80"
  }
]

const recentEpisodes = [
  {
    title: "Julie Zhuo on The Making of a Manager",
    description: "Former Facebook VP of Design Julie Zhuo shares her transition from creator to leader.",
    date: "Mar 10",
    duration: "45m",
    image: "https://images.unsplash.com/photo-1516321497487-e288fb19713f?auto=format&fit=crop&w=200&q=80"
  },
  {
    title: "Understanding 'The 5 Love Languages' in 2026",
    description: "Does Gary Chapman's classic still hold up in the era of digital dating and remote relationships?",
    date: "Mar 05",
    duration: "52m",
    image: "https://images.unsplash.com/photo-1518199266791-5375a83190b7?auto=format&fit=crop&w=200&q=80"
  },
  {
    title: "Why We Can't Stop Chasing Happy",
    description: "Phil Waldrep discusses the societal pressures of constant positive emotional output.",
    date: "Feb 28",
    duration: "1h 05m",
    image: "https://images.unsplash.com/photo-1499209974431-9dddcece7f88?auto=format&fit=crop&w=200&q=80"
  },
  {
    title: "Find Your People: Navigating Adult Friendships",
    description: "Jennie Allen breaks down the neurobiology and sociology behind forming tight-knit communities.",
    date: "Feb 21",
    duration: "58m",
    image: "https://images.unsplash.com/photo-1529156069898-49953eb1b5ce?auto=format&fit=crop&w=200&q=80"
  }
]
</script>
