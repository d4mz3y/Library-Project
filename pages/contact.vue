<template>
  <div class="max-w-7xl mx-auto py-16 px-8 flex flex-col lg:flex-row gap-16">
    <!-- Left Info Side -->
    <div class="lg:w-1/3">
      <h1 class="text-4xl font-bold text-gray-900 mb-6 tracking-tight">Get in touch</h1>
      <p class="text-gray-600 mb-10 text-lg">
        We'd love to hear from you. Please fill out this form or shoot us an email. Let's talk about books, features, or partnerships.
      </p>

      <div class="space-y-8">
        <div>
          <h3 class="font-bold text-gray-900 text-lg mb-2 flex items-center gap-2">
            <span class="w-8 h-8 rounded-full bg-primary/10 text-primary flex items-center justify-center">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
            </span>
            Email
          </h3>
          <p class="text-gray-600 ml-10">hello@leadbybooks.com</p>
          <p class="text-gray-600 ml-10">support@leadbybooks.com</p>
        </div>

        <div>
          <h3 class="font-bold text-gray-900 text-lg mb-2 flex items-center gap-2">
            <span class="w-8 h-8 rounded-full bg-primary/10 text-primary flex items-center justify-center">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
            </span>
            Office
          </h3>
          <p class="text-gray-600 ml-10">123 Literary Lane</p>
          <p class="text-gray-600 ml-10">San Francisco, CA 94105</p>
        </div>
        
        <div>
          <h3 class="font-bold text-gray-900 text-lg mb-2 flex items-center gap-2">
            <span class="w-8 h-8 rounded-full bg-primary/10 text-primary flex items-center justify-center">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
            </span>
            Phone
          </h3>
          <p class="text-gray-600 ml-10">+1 (555) 123-4567</p>
        </div>
      </div>
    </div>

    <!-- Right Form Side -->
    <div class="lg:w-2/3 bg-white border border-gray-100 shadow-xl shadow-gray-200/40 rounded-3xl p-8 md:p-12">
      <form @submit.prevent class="space-y-6">
        <div class="grid md:grid-cols-2 gap-6">
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">First Name</label>
            <input type="text" placeholder="John" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors bg-gray-50 focus:bg-white" />
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Last Name</label>
            <input type="text" placeholder="Doe" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors bg-gray-50 focus:bg-white" />
          </div>
        </div>
        
        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Email Address</label>
          <input type="email" placeholder="john@example.com" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors bg-gray-50 focus:bg-white" />
        </div>
        
        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Subject</label>
          <input type="text" placeholder="How can we help?" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors bg-gray-50 focus:bg-white" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Message</label>
          <textarea rows="5" placeholder="Your message here..." class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors bg-gray-50 focus:bg-white resize-none"></textarea>
        </div>

        <button type="submit" class="w-full bg-primary hover:bg-primary-dark text-white font-medium py-4 rounded-xl shadow-lg shadow-primary/30 transition-colors text-lg">
          Send Message
        </button>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Contact Us - LeadByBooks'
})
</script>
