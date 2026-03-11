<template>
  <div class="max-w-4xl mx-auto py-16 px-8">
    <div class="text-center mb-16">
      <h1 class="text-4xl font-bold text-gray-900 mb-4 tracking-tight">Frequently Asked Questions</h1>
      <p class="text-xl text-gray-600">Got questions? We've got answers to help you get the most out of LeadByBooks.</p>
    </div>

    <!-- FAQ Accordion -->
    <div class="space-y-4">
      <div v-for="(faq, index) in faqs" :key="index" class="border border-gray-100 rounded-2xl bg-white overflow-hidden shadow-sm hover:shadow-md transition-shadow">
        <button 
          @click="toggleFaq(index)"
          class="w-full text-left px-6 py-5 flex items-center justify-between focus:outline-none"
        >
          <span class="font-bold text-gray-900 pr-4">{{ faq.question }}</span>
          <span class="text-primary transform transition-transform duration-300 flex-shrink-0" :class="{ 'rotate-180': openIndex === index }">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
          </span>
        </button>
        
        <div 
          class="px-6 pb-5 text-gray-600 border-t border-gray-50 pt-4"
          v-show="openIndex === index"
        >
          {{ faq.answer }}
        </div>
      </div>
    </div>

    <div class="mt-16 bg-primary/5 border border-primary/10 rounded-3xl p-8 text-center">
      <h3 class="text-xl font-bold text-gray-900 mb-2">Still have questions?</h3>
      <p class="text-gray-600 mb-6">Can't find the answer you're looking for? Please contact our friendly team.</p>
      <NuxtLink to="/contact" class="inline-block bg-primary hover:bg-primary-dark transition-colors text-white font-medium px-8 py-3 rounded-xl shadow-md cursor-pointer">
        Get in touch
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

useHead({
  title: 'FAQ - LeadByBooks'
})

const openIndex = ref<number | null>(0)

const toggleFaq = (index: number) => {
  openIndex.value = openIndex.value === index ? null : index
}

const faqs = [
  {
    question: "What exactly is LeadByBooks?",
    answer: "LeadByBooks is a community-driven platform designed for intellectual engagement. It's more than just a digital library; it's a social space where readers can track their books, join themed chatrooms, and access supplementary materials like podcasts and articles related to their interests."
  },
  {
    question: "Is it free to join?",
    answer: "Yes! Creating an account and joining the global reading community on LeadByBooks is completely free. We believe in open access to shared knowledge."
  },
  {
    question: "How do the Chatrooms work?",
    answer: "Chatrooms are dedicated, real-time messaging spaces organized around specific genres, topics, or even single books. You can join them via the 'Interests' page to discuss themes with like-minded members."
  },
  {
    question: "Can I host my own reading group here?",
    answer: "Absolutely. While we curate some main channels, our upcoming features will allow users to create and moderate private or public groups tailored to their local book clubs or specific niches."
  },
  {
    question: "What is 'Chess Mates' on the user dashboard?",
    answer: "Chess Mates is an integrated mini-game feature designed to provide a mental break and intellectual stimulation between reading sessions. It allows you to challenge other active platform members to a quick game of chess."
  },
  {
    question: "Do you provide actual ebooks or just summaries?",
    answer: "We showcase a vast library of curated real-world books for you to discover and discuss. While we don't host the full copyrighted e-book files themselves, we provide extensive supplementary reading materials, articles, and recommendations."
  },
  {
    question: "How are the \"Books of the Month\" selected?",
    answer: "The Books of the Month featured on our landing page are curated by our editorial team based on community trends, highly anticipated releases across various genres, and profound literary impact."
  },
  {
    question: "Can I send direct messages to other users?",
    answer: "Yes, our Chatrooms feature includes both public channels and private direct messaging, allowing you to have one-on-one literature discussions with connections you make on the platform."
  },
  {
    question: "Do I need to read business or non-fiction books to join?",
    answer: "Not at all. While we have robust categories for Business, Science, and Autobiography, we also proudly feature Romance, Fiction, and History. All genres that provoke thought and enjoyment are welcome."
  },
  {
    question: "Is there a mobile app available?",
    answer: "Currently, LeadByBooks is a fully responsive web application optimized for all devices including mobile browsers. Native iOS and Android applications are on our development roadmap."
  }
]
</script>
