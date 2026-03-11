<template>
  <div class="bg-gray-50 min-h-screen py-24">
    <div class="max-w-7xl mx-auto px-8 grid grid-cols-1 lg:grid-cols-4 gap-8">
      
      <!-- Sidebar / User Profile Stats -->
      <aside class="lg:col-span-1 space-y-6">
        <!-- User Welcome Card -->
        <div class="bg-white rounded-3xl p-6 shadow-sm border border-gray-100 flex flex-col items-center text-center">
          <div class="w-24 h-24 rounded-full bg-primary/20 text-primary flex items-center justify-center text-3xl font-bold mb-4">
            JD
          </div>
          <h2 class="text-xl font-bold text-gray-900">John Doe</h2>
          <p class="text-gray-500 mb-6 font-medium text-sm">Passionate Reader</p>
          
          <div class="flex justify-between w-full border-t border-gray-100 pt-6">
            <div>
              <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">Books Read</p>
              <p class="text-2xl font-bold text-gray-900">28</p>
            </div>
            <div>
              <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">Groups</p>
              <p class="text-2xl font-bold text-gray-900">4</p>
            </div>
          </div>
        </div>

        <!-- Navigation Menu -->
        <nav class="bg-white rounded-3xl p-4 shadow-sm border border-gray-100 space-y-2">
          <a href="#" class="flex items-center space-x-3 px-4 py-3 rounded-xl bg-primary/10 text-primary font-bold transition-colors">
            <IconDashboard class="w-5 h-5" />
            <span>Dashboard</span>
          </a>
          <a href="#" class="flex items-center space-x-3 px-4 py-3 rounded-xl text-gray-600 hover:bg-gray-50 hover:text-primary transition-colors font-medium">
            <IconBooks class="w-5 h-5" />
            <span>My Library</span>
          </a>
          <a href="#" class="flex items-center space-x-3 px-4 py-3 rounded-xl text-gray-600 hover:bg-gray-50 hover:text-primary transition-colors font-medium">
            <IconMessages class="w-5 h-5" />
            <span>Chatrooms</span>
          </a>
          <a href="#" class="flex items-center space-x-3 px-4 py-3 rounded-xl text-gray-600 hover:bg-gray-50 hover:text-primary transition-colors font-medium">
            <IconSettings class="w-5 h-5" />
            <span>Settings</span>
          </a>
        </nav>
      </aside>

      <!-- Main Dashboard Content -->
      <main class="lg:col-span-3 space-y-8">
        
        <!-- Header -->
        <div class="flex justify-between items-end">
          <div>
            <h1 class="text-3xl font-bold text-gray-900 mb-2">Welcome back, John!</h1>
            <p class="text-gray-500">Here is what's happening in your reading community today.</p>
          </div>
        </div>

        <!-- Reading Progress row -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div class="bg-white rounded-3xl p-6 shadow-sm border border-gray-100">
            <div class="flex items-center justify-between mb-4">
              <h3 class="font-bold text-gray-900">Book of the Month</h3>
              <span class="text-primary bg-primary/10 p-2 rounded-lg"><IconTrophy class="w-5 h-5"/></span>
            </div>
            <p class="text-gray-500 text-sm mb-4">You're currently reading</p>
            <div class="flex items-center space-x-4">
              <div class="w-16 h-24 bg-gray-200 rounded-lg overflow-hidden shrink-0">
                <img src="https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Book" class="w-full h-full object-cover" />
              </div>
              <div>
                <h4 class="font-bold text-gray-900 line-clamp-1">The Great Gatsby</h4>
                <p class="text-primary text-xs font-bold mb-2">F. Scott Fitzgerald</p>
                <div class="w-full bg-gray-100 rounded-full h-1.5 mt-2">
                  <div class="bg-primary h-1.5 rounded-full" style="width: 45%"></div>
                </div>
                <p class="text-xs text-gray-500 mt-1 text-right">45%</p>
              </div>
            </div>
          </div>

          <div class="bg-white rounded-3xl p-6 shadow-sm border border-gray-100 md:col-span-2 relative overflow-hidden flex items-center">
            <!-- Background Decoration -->
            <div class="absolute -right-12 -top-12 w-48 h-48 bg-primary/5 rounded-full blur-3xl"></div>
            
            <div class="w-full flex justify-between items-center z-10">
              <div class="max-w-xs">
                <h3 class="font-bold text-xl text-gray-900 mb-2">Chess Mates</h3>
                <p class="text-gray-500 text-sm mb-6">Take a break from reading. Challenge your community members to a friendly game.</p>
                <button class="bg-gray-900 hover:bg-gray-800 text-white transition-colors px-6 py-2.5 rounded-full font-medium text-sm">
                  Join Players
                </button>
              </div>
              <div class="hidden sm:block w-32 h-32">
                <IconChess class="w-full h-full text-gray-200" />
              </div>
            </div>
          </div>
        </div>

        <!-- Active Chatrooms -->
        <h3 class="text-2xl font-bold text-gray-900 pt-4">Your Active Chatrooms</h3>
        <div class="grid md:grid-cols-2 gap-6">
          
          <div class="bg-white border border-gray-100 rounded-3xl p-6 shadow-sm flex space-x-6 hover:shadow-md transition-shadow cursor-pointer">
            <div class="w-24 h-24 rounded-2xl overflow-hidden shrink-0">
              <img src="https://images.unsplash.com/photo-1532094349884-543bc11b234d?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Room" class="w-full h-full object-cover" />
            </div>
            <div class="flex flex-col justify-center w-full">
              <div class="flex justify-between items-center mb-1">
                <h4 class="font-bold text-gray-900 text-lg">Science Explorer</h4>
                <div class="w-2 h-2 rounded-full bg-green-500"></div>
              </div>
              <p class="text-gray-500 text-sm mb-3">Alice: I completely agree with the theory...</p>
              <div class="flex items-center justify-between mt-auto">
                <span class="text-xs font-semibold text-primary bg-primary/10 px-2 py-1 rounded">2 New Messages</span>
                <span class="text-xs text-gray-400">10:42 AM</span>
              </div>
            </div>
          </div>

          <div class="bg-white border border-gray-100 rounded-3xl p-6 shadow-sm flex space-x-6 hover:shadow-md transition-shadow cursor-pointer">
            <div class="w-24 h-24 rounded-2xl overflow-hidden shrink-0">
              <img src="https://images.unsplash.com/photo-1474932430478-367d16b99231?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Room" class="w-full h-full object-cover" />
            </div>
            <div class="flex flex-col justify-center w-full">
              <div class="flex justify-between items-center mb-1">
                <h4 class="font-bold text-gray-900 text-lg">Classic Literature</h4>
                <div class="w-2 h-2 rounded-full bg-gray-300"></div>
              </div>
              <p class="text-gray-500 text-sm mb-3">Bob: Has anyone read chapters 4-6 yet?</p>
              <div class="flex items-center justify-between mt-auto">
                <span class="text-xs font-semibold text-gray-500 bg-gray-100 px-2 py-1 rounded">No unread msgs</span>
                <span class="text-xs text-gray-400">Yesterday</span>
              </div>
            </div>
          </div>

        </div>

      </main>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconDashboard, IconBooks, IconMessages, IconSettings, IconTrophy, IconChess } from '@tabler/icons-vue'

useHead({
  title: 'Dashboard - LeadByBooks'
})
</script>
