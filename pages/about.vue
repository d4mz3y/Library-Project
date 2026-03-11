<template>
  <div class="max-w-4xl mx-auto py-16 px-8">
    <div class="text-center mb-16">
      <h1 class="text-5xl font-bold text-gray-900 mb-6 tracking-tight">About LeadByBooks</h1>
      <p class="text-xl text-gray-600 leading-relaxed max-w-2xl mx-auto">
        We are building the internet's most thoughtful, intellectually rigorous, and engaged community of readers. 
      </p>
    </div>

    <div class="prose prose-lg prose-primary max-w-none text-gray-700">
      <p class="mb-6">
        LeadByBooks started with a simple observation: reading is often solitary, yet the ideas we encounter in books demand discussion, debate, and shared exploration. We wanted to build a bridge between the quiet act of reading and the vibrant world of human connection.
      </p>
      
      <div class="my-12 grid md:grid-cols-2 gap-8">
        <div class="bg-gray-50 p-8 rounded-2xl border border-gray-100">
          <h3 class="text-xl font-bold text-gray-900 mb-4">Our Mission</h3>
          <p>
            To cultivate a global network of continuous learners by providing a platform where deep literary engagement and meaningful interpersonal connections intersect. We believe that shared knowledge accelerates personal and collective growth.
          </p>
        </div>
        <div class="bg-primary/5 p-8 rounded-2xl border border-primary/10">
          <h3 class="text-xl font-bold text-primary mb-4">The Platform</h3>
          <p>
            More than just a digital bookshelf, LeadByBooks is a social habitat for the mind. We offer curated reading spaces, real-time thematic chatrooms, shared progress tracking, and access to a massive library of supplementary materials including articles, podcasts, and audiobooks.
          </p>
        </div>
      </div>

      <h2 class="text-3xl font-bold text-gray-900 mt-12 mb-6">Why We're Different</h2>
      <ul class="space-y-4 mb-8">
        <li class="flex items-start">
          <span class="flex-shrink-0 h-6 w-6 rounded-full bg-primary/20 text-primary flex items-center justify-center font-bold text-sm mt-1 mr-3">1</span>
          <span><strong>Curated Intimacy:</strong> Instead of massive, noisy feeds, we focus on intimate, interest-based Chatrooms where voices can actually be heard.</span>
        </li>
        <li class="flex items-start">
          <span class="flex-shrink-0 h-6 w-6 rounded-full bg-primary/20 text-primary flex items-center justify-center font-bold text-sm mt-1 mr-3">2</span>
          <span><strong>Multi-Format Learning:</strong> We understand books are just one medium. We actively integrate podcasts, articles, and audiobooks into the discourse.</span>
        </li>
        <li class="flex items-start">
          <span class="flex-shrink-0 h-6 w-6 rounded-full bg-primary/20 text-primary flex items-center justify-center font-bold text-sm mt-1 mr-3">3</span>
          <span><strong>Intellectual Play:</strong> With integrations like "Chess Mates," we recognize that intellectual stimulation takes many forms beyond just reading.</span>
        </li>
      </ul>

      <div class="mt-16 text-center border-t border-gray-100 pt-12">
        <h3 class="text-2xl font-bold text-gray-900 mb-4">Ready to join the conversation?</h3>
        <NuxtLink to="/signup" class="inline-block bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-8 py-4 rounded-full shadow-lg shadow-primary/30 text-lg">
          Create an Account Today
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'About Us - LeadByBooks'
})
</script>
