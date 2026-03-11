<template>
  <div class="bg-white pb-20">
    <!-- Hero Section 1: Read with Like-Minds -->
    <section class="max-w-7xl mx-auto px-8 py-16 md:py-24 grid md:grid-cols-2 gap-12 items-center">
      <div class="space-y-6">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 leading-tight">
          Read with Like-Minds
        </h1>
        <p class="text-lg text-gray-600 leading-relaxed">
          Share your opinions and thoughts on your favorite books. Engage in meaningful discussions with a community that shares your passion for literature.
        </p>
        <NuxtLink to="/signup" class="inline-block bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-8 py-3 rounded-full shadow-lg shadow-primary/30">
          Get Started
        </NuxtLink>
      </div>
      <div class="relative h-[400px] rounded-3xl overflow-hidden shadow-2xl">
        <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Group of friends reading" class="w-full h-full object-cover" />
      </div>
    </section>

    <!-- Hero Section 2: Make new Connections (Reversed) -->
    <section class="bg-secondary/30 py-16 md:py-24">
      <div class="max-w-7xl mx-auto px-8 grid md:grid-cols-2 gap-12 items-center">
        <div class="relative h-[400px] rounded-3xl overflow-hidden shadow-2xl order-2 md:order-1">
          <img src="https://images.unsplash.com/photo-1517486808906-6ca8b3f04846?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Two people drinking coffee and discussing" class="w-full h-full object-cover" />
        </div>
        <div class="space-y-6 order-1 md:order-2 md:pl-8">
          <h2 class="text-4xl md:text-5xl font-bold text-gray-900 leading-tight">
            Make new Connections
          </h2>
          <p class="text-lg text-gray-600 leading-relaxed">
            Find reading friends perfectly matched to your interests. Build a network of intellectuals and expand your horizons through shared knowledge.
          </p>
          <NuxtLink to="/chatrooms" class="inline-block border-2 border-primary text-primary hover:bg-primary hover:text-white transition-colors font-medium px-8 py-3 rounded-full">
            Explore Chatrooms
          </NuxtLink>
        </div>
      </div>
    </section>

    <!-- Call To Action Panel -->
    <section class="max-w-7xl mx-auto px-8 py-20">
      <div class="bg-secondary p-10 md:p-16 rounded-[40px] flex flex-col md:flex-row items-center justify-between shadow-xl">
        <div class="mb-8 md:mb-0 md:mr-8 text-center md:text-left">
          <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
            Join any Reading group of your choice
          </h2>
          <p class="text-lg text-gray-700">Connect with thousands of active readers across the globe.</p>
        </div>
        <NuxtLink to="/signup" class="bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-10 py-4 rounded-full text-lg shadow-lg shadow-primary/40 flex-shrink-0 inline-block">
          Get Started
        </NuxtLink>
      </div>
    </section>

    <!-- Featured Books Horizontal Scroll -->
    <section class="max-w-7xl mx-auto px-8 py-12 overflow-hidden">
      <div class="flex items-center justify-between mb-8">
        <h3 class="text-2xl font-bold text-gray-900">Books for the month of May</h3>
        <NuxtLink to="/books" class="text-primary font-medium hover:underline">View All</NuxtLink>
      </div>
      
      <!-- Books Scroll Area -->
      <div class="flex space-x-6 overflow-x-auto pb-8 snap-x hide-scrollbar">
        <!-- Book Card 1 -->
        <div class="min-w-[240px] snap-start group cursor-pointer w-[240px]">
          <div class="h-[360px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://books.google.com/books/content?id=-NdcCSt8t_YC&printsec=frontcover&img=1&zoom=0&source=gbs_api" alt="The Intelligent Investor" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">The Intelligent Investor</h4>
          <p class="text-gray-500 text-sm mb-1">Benjamin Graham</p>
          <p class="text-primary font-bold text-xs mt-1 bg-secondary inline-block px-3 py-1 rounded-full uppercase tracking-wider">Business</p>
        </div>

        <!-- Book Card 2 -->
        <div class="min-w-[240px] snap-start group cursor-pointer w-[240px]">
          <div class="h-[360px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://books.google.com/books/content?id=efE_AQAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api" alt="This is the Story of a Happy Marriage" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">A Happy Marriage</h4>
          <p class="text-gray-500 text-sm mb-1">Ann Patchett</p>
          <p class="text-primary font-bold text-xs mt-1 bg-secondary inline-block px-3 py-1 rounded-full uppercase tracking-wider">Romance</p>
        </div>

        <!-- Book Card 3 -->
        <div class="min-w-[240px] snap-start group cursor-pointer w-[240px]">
          <div class="h-[360px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
             <img src="https://books.google.com/books/content?id=kRtdEAAAQBAJ&printsec=frontcover&img=1&zoom=0&source=gbs_api" alt="Just Tyrus" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">Just Tyrus</h4>
          <p class="text-gray-500 text-sm mb-1">Tyrus</p>
          <p class="text-primary font-bold text-xs mt-1 bg-secondary inline-block px-3 py-1 rounded-full uppercase tracking-wider">Autobiography</p>
        </div>

        <!-- Book Card 4 -->
        <div class="min-w-[240px] snap-start group cursor-pointer w-[240px]">
          <div class="h-[360px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://books.google.com/books/content?id=malkEQAAQBAJ&printsec=frontcover&img=1&zoom=0&edge=curl&source=gbs_api" alt="The Making of a Manager" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg leading-tight line-clamp-1 mb-1">The Making of a Manager</h4>
          <p class="text-gray-500 text-sm mb-1">Julie Zhuo</p>
          <p class="text-primary font-bold text-xs mt-1 bg-secondary inline-block px-3 py-1 rounded-full uppercase tracking-wider">Business</p>
        </div>
      </div>
    </section>

    <!-- Subscription Section -->
    <section class="max-w-3xl mx-auto px-8 py-20 text-center">
      <h3 class="text-3xl font-bold text-gray-900 mb-6">Stay Updated</h3>
      <p class="text-gray-600 mb-8 max-w-xl mx-auto">Get updates and announcements, subscribe to our mail.</p>
      
      <form @submit.prevent class="flex flex-col sm:flex-row gap-4 justify-center">
        <input 
          type="email" 
          placeholder="Enter your email address" 
          class="flex-1 max-w-md px-6 py-4 rounded-full border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/50 focus:border-primary transition-all"
        />
        <button type="submit" class="bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-8 py-4 rounded-full shadow-lg shadow-primary/30">
          Subscribe
        </button>
      </form>
    </section>

  </div>
</template>

<script setup lang="ts">
// Page Head
useHead({
  title: 'LeadByBooks - Read with Like-Minds',
  meta: [
    { name: 'description', content: 'Join a reading community, share your thoughts, and make new connections.' }
  ]
})
</script>

<style scoped>
/* Hide scrollbar for Chrome, Safari and Opera */
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
/* Hide scrollbar for IE, Edge and Firefox */
.hide-scrollbar {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>
