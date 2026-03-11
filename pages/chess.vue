<template>
  <div class="max-w-7xl mx-auto py-12 px-8">
    <div class="text-center max-w-3xl mx-auto mb-16">
       <div class="w-20 h-20 bg-primary/10 rounded-3xl mx-auto flex items-center justify-center mb-6">
         <IconChess class="w-10 h-10 text-primary" />
       </div>
       <h1 class="text-5xl font-bold text-gray-900 mb-6 font-serif">Chess Mates</h1>
       <p class="text-xl text-gray-600">
         Intellectual stimulation doesn't stop at the bookmark. Challenge members of the reading community to a game of strategy.
       </p>
    </div>

    <!-- Main Chess Interface Placeholder -->
    <div class="bg-gray-900 rounded-[3rem] p-8 md:p-12 text-white shadow-2xl relative overflow-hidden flex flex-col lg:flex-row items-center justify-between min-h-[500px] mb-16">
      <!-- Decorative BG -->
      <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1529699211952-734e80c4d42b?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80')] bg-cover bg-center mix-blend-overlay opacity-20"></div>
      
      <div class="lg:w-1/2 z-10 text-center lg:text-left mb-10 lg:mb-0">
        <h2 class="text-4xl font-bold mb-4">Master Your Mind</h2>
        <p class="text-gray-400 text-lg mb-8 max-w-md mx-auto lg:mx-0">
          Ranked matchmaking is currently offline. Play against our state-of-the-art AI, or invite a friend directly via a Chatroom link.
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
          <button class="bg-primary hover:bg-primary-light transition-colors text-white font-bold py-4 px-8 rounded-2xl shadow-lg shadow-primary/30 flex items-center justify-center gap-2">
            Play vs AI (Stockfish)
          </button>
          <button class="bg-white/10 hover:bg-white/20 backdrop-blur-md transition-colors text-white font-bold py-4 px-8 rounded-2xl flex items-center justify-center gap-2 border border-white/10">
            Create Invite Link
          </button>
        </div>
      </div>

      <!-- Conceptual Chessboard Graphic -->
      <div class="lg:w-1/2 z-10 flex justify-center lg:justify-end">
         <div class="w-72 h-72 md:w-96 md:h-96 bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl shadow-2xl overflow-hidden grid grid-cols-8 grid-rows-8 transform rotate-3 hover:rotate-0 transition-transform duration-500">
            <!-- Generate checkerboard pattern -->
            <template v-for="row in 8" :key="`row-${row}`">
               <div v-for="col in 8" :key="`cell-${row}-${col}`" 
                    :class="[ (row + col) % 2 === 0 ? 'bg-white/10' : 'bg-transparent', 'w-full h-full' ]">
               </div>
            </template>
         </div>
      </div>
    </div>

    <!-- Leaderboard / Active Players -->
    <div class="max-w-4xl mx-auto">
      <h3 class="text-2xl font-bold text-gray-900 mb-6">Top Rated Readers</h3>
      <div class="bg-white border border-gray-100 rounded-3xl overflow-hidden shadow-sm">
        <div class="divide-y divide-gray-100">
           <div v-for="(player, index) in topPlayers" :key="index" class="p-4 flex items-center justify-between hover:bg-gray-50 transition-colors">
              <div class="flex items-center gap-4">
                 <div class="w-8 font-bold text-gray-400 text-center">#{{ index + 1 }}</div>
                 <div class="w-10 h-10 rounded-full bg-gray-200 overflow-hidden">
                   <img :src="`https://i.pravatar.cc/150?u=${player.id}`" alt="Avatar" class="w-full h-full object-cover">
                 </div>
                 <div>
                   <p class="font-bold text-gray-900">{{ player.name }}</p>
                   <p class="text-xs text-gray-500">Currently Reading: <span class="italic">{{ player.reading }}</span></p>
                 </div>
              </div>
              <div class="flex items-center gap-6">
                <div class="text-right">
                  <p class="text-sm font-bold text-primary">{{ player.elo }} ELO</p>
                  <p class="text-xs text-gray-400">{{ player.games }} Games</p>
                </div>
                <button class="bg-gray-100 hover:bg-gray-200 text-gray-900 px-4 py-2 rounded-lg text-sm font-medium transition-colors hidden sm:block">
                  Challenge
                </button>
              </div>
           </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IconChess } from '@tabler/icons-vue'

useHead({
  title: 'Chess Mates - LeadByBooks'
})

const topPlayers = [
  { id: 1, name: "MagnusC", elo: 2840, games: 1432, reading: "Thinking Fast and Slow" },
  { id: 2, name: "HikaruN", elo: 2790, games: 2104, reading: "Atomic Habits" },
  { id: 3, name: "FabianoC", elo: 2755, games: 890, reading: "The Intelligent Investor" },
  { id: 4, name: "IanN", elo: 2730, games: 1120, reading: "Dune" },
  { id: 5, name: "AlirezaF", elo: 2715, games: 450, reading: "Zero to One" },
]
</script>
