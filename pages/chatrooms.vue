<template>
  <div class="h-[calc(100vh-80px)] mt-20 flex bg-gray-50 overflow-hidden">
    <!-- Sidebar: Contacts & Channels -->
    <div class="w-80 bg-white border-r border-gray-100 flex flex-col h-full flex-shrink-0">
      
      <!-- User Profile Header -->
      <div class="p-4 border-b border-gray-100 flex items-center gap-3">
        <div class="w-10 h-10 rounded-full bg-gray-200 overflow-hidden">
           <img src="https://i.pravatar.cc/150?u=current_user" alt="My Profile" class="w-full h-full object-cover">
        </div>
        <div class="flex-1">
          <h3 class="font-bold text-gray-900 leading-tight">Sarah Reader</h3>
          <p class="text-xs text-green-500 font-medium">Online</p>
        </div>
        <button class="text-gray-400 hover:text-primary transition-colors">
          <IconSettings class="w-5 h-5" />
        </button>
      </div>

      <!-- Search -->
      <div class="p-4 border-b border-gray-100">
        <div class="relative">
           <input type="text" placeholder="Search chats..." class="w-full bg-gray-50 border border-gray-200 rounded-lg py-2 pl-9 pr-3 focus:outline-none focus:ring-1 focus:ring-primary text-sm">
           <IconSearch class="w-4 h-4 text-gray-400 absolute left-3 top-2.5" />
        </div>
      </div>

      <!-- Chat List -->
      <div class="flex-1 overflow-y-auto no-scrollbar">
        
        <!-- Channels -->
        <div class="p-2">
          <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider px-2 mb-2 mt-2">Public Channels</h4>
          
          <div class="space-y-1">
            <button class="w-full flex items-center gap-3 px-2 py-2.5 bg-primary/5 rounded-lg text-left group">
               <div class="w-10 h-10 rounded-xl bg-primary/20 flex items-center justify-center text-primary font-bold shadow-sm">
                 <IconHash class="w-5 h-5" />
               </div>
               <div class="flex-1 overflow-hidden">
                 <h5 class="font-bold text-gray-900 text-sm truncate group-hover:text-primary transition-colors">Philosophy Hub</h5>
                 <p class="text-xs text-gray-500 truncate">I think Therefore I Read...</p>
               </div>
               <div class="w-2 h-2 rounded-full bg-primary"></div>
            </button>
            <button class="w-full flex items-center gap-3 px-2 py-2.5 hover:bg-gray-50 rounded-lg text-left transition-colors group">
               <div class="w-10 h-10 rounded-xl bg-gray-100 flex items-center justify-center text-gray-500 font-bold group-hover:bg-primary/10 group-hover:text-primary transition-colors">
                 <IconHash class="w-5 h-5" />
               </div>
               <div class="flex-1 overflow-hidden">
                 <h5 class="font-medium text-gray-700 text-sm truncate group-hover:text-primary transition-colors">Modern Fiction</h5>
                 <p class="text-xs text-gray-400 truncate">Has anyone read the new...</p>
               </div>
            </button>
          </div>
        </div>

        <!-- Direct Messages -->
        <div class="p-2 border-t border-gray-100">
          <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider px-2 mb-2 mt-2">Direct Messages</h4>
          
          <div class="space-y-1">
            <button v-for="dm in directMessages" :key="dm.id" class="w-full flex items-center gap-3 px-2 py-2.5 hover:bg-gray-50 rounded-lg text-left transition-colors group">
               <div class="relative">
                 <div class="w-10 h-10 rounded-full bg-gray-200 overflow-hidden">
                   <img :src="dm.avatar" :alt="dm.name" class="w-full h-full object-cover">
                 </div>
                 <div class="absolute bottom-0 right-0 w-3 h-3 rounded-full border-2 border-white" :class="dm.online ? 'bg-green-500' : 'bg-gray-300'"></div>
               </div>
               <div class="flex-1 overflow-hidden">
                 <div class="flex justify-between items-baseline mb-0.5">
                   <h5 class="font-medium text-gray-700 text-sm truncate group-hover:text-primary transition-colors">{{ dm.name }}</h5>
                   <span class="text-[10px] text-gray-400">{{ dm.time }}</span>
                 </div>
                 <p class="text-xs truncate" :class="dm.unread ? 'text-gray-900 font-semibold' : 'text-gray-400'">{{ dm.lastMessage }}</p>
               </div>
               <div v-if="dm.unread" class="w-5 h-5 rounded-full bg-primary flex items-center justify-center text-[10px] text-white font-bold">
                 {{ dm.unread }}
               </div>
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Main Chat Window -->
    <div class="flex-1 flex flex-col h-full bg-white relative">
      
      <!-- Chat Header -->
      <div class="h-16 border-b border-gray-100 flex items-center justify-between px-6 flex-shrink-0 bg-white/80 backdrop-blur-md z-10 absolute top-0 w-full">
         <div class="flex items-center gap-4">
           <div class="w-10 h-10 rounded-xl bg-primary/10 flex items-center justify-center text-primary font-bold">
             <IconHash class="w-5 h-5" />
           </div>
           <div>
             <h2 class="font-bold text-gray-900 leading-tight">Philosophy Hub</h2>
             <p class="text-xs text-gray-500">2,415 members • 152 online</p>
           </div>
         </div>
         <div class="flex items-center gap-3 text-gray-400">
           <button class="hover:text-primary transition-colors"><IconPhone class="w-5 h-5" /></button>
           <button class="hover:text-primary transition-colors"><IconVideo class="w-5 h-5" /></button>
           <div class="w-px h-6 bg-gray-200 mx-2"></div>
           <button class="hover:text-primary transition-colors"><IconInfoCircle class="w-5 h-5" /></button>
         </div>
      </div>

      <!-- Messages Area -->
      <div class="flex-1 overflow-y-auto pt-20 pb-24 px-6 space-y-6">
         <!-- Date Divider -->
         <div class="flex items-center justify-center my-6">
           <div class="bg-gray-100 text-gray-500 text-xs font-bold px-3 py-1 rounded-full">Today, March 11</div>
         </div>

         <!-- Message Batch 1 -->
         <div class="flex gap-4">
           <img src="https://i.pravatar.cc/150?u=12" class="w-10 h-10 rounded-full flex-shrink-0">
           <div>
             <div class="flex items-baseline gap-2 mb-1">
               <span class="font-bold text-gray-900 text-sm">Marcus Vance</span>
               <span class="text-xs text-gray-400">10:42 AM</span>
             </div>
             <p class="text-gray-700 bg-gray-50 rounded-2xl rounded-tl-none px-4 py-2.5 inline-block">
               Has anyone here read the new analysis on Meditations? I feel like the stoicism trend in tech is completely misinterpreting Aurelius.
             </p>
           </div>
         </div>

         <!-- Message Batch 2 -->
         <div class="flex gap-4">
           <img src="https://i.pravatar.cc/150?u=45" class="w-10 h-10 rounded-full flex-shrink-0">
           <div>
             <div class="flex items-baseline gap-2 mb-1">
               <span class="font-bold text-gray-900 text-sm">Elena Richardson</span>
               <span class="text-xs text-gray-400">10:45 AM</span>
             </div>
             <p class="text-gray-700 bg-gray-50 rounded-2xl rounded-tl-none px-4 py-2.5 inline-block mb-1 border border-gray-100">
               100%. They treat it like a productivity hack instead of an actual ethical framework for existing in society.
             </p>
             <div class="w-full"></div>
             <p class="text-gray-700 bg-gray-50 rounded-2xl px-4 py-2.5 inline-block">
               I wrote a piece about this for the Articles section yesterday actually.
             </p>
           </div>
         </div>

         <!-- Current User Message -->
         <div class="flex gap-4 justify-end">
           <div class="flex flex-col items-end">
             <div class="flex items-baseline gap-2 mb-1 flex-row-reverse">
               <span class="font-bold text-gray-900 text-sm">You</span>
               <span class="text-xs text-gray-400">10:48 AM</span>
             </div>
             <p class="text-white bg-primary rounded-2xl rounded-tr-none px-4 py-2.5 inline-block shadow-md">
               I'll definitely check that article out. The commodification of philosophy is a massive issue right now.
             </p>
           </div>
           <img src="https://i.pravatar.cc/150?u=current_user" class="w-10 h-10 rounded-full flex-shrink-0">
         </div>
      </div>

      <!-- Input Area -->
      <div class="absolute bottom-0 w-full bg-white p-4 border-t border-gray-100 z-10">
        <div class="flex items-end gap-3 max-w-4xl mx-auto">
          <button class="w-10 h-10 rounded-full bg-gray-50 text-gray-400 hover:text-primary hover:bg-primary/10 transition-colors flex items-center justify-center flex-shrink-0 mb-1">
            <IconPlus class="w-5 h-5" />
          </button>
          <div class="flex-1 bg-gray-50 border border-gray-200 rounded-2xl flex items-center px-4 py-1 focus-within:ring-2 focus-within:ring-primary/20 focus-within:border-primary transition-all">
            <textarea 
              rows="1" 
              placeholder="Message #Philosophy Hub..." 
              class="w-full bg-transparent border-none focus:outline-none py-3 resize-none max-h-32 text-gray-700"
            ></textarea>
            <button class="text-gray-400 hover:text-primary transition-colors p-2">
              <IconMoodSmile class="w-5 h-5" />
            </button>
          </div>
          <button class="w-12 h-12 rounded-full bg-primary text-white hover:bg-primary-dark transition-colors flex items-center justify-center flex-shrink-0 shadow-md shadow-primary/30 mb-0.5">
            <IconSend class="w-5 h-5 ml-0.5" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { 
  IconSettings, IconSearch, IconHash, IconPhone, IconVideo, 
  IconInfoCircle, IconPlus, IconMoodSmile, IconSend 
} from '@tabler/icons-vue'

useHead({
  title: 'Chatrooms - LeadByBooks'
})

const directMessages = [
  { id: 1, name: "Alexander Hunt", avatar: "https://i.pravatar.cc/150?u=22", lastMessage: "Did you finish chapter 4?", time: "10m", unread: 2, online: true },
  { id: 2, name: "David Chen", avatar: "https://i.pravatar.cc/150?u=33", lastMessage: "That's exactly what I thought too.", time: "1h", unread: 0, online: true },
  { id: 3, name: "Sarah Jenkins", avatar: "https://i.pravatar.cc/150?u=44", lastMessage: "Let's play chess later!", time: "Yesterday", unread: 0, online: false },
  { id: 4, name: "Michael Chang", avatar: "https://i.pravatar.cc/150?u=55", lastMessage: "Thanks for the recommendation.", time: "Monday", unread: 0, online: false },
]

definePageMeta({
  layout: 'default' // Need to remove footer visually, but keep navbar
})
</script>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>
