<template>
  <div class="max-w-7xl mx-auto py-12 px-8">
    <div class="mb-12 flex flex-col md:flex-row md:items-end justify-between gap-6">
      <div>
        <h1 class="text-4xl font-bold text-gray-900 mb-2 font-serif tracking-tight">Articles & Essays</h1>
        <p class="text-gray-500 text-lg">Curated thought pieces from our community and renowned authors.</p>
      </div>
      
      <div class="flex gap-4 w-full md:w-auto">
        <div class="flex space-x-2 overflow-x-auto pb-2 snap-x hide-scrollbar">
           <button v-for="tag in ['All', 'Philosophy', 'Tech', 'Literature', 'Science']" :key="tag" 
                   class="px-4 py-2 rounded-full border border-gray-200 text-sm font-medium whitespace-nowrap hover:bg-primary hover:text-white hover:border-primary transition-colors cursor-pointer">
             {{ tag }}
           </button>
        </div>
      </div>
    </div>

    <!-- Featured Hero Article -->
    <div class="grid lg:grid-cols-2 gap-10 mb-16 items-center">
       <div class="order-2 lg:order-1">
          <div class="flex items-center gap-3 mb-4">
            <span class="text-xs font-bold text-primary bg-primary/10 px-3 py-1 rounded-full uppercase tracking-wider">Editor's Pick</span>
            <span class="text-sm text-gray-400 font-medium">10 min read</span>
          </div>
          <h2 class="text-4xl font-bold text-gray-900 mb-4 leading-tight hover:text-primary transition-colors cursor-pointer">The Silent Erosion of Deep Reading in the Algorithmic Age</h2>
          <p class="text-lg text-gray-600 mb-6 leading-relaxed">
            As our screens fracture our attention into smaller and smaller increments, what happens to the cognitive pathways built for traversing an 800-page Russian novel? A look at how technology is rewiring our literary brains.
          </p>
          <div class="flex items-center gap-4">
             <div class="w-12 h-12 rounded-full overflow-hidden bg-gray-200">
               <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-4.0.3&auto=format&fit=crop&w=150&q=80" alt="Author" class="w-full h-full object-cover">
             </div>
             <div>
               <p class="font-bold text-gray-900 leading-none">Elena Richardson</p>
               <p class="text-sm text-gray-500">March 11, 2026</p>
             </div>
          </div>
       </div>
       <div class="order-1 lg:order-2 h-80 lg:h-[500px] rounded-3xl overflow-hidden shadow-xl">
          <img src="https://images.unsplash.com/photo-1543269664-7eef42226a21?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Library" class="w-full h-full object-cover hover:scale-105 transition-transform duration-700 cursor-pointer">
       </div>
    </div>

    <!-- Article Grid -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
      <div v-for="(article, index) in articles" :key="index" class="group cursor-pointer flex flex-col">
        <div class="h-48 rounded-2xl overflow-hidden mb-5 bg-gray-100 shadow-sm group-hover:shadow-md transition-shadow relative">
           <img :src="article.image" :alt="article.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
           <div class="absolute top-3 right-3 bg-white/90 backdrop-blur-sm text-gray-900 text-xs font-bold px-2 py-1 rounded-md shadow-sm">
             {{ article.readTime }}
           </div>
        </div>
        <div class="flex flex-col flex-1">
           <span class="text-primary text-xs font-bold uppercase tracking-wider mb-2 block">{{ article.category }}</span>
           <h3 class="font-bold text-gray-900 text-xl leading-tight mb-3 group-hover:text-primary transition-colors">{{ article.title }}</h3>
           <p class="text-gray-600 text-sm line-clamp-2 md:line-clamp-3 mb-4 flex-1">{{ article.excerpt }}</p>
           
           <div class="flex items-center justify-between border-t border-gray-100 pt-4 mt-auto">
             <div class="flex items-center gap-2">
               <div class="w-6 h-6 rounded-full bg-gray-200 overflow-hidden">
                 <img :src="article.authorImage" alt="Author" class="w-full h-full object-cover">
               </div>
               <span class="text-sm font-medium text-gray-700">{{ article.author }}</span>
             </div>
             <span class="text-xs text-gray-400">{{ article.date }}</span>
           </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Articles - LeadByBooks'
})

const articles = [
  {
    title: "Why 'Dune' Remains the Apex of Sci-Fi Worldbuilding",
    excerpt: "Six decades later, Frank Herbert's masterpiece still serves as the architectural blueprint for modern science fiction. We analyze the ecological and political systems that make Arrakis feel real.",
    category: "Literature",
    readTime: "8 min",
    date: "Mar 08",
    image: "https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?auto=format&fit=crop&w=600&q=80",
    author: "Marcus Vance",
    authorImage: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "The Stoicism Renaissance in Silicon Valley",
    excerpt: "From Marcus Aurelius to tech CEOs: How an ancient Hellenistic philosophy became the operating system for modern business leaders facing continuous market volatility.",
    category: "Philosophy",
    readTime: "12 min",
    date: "Mar 02",
    image: "https://images.unsplash.com/photo-1555674066-cd59b7cebb71?auto=format&fit=crop&w=600&q=80",
    author: "David Chen",
    authorImage: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "Defending the Romance Genre Against Literary Snobbery",
    excerpt: "It's a billion-dollar industry that keeps publishing afloat, yet it's treated as secondary. It's time to dismantle the patriarchal dismissal of 'happily ever afters.'",
    category: "Essay",
    readTime: "6 min",
    date: "Feb 25",
    image: "https://images.unsplash.com/photo-1474552226712-ac0f0961a954?auto=format&fit=crop&w=600&q=80",
    author: "Sarah Jenkins",
    authorImage: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "Artificial Intelligence vs. The Human Canvas",
    excerpt: "As large language models learn to generate cohesive narratives, what happens to the intrinsic value of human suffering and joy poured onto the page? Are books dead?",
    category: "Tech",
    readTime: "15 min",
    date: "Feb 18",
    image: "https://images.unsplash.com/photo-1620825937374-87fc7d62828e?auto=format&fit=crop&w=600&q=80",
    author: "Elena Richardson",
    authorImage: "https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "Reading 'Zero to One' When You're Not a Founder",
    excerpt: "Peter Thiel's manual for monopolistic capitalism has lessons that extend far beyond venture capital. Here is how independent creatives can use contrarian thinking.",
    category: "Business",
    readTime: "7 min",
    date: "Feb 10",
    image: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&w=600&q=80",
    author: "Michael Chang",
    authorImage: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?auto=format&fit=crop&w=150&q=80"
  },
  {
    title: "The Quiet Architecture of The Great Gatsby",
    excerpt: "Fitzgerald's brevity is often praised, but structural analysis reveals a highly engineered framework holding the tragic facade of East Egg together.",
    category: "Literature",
    readTime: "9 min",
    date: "Jan 28",
    image: "https://images.unsplash.com/photo-1518063319789-7217e3706bce?auto=format&fit=crop&w=600&q=80",
    author: "Julia Vance",
    authorImage: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=150&q=80"
  }
]
</script>
