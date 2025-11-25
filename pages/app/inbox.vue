<script setup lang="ts">
import { Search, MoreVertical, Send, Paperclip, Phone, Video } from 'lucide-vue-next'

definePageMeta({
  layout: 'app'
})

const conversations = [
  { id: 1, name: 'Sarah Chen', preview: 'Thanks for the update! When can we...', time: '2m', unread: true, avatar: 'SC', active: true },
  { id: 2, name: 'Marcus Rodriguez', preview: 'The proposal looks good. I have one...', time: '1h', unread: false, avatar: 'MR', active: false },
  { id: 3, name: 'Emily Watson', preview: 'Can we reschedule our meeting?', time: '3h', unread: false, avatar: 'EW', active: false },
  { id: 4, name: 'David Kim', preview: 'I sent over the files you requested.', time: '1d', unread: false, avatar: 'DK', active: false },
  { id: 5, name: 'Jessica Lee', preview: 'Let me check with my team.', time: '2d', unread: false, avatar: 'JL', active: false },
]

const messages = [
  { id: 1, text: 'Hi Sarah, just wanted to follow up on our call yesterday.', sender: 'me', time: '10:30 AM' },
  { id: 2, text: 'Hey! Yes, I discussed it with the team.', sender: 'them', time: '10:35 AM' },
  { id: 3, text: 'We are very interested in the Enterprise plan.', sender: 'them', time: '10:36 AM' },
  { id: 4, text: 'That\'s great to hear! I can send over the contract details.', sender: 'me', time: '10:38 AM' },
  { id: 5, text: 'Perfect. Also, do you have documentation on the API integration?', sender: 'them', time: '10:40 AM' },
  { id: 6, text: 'Absolutely, here is the link to our developer docs.', sender: 'me', time: '10:42 AM' },
  { id: 7, text: 'Thanks for the update! When can we schedule a technical deep dive?', sender: 'them', time: '10:45 AM' },
]
</script>

<template>
  <div class="h-[calc(100vh-100px)] flex gap-6 overflow-hidden">
    <!-- Sidebar List -->
    <div class="w-80 flex flex-col card p-0 overflow-hidden flex-shrink-0">
      <div class="p-4 border-b border-[#2E2E3A]">
        <h2 class="text-lg font-bold mb-4">Inbox</h2>
        <div class="relative">
          <Search class="absolute left-3 top-1/2 -translate-y-1/2 w-4 h-4 text-gray-400" />
          <input 
            type="text" 
            placeholder="Search messages..." 
            class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg pl-10 pr-4 py-2 text-sm text-white focus:outline-none focus:border-primary transition-colors"
          >
        </div>
      </div>
      
      <div class="flex-1 overflow-y-auto">
        <div 
          v-for="chat in conversations" 
          :key="chat.id"
          class="p-4 border-b border-[#2E2E3A] cursor-pointer hover:bg-[#151520]/50 transition-colors"
          :class="{ 'bg-[#151520]/80 border-l-2 border-l-primary': chat.active }"
        >
          <div class="flex justify-between items-start mb-1">
            <div class="flex items-center gap-3">
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-gray-700 to-gray-800 flex items-center justify-center text-sm font-bold text-white border border-[#2E2E3A]">
                {{ chat.avatar }}
              </div>
              <div>
                <h3 class="font-medium text-white text-sm">{{ chat.name }}</h3>
                <p class="text-xs text-gray-400 truncate w-32">{{ chat.preview }}</p>
              </div>
            </div>
            <div class="flex flex-col items-end gap-1">
              <span class="text-xs text-gray-500">{{ chat.time }}</span>
              <div v-if="chat.unread" class="w-2 h-2 rounded-full bg-primary"></div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Chat Area -->
    <div class="flex-1 card p-0 flex flex-col overflow-hidden">
      <!-- Chat Header -->
      <div class="p-4 border-b border-[#2E2E3A] flex justify-between items-center bg-[#151520]/30">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 rounded-full bg-gradient-to-br from-gray-700 to-gray-800 flex items-center justify-center text-sm font-bold text-white border border-[#2E2E3A]">
            SC
          </div>
          <div>
            <h3 class="font-bold text-white">Sarah Chen</h3>
            <span class="text-xs text-green-400 flex items-center gap-1">
              <div class="w-1.5 h-1.5 rounded-full bg-green-400"></div>
              Online
            </span>
          </div>
        </div>
        <div class="flex items-center gap-2">
          <button class="p-2 hover:bg-[#2E2E3A] rounded-lg text-gray-400 hover:text-white transition-colors">
            <Phone class="w-5 h-5" />
          </button>
          <button class="p-2 hover:bg-[#2E2E3A] rounded-lg text-gray-400 hover:text-white transition-colors">
            <Video class="w-5 h-5" />
          </button>
          <button class="p-2 hover:bg-[#2E2E3A] rounded-lg text-gray-400 hover:text-white transition-colors">
            <MoreVertical class="w-5 h-5" />
          </button>
        </div>
      </div>

      <!-- Messages -->
      <div class="flex-1 overflow-y-auto p-6 space-y-6 bg-[#0A0A1A]/20">
        <div 
          v-for="msg in messages" 
          :key="msg.id" 
          class="flex"
          :class="msg.sender === 'me' ? 'justify-end' : 'justify-start'"
        >
          <div 
            class="max-w-[70%] rounded-2xl p-4 text-sm"
            :class="msg.sender === 'me' 
              ? 'bg-primary text-white rounded-tr-none' 
              : 'bg-[#2E2E3A] text-gray-200 rounded-tl-none'"
          >
            <p>{{ msg.text }}</p>
            <span 
              class="text-[10px] mt-1 block opacity-70"
              :class="msg.sender === 'me' ? 'text-right' : 'text-left'"
            >
              {{ msg.time }}
            </span>
          </div>
        </div>
      </div>

      <!-- Input Area -->
      <div class="p-4 border-t border-[#2E2E3A] bg-[#151520]/30">
        <div class="flex items-center gap-3">
          <button class="p-2 hover:bg-[#2E2E3A] rounded-full text-gray-400 hover:text-white transition-colors">
            <Paperclip class="w-5 h-5" />
          </button>
          <input 
            type="text" 
            placeholder="Type a message..." 
            class="flex-1 bg-[#151520] border border-[#2E2E3A] rounded-full px-4 py-2.5 text-sm text-white focus:outline-none focus:border-primary transition-colors"
          >
          <button class="p-2.5 bg-primary hover:bg-primary/90 rounded-full text-white transition-colors shadow-lg shadow-primary/20">
            <Send class="w-4 h-4" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
