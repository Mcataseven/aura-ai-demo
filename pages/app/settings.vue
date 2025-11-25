<script setup lang="ts">
import { Camera, Save } from 'lucide-vue-next'

definePageMeta({
  layout: 'app'
})
</script>

<template>
  <div class="max-w-4xl mx-auto space-y-8">
    <!-- Header -->
    <div>
      <h1 class="text-2xl font-bold text-white">Account Settings</h1>
      <p class="text-gray-400">Manage your profile and preferences.</p>
    </div>

    <!-- Profile Section -->
    <div class="card p-8">
      <h2 class="text-lg font-bold text-white mb-6">Profile Information</h2>
      
      <div class="flex flex-col md:flex-row gap-8">
        <!-- Avatar Upload -->
        <div class="flex flex-col items-center gap-4">
          <div class="w-24 h-24 rounded-full bg-[#151520] border border-[#2E2E3A] flex items-center justify-center relative group cursor-pointer overflow-hidden">
            <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?auto=format&fit=crop&q=80&w=200" alt="Profile" class="w-full h-full object-cover opacity-80 group-hover:opacity-50 transition-opacity">
            <Camera class="w-8 h-8 text-white absolute opacity-0 group-hover:opacity-100 transition-opacity" />
          </div>
          <button class="text-sm text-primary hover:text-white transition-colors">Change Photo</button>
        </div>

        <!-- Form Fields -->
        <div class="flex-1 space-y-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="space-y-2">
              <label class="text-sm font-medium text-gray-400">First Name</label>
              <input type="text" value="Alex" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">
            </div>
            <div class="space-y-2">
              <label class="text-sm font-medium text-gray-400">Last Name</label>
              <input type="text" value="Morgan" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">
            </div>
          </div>

          <div class="space-y-2">
            <label class="text-sm font-medium text-gray-400">Email Address</label>
            <input type="email" value="alex.morgan@company.com" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">
          </div>

          <div class="space-y-2">
            <label class="text-sm font-medium text-gray-400">Bio</label>
            <textarea rows="3" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">Product Manager at TechFlow. Passionate about AI and automation.</textarea>
          </div>
        </div>
      </div>
    </div>

    <!-- Security Section -->
    <div class="card p-8">
      <h2 class="text-lg font-bold text-white mb-6">Security</h2>
      <div class="space-y-6 max-w-md">
        <div class="space-y-2">
          <label class="text-sm font-medium text-gray-400">Current Password</label>
          <input type="password" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">
        </div>
        <div class="space-y-2">
          <label class="text-sm font-medium text-gray-400">New Password</label>
          <input type="password" class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg px-4 py-2.5 text-white focus:outline-none focus:border-primary transition-colors">
        </div>
      </div>
    </div>

    <!-- Notifications Section -->
    <div class="card p-8">
      <h2 class="text-lg font-bold text-white mb-6">Notifications</h2>
      <div class="space-y-4">
        <label class="flex items-center gap-3 cursor-pointer group">
          <input type="checkbox" checked class="w-5 h-5 rounded border-gray-600 text-primary focus:ring-primary bg-[#151520]">
          <span class="text-gray-300 group-hover:text-white transition-colors">Email me about new leads</span>
        </label>
        <label class="flex items-center gap-3 cursor-pointer group">
          <input type="checkbox" checked class="w-5 h-5 rounded border-gray-600 text-primary focus:ring-primary bg-[#151520]">
          <span class="text-gray-300 group-hover:text-white transition-colors">Email me about weekly reports</span>
        </label>
        <label class="flex items-center gap-3 cursor-pointer group">
          <input type="checkbox" class="w-5 h-5 rounded border-gray-600 text-primary focus:ring-primary bg-[#151520]">
          <span class="text-gray-300 group-hover:text-white transition-colors">Subscribe to product updates newsletter</span>
        </label>
      </div>
    </div>

    <!-- Action Buttons -->
    <div class="flex justify-end gap-4 pt-4">
      <button class="btn btn-ghost">Cancel</button>
      <button class="btn btn-primary gap-2 px-8">
        <Save class="w-4 h-4" />
        Save Changes
      </button>
    </div>
  </div>
</template>
