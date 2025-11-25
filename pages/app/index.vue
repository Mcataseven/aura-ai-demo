<script setup lang="ts">
import { 
  TrendingUp, 
  Users, 
  Target, 
  CheckSquare,
  MoreHorizontal,
  ArrowUpRight,
  ArrowDownRight
} from 'lucide-vue-next'

definePageMeta({
  layout: 'app'
})

useHead({
  title: 'Dashboard - Aura AI'
})

const stats = [
  { 
    label: 'Total Revenue', 
    value: '$124,500', 
    change: '+12.5%', 
    trend: 'up',
    icon: TrendingUp,
    color: 'text-[#8C52FF]'
  },
  { 
    label: 'Active Leads', 
    value: '1,240', 
    change: '+3.2%', 
    trend: 'up',
    icon: Users,
    color: 'text-blue-500'
  },
  { 
    label: 'Win Rate', 
    value: '24.8%', 
    change: '-0.4%', 
    trend: 'down',
    icon: Target,
    color: 'text-emerald-500'
  },
  { 
    label: 'Tasks Due', 
    value: '12', 
    change: 'Urgent', 
    trend: 'neutral',
    icon: CheckSquare,
    color: 'text-orange-500'
  }
]

const recentLeads = [
  { name: 'Sarah Chen', company: 'TechVision Inc.', status: 'New', value: '$12,000', date: '2 min ago' },
  { name: 'Marcus Rodriguez', company: 'CloudScale', status: 'Negotiation', value: '$45,000', date: '1 hour ago' },
  { name: 'Emily Watson', company: 'DataFlow', status: 'Qualified', value: '$8,500', date: '3 hours ago' },
  { name: 'David Kim', company: 'FutureSoft', status: 'Proposal', value: '$22,000', date: '5 hours ago' },
  { name: 'Jessica Lee', company: 'Innovate Corp', status: 'New', value: '$15,000', date: '1 day ago' },
]

const getStatusColor = (status: string) => {
  switch (status) {
    case 'New': return 'bg-blue-500/10 text-blue-500 border-blue-500/20'
    case 'Negotiation': return 'bg-orange-500/10 text-orange-500 border-orange-500/20'
    case 'Qualified': return 'bg-emerald-500/10 text-emerald-500 border-emerald-500/20'
    case 'Proposal': return 'bg-[#8C52FF]/10 text-[#8C52FF] border-[#8C52FF]/20'
    default: return 'bg-gray-500/10 text-gray-500 border-gray-500/20'
  }
}
</script>

