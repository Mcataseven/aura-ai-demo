<script setup lang="ts">
import { ref } from 'vue'
import { Menu, X } from 'lucide-vue-next'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <!-- NAV -->
  <nav class="nav">
    <div class="container nav-inner">
      <NuxtLink to="/" class="logo" aria-label="Aura AI Home" style="display:flex;align-items:center;gap:10px;">
        <div style="width:32px;height:32px;border-radius:10px;display:grid;place-items:center;background:color-mix(in oklab, var(--primary) 12%, transparent);">
          <!-- sparkles -->
          <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/>
            <path d="M5 3v4"/><path d="M19 17v4"/><path d="M3 5h4"/><path d="M17 19h4"/>
          </svg>
        </div>
        <span style="font-weight:700;">Aura AI</span>
      </NuxtLink>

      <!-- Desktop Menu -->
      <div class="nav-links hidden-md" style="gap:24px;">
        <NuxtLink to="/features" class="hover:text-white transition-colors">Features</NuxtLink>
        <NuxtLink to="/pricing" class="hover:text-white transition-colors">Pricing</NuxtLink>
        <NuxtLink to="/blog" class="hover:text-white transition-colors">Blog</NuxtLink>
        <NuxtLink to="/templates" class="hover:text-white transition-colors">Templates</NuxtLink>
      </div>

      <!-- Desktop Actions -->
      <div class="hidden md:flex" style="display:flex;gap:10px;">
        <NuxtLink to="/login" class="btn btn-ghost">Login</NuxtLink>
        <NuxtLink to="/register" class="btn btn-primary">Start Free Trial →</NuxtLink>
      </div>

      <!-- Mobile Menu Button -->
      <button @click="toggleMenu" class="md:hidden text-gray-400 hover:text-white">
        <Menu v-if="!isMenuOpen" class="w-6 h-6" />
        <X v-else class="w-6 h-6" />
      </button>
    </div>

    <!-- Mobile Menu Drawer -->
    <div 
      v-if="isMenuOpen" 
      class="md:hidden absolute top-[65px] left-0 w-full bg-[#0A0A1A] border-b border-[#2E2E3A] p-6 flex flex-col gap-4 shadow-2xl z-50"
    >
      <NuxtLink to="/features" @click="closeMenu" class="text-lg font-medium text-gray-300 hover:text-white">Features</NuxtLink>
      <NuxtLink to="/pricing" @click="closeMenu" class="text-lg font-medium text-gray-300 hover:text-white">Pricing</NuxtLink>
      <NuxtLink to="/blog" @click="closeMenu" class="text-lg font-medium text-gray-300 hover:text-white">Blog</NuxtLink>
      <NuxtLink to="/templates" @click="closeMenu" class="text-lg font-medium text-gray-300 hover:text-white">Templates</NuxtLink>
      
      <div class="h-px bg-[#2E2E3A] my-2"></div>
      
      <NuxtLink to="/login" @click="closeMenu" class="btn btn-ghost justify-start px-0 text-lg">Login</NuxtLink>
      <NuxtLink to="/register" @click="closeMenu" class="btn btn-primary justify-center text-lg py-3">Start Free Trial</NuxtLink>
    </div>
  </nav>
</template>
