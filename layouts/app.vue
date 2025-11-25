<script setup lang="ts">
import { 
  LayoutDashboard, 
  Users, 
  Inbox, 
  GitBranch, 
  Settings, 
  LogOut,
  Search,
  Bell,
  ChevronDown
} from 'lucide-vue-next'

const route = useRoute()

const menuItems = [
  { name: 'Dashboard', icon: LayoutDashboard, path: '/app' },
  { name: 'Leads', icon: Users, path: '/app/leads' },
  { name: 'Inbox', icon: Inbox, path: '/app/inbox' },
  { name: 'Workflows', icon: GitBranch, path: '/app/workflows' },
  { name: 'Settings', icon: Settings, path: '/app/settings' },
]
</script>

<template>
  <div class="min-h-screen bg-[#0A0A1A] text-white font-sans flex">
    <!-- Sidebar -->
    <aside class="w-64 border-r border-[#2E2E3A] bg-[#151520] flex flex-col fixed h-full z-20">
      <!-- Logo -->
      <div class="h-16 flex items-center px-6 border-b border-[#2E2E3A]">
        <div class="flex items-center gap-3">
          <div class="w-8 h-8 rounded-lg bg-gradient-to-br from-[#8C52FF] to-blue-600 flex items-center justify-center shadow-lg shadow-[#8C52FF]/20">
            <span class="font-bold text-white text-lg">A</span>
          </div>
          <span class="font-bold text-lg tracking-tight">Aura AI</span>
        </div>
      </div>

      <!-- Navigation -->
      <nav class="flex-1 px-4 py-6 space-y-2">
        <NuxtLink 
          v-for="item in menuItems" 
          :key="item.name"
          :to="item.path"
          class="flex items-center gap-3 px-4 py-3 rounded-lg text-sm font-medium transition-all duration-200 group"
          :class="[
            route.path === item.path 
              ? 'bg-[#1E1E2D] text-white' 
              : 'text-gray-400 hover:bg-[#1E1E2D] hover:text-white'
          ]"
        >
          <component 
            :is="item.icon" 
            class="w-5 h-5 transition-colors"
            :class="route.path === item.path ? 'text-[#8C52FF]' : 'text-gray-500 group-hover:text-gray-300'"
          />
          {{ item.name }}
        </NuxtLink>
      </nav>

      <!-- User & Logout -->
      <div class="p-4 border-t border-[#2E2E3A]">
        <div class="flex items-center gap-3 px-4 py-3 mb-2">
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-purple-500 to-blue-500 flex items-center justify-center text-xs font-bold text-white">
            AM
          </div>
          <div class="flex-1 overflow-hidden">
            <h4 class="text-sm font-medium text-white truncate">Alex Morgan</h4>
            <p class="text-xs text-gray-500 truncate">alex@company.com</p>
          </div>
        </div>
        
        <NuxtLink 
          to="/" 
          class="flex items-center gap-3 px-4 py-2 text-gray-400 hover:text-red-400 hover:bg-red-400/10 rounded-lg transition-colors w-full"
        >
          <LogOut class="w-4 h-4" />
          <span class="font-medium text-sm">Logout</span>
        </NuxtLink>
      </div>
    </aside>

    <!-- Main Content -->
    <div class="flex-1 ml-64 flex flex-col min-h-screen">
      <!-- Topbar -->
      <header class="h-16 border-b border-[#2E2E3A] bg-[#0A0A1A]/80 backdrop-blur-md sticky top-0 z-10 px-8 flex items-center justify-between">
        <!-- Breadcrumbs / Title -->
        <div class="flex items-center gap-2 text-sm text-gray-400">
          <span>App</span>
          <span class="text-gray-600">/</span>
          <span class="text-white font-medium">{{ route.name?.toString().split('-').pop()?.replace(/^\w/, c => c.toUpperCase()) || 'Dashboard' }}</span>
        </div>

        <!-- Right Actions -->
        <div class="flex items-center gap-6">
          <!-- Search -->
          <div class="relative hidden md:block">
            <Search class="w-4 h-4 text-gray-500 absolute left-3 top-1/2 -translate-y-1/2" />
            <input 
              type="text" 
              placeholder="Search..." 
              class="bg-[#151520] border border-[#2E2E3A] rounded-full pl-9 pr-4 py-1.5 text-sm text-white placeholder-gray-600 focus:outline-none focus:border-[#8C52FF] focus:ring-1 focus:ring-[#8C52FF] w-64 transition-all"
            >
          </div>

          <!-- Notifications -->
          <button class="relative text-gray-400 hover:text-white transition-colors">
            <Bell class="w-5 h-5" />
            <span class="absolute top-0 right-0 w-2 h-2 bg-[#8C52FF] rounded-full border-2 border-[#0A0A1A]"></span>
          </button>
        </div>
      </header>

      <!-- Page Content -->
      <main class="p-8">
        <slot />
      </main>
    </div>
  </div>
</template>