<template>
  <div class="space-y-8">
    <!-- Header -->
    <div class="flex items-center justify-between">
      <h1 class="text-2xl font-bold text-white">Dashboard Overview</h1>
      <div class="flex gap-3">
        <button class="px-4 py-2 bg-[#151520] border border-[#2E2E3A] rounded-lg text-sm text-gray-300 hover:text-white hover:border-gray-600 transition-colors">
          Last 7 Days
        </button>
        <button class="px-4 py-2 bg-[#8C52FF] text-white rounded-lg text-sm font-medium hover:bg-[#7B42EE] transition-colors shadow-lg shadow-[#8C52FF]/20">
          + New Lead
        </button>
      </div>
    </div>

    <!-- Stats Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      <div 
        v-for="(stat, index) in stats" 
        :key="index"
        class="bg-[#151520] border border-[#2E2E3A] p-6 rounded-xl hover:border-gray-700 transition-colors group"
      >
        <div class="flex items-start justify-between mb-4">
          <div class="p-2 rounded-lg bg-[#0A0A1A] border border-[#2E2E3A] group-hover:border-[#8C52FF]/30 transition-colors">
            <component :is="stat.icon" class="w-5 h-5" :class="stat.color" />
          </div>
          <div 
            class="flex items-center gap-1 text-xs font-medium px-2 py-1 rounded-full"
            :class="stat.trend === 'up' ? 'bg-emerald-500/10 text-emerald-500' : stat.trend === 'down' ? 'bg-red-500/10 text-red-500' : 'bg-gray-500/10 text-gray-500'"
          >
            <ArrowUpRight v-if="stat.trend === 'up'" class="w-3 h-3" />
            <ArrowDownRight v-if="stat.trend === 'down'" class="w-3 h-3" />
            {{ stat.change }}
          </div>
        </div>
        <h3 class="text-gray-400 text-sm font-medium mb-1">{{ stat.label }}</h3>
        <p class="text-2xl font-bold text-white">{{ stat.value }}</p>
      </div>
    </div>

    <!-- Main Content Grid -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
      <!-- Activity Chart -->
      <div class="lg:col-span-2 bg-[#151520] border border-[#2E2E3A] rounded-xl p-6">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-lg font-bold text-white">Revenue Activity</h2>
          <button class="text-gray-500 hover:text-white">
            <MoreHorizontal class="w-5 h-5" />
          </button>
        </div>
        
        <!-- Fake Chart Area -->
        <div class="h-[300px] w-full relative flex items-end justify-between gap-2 px-4">
          <!-- Grid Lines -->
          <div class="absolute inset-0 flex flex-col justify-between pointer-events-none">
            <div v-for="i in 5" :key="i" class="w-full h-px bg-[#2E2E3A] border-t border-dashed border-gray-800"></div>
          </div>
          
          <!-- Bars (Fake) -->
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[40%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
            <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$42k</div>
          </div>
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[65%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$68k</div>
          </div>
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[45%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$48k</div>
          </div>
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[80%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$85k</div>
          </div>
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[55%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$58k</div>
          </div>
          <div class="w-full bg-[#8C52FF]/20 rounded-t-sm h-[90%] hover:bg-[#8C52FF] transition-colors cursor-pointer relative group">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">$92k</div>
          </div>
          <div class="w-full bg-[#8C52FF] rounded-t-sm h-[75%] shadow-[0_0_20px_rgba(140,82,255,0.3)] relative group cursor-pointer">
             <div class="absolute -top-8 left-1/2 -translate-x-1/2 bg-[#2E2E3A] text-white text-xs px-2 py-1 rounded opacity-100 transition-opacity whitespace-nowrap">$78k</div>
          </div>
        </div>
        <div class="flex justify-between mt-4 text-xs text-gray-500 px-4">
          <span>Mon</span>
          <span>Tue</span>
          <span>Wed</span>
          <span>Thu</span>
          <span>Fri</span>
          <span>Sat</span>
          <span>Sun</span>
        </div>
      </div>

      <!-- Recent Leads -->
      <div class="bg-[#151520] border border-[#2E2E3A] rounded-xl p-6 flex flex-col">
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-lg font-bold text-white">Recent Leads</h2>
          <NuxtLink to="/app/leads" class="text-sm text-[#8C52FF] hover:text-[#7B42EE]">View All</NuxtLink>
        </div>

        <div class="flex-1 overflow-y-auto pr-2 -mr-2 space-y-4">
          <div 
            v-for="(lead, index) in recentLeads" 
            :key="index"
            class="flex items-center justify-between p-3 rounded-lg hover:bg-[#2E2E3A]/30 transition-colors group cursor-pointer"
          >
            <div class="flex items-center gap-3">
              <div class="w-10 h-10 rounded-full bg-[#2E2E3A] flex items-center justify-center text-sm font-bold text-gray-300 group-hover:text-white group-hover:bg-[#8C52FF] transition-all">
                {{ lead.name.split(' ').map(n => n[0]).join('') }}
              </div>
              <div>
                <p class="text-sm font-medium text-white">{{ lead.name }}</p>
                <p class="text-xs text-gray-500">{{ lead.company }}</p>
              </div>
            </div>
            <div class="text-right">
              <p class="text-sm font-medium text-white">{{ lead.value }}</p>
              <span 
                class="inline-block px-2 py-0.5 rounded text-[10px] font-medium border mt-1"
                :class="getStatusColor(lead.status)"
              >
                {{ lead.status }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
