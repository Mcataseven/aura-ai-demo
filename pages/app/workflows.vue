<script setup lang="ts">
import { ref } from 'vue'
import { Zap, Mail, UserPlus, AlertCircle, Calendar, MessageSquare, Plus } from 'lucide-vue-next'

definePageMeta({
  layout: 'app'
})

const workflows = ref([
  { id: 1, title: 'New Lead Welcome', description: 'Send a welcome email sequence when a new lead is added.', icon: UserPlus, active: true, runs: 1240 },
  { id: 2, title: 'Churn Prevention', description: 'Alert account manager when usage drops below 20%.', icon: AlertCircle, active: true, runs: 45 },
  { id: 3, title: 'Meeting Follow-up', description: 'Send summary and action items after every Zoom call.', icon: Calendar, active: false, runs: 890 },
  { id: 4, title: 'Deal Acceleration', description: 'Notify sales rep when a prospect views the pricing page.', icon: Zap, active: true, runs: 320 },
  { id: 5, title: 'Support Auto-Reply', description: 'Send instant reply to support tickets created off-hours.', icon: MessageSquare, active: true, runs: 2100 },
  { id: 6, title: 'Cold Outreach', description: 'Automated LinkedIn connection and message sequence.', icon: Mail, active: false, runs: 0 },
])
</script>

<template>
  <div class="space-y-6">
    <!-- Header -->
    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
      <div>
        <h1 class="text-2xl font-bold text-white">Automation Workflows</h1>
        <p class="text-gray-400">Manage and monitor your automated tasks.</p>
      </div>
      <button class="btn btn-primary gap-2">
        <Plus class="w-5 h-5" />
        Create Workflow
      </button>
    </div>

    <!-- Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div v-for="workflow in workflows" :key="workflow.id" class="card p-6 flex flex-col h-full hover:border-primary/50 transition-colors">
        <div class="flex justify-between items-start mb-4">
          <div class="w-12 h-12 rounded-lg bg-[#151520] border border-[#2E2E3A] flex items-center justify-center text-primary">
            <component :is="workflow.icon" class="w-6 h-6" />
          </div>
          
          <!-- Toggle Switch -->
          <button 
            @click="workflow.active = !workflow.active"
            class="w-12 h-6 rounded-full relative transition-colors duration-300 focus:outline-none"
            :class="workflow.active ? 'bg-primary' : 'bg-[#2E2E3A]'"
          >
            <div 
              class="w-4 h-4 rounded-full bg-white absolute top-1 transition-transform duration-300"
              :class="workflow.active ? 'left-7' : 'left-1'"
            ></div>
          </button>
        </div>

        <h3 class="text-lg font-bold text-white mb-2">{{ workflow.title }}</h3>
        <p class="text-sm text-gray-400 mb-6 flex-1">{{ workflow.description }}</p>

        <div class="flex items-center justify-between pt-4 border-t border-[#2E2E3A]">
          <span class="text-xs text-gray-500">{{ workflow.runs }} runs this month</span>
          <button class="text-sm font-medium text-primary hover:text-white transition-colors">Edit</button>
        </div>
      </div>

      <!-- Create New Card Placeholder -->
      <button class="card p-6 flex flex-col items-center justify-center h-full border-dashed border-2 border-[#2E2E3A] hover:border-primary/50 hover:bg-[#151520]/50 transition-all group cursor-pointer min-h-[200px]">
        <div class="w-12 h-12 rounded-full bg-[#151520] flex items-center justify-center mb-4 group-hover:scale-110 transition-transform">
          <Plus class="w-6 h-6 text-gray-400 group-hover:text-primary" />
        </div>
        <span class="font-medium text-gray-400 group-hover:text-white">Create New Workflow</span>
      </button>
    </div>
  </div>
</template>
