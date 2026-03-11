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
        <button class="bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-8 py-3 rounded-full shadow-lg shadow-primary/30">
          Get Started
        </button>
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
          <button class="border-2 border-primary text-primary hover:bg-primary hover:text-white transition-colors font-medium px-8 py-3 rounded-full">
            Explore Chatrooms
          </button>
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
        <button class="bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-10 py-4 rounded-full text-lg shadow-lg shadow-primary/40 flex-shrink-0">
          Get Started
        </button>
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
        <!-- Book Card Placeholder 1 -->
        <div class="min-w-[240px] snap-start group cursor-pointer">
          <div class="h-[320px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://images.unsplash.com/photo-1589829085413-56de8ae18c73?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="The Intelligent Investor" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg line-clamp-1">The Intelligent Investor</h4>
          <p class="text-primary font-medium text-sm mt-1 bg-secondary inline-block px-3 py-1 rounded-full">Business</p>
        </div>

        <!-- Book Card Placeholder 2 -->
        <div class="min-w-[240px] snap-start group cursor-pointer">
          <div class="h-[320px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="This is the Story of a Happy Marriage" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg line-clamp-1">Happy Marriage Story</h4>
          <p class="text-primary font-medium text-sm mt-1 bg-secondary inline-block px-3 py-1 rounded-full">Romance</p>
        </div>

        <!-- Book Card Placeholder 3 -->
        <div class="min-w-[240px] snap-start group cursor-pointer">
          <div class="h-[320px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://images.unsplash.com/photo-1532012197267-da84d127e765?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Atomic Habits" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg line-clamp-1">Atomic Habits</h4>
          <p class="text-primary font-medium text-sm mt-1 bg-secondary inline-block px-3 py-1 rounded-full">Growth</p>
        </div>

        <!-- Book Card Placeholder 4 -->
        <div class="min-w-[240px] snap-start group cursor-pointer">
          <div class="h-[320px] bg-gray-100 rounded-2xl mb-4 overflow-hidden shadow-md group-hover:shadow-xl transition-all">
            <img src="https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Sapiens" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <h4 class="font-bold text-gray-900 text-lg line-clamp-1">Sapiens</h4>
          <p class="text-primary font-medium text-sm mt-1 bg-secondary inline-block px-3 py-1 rounded-full">History</p>
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
