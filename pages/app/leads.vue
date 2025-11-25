<script setup lang="ts">
import { Download, Filter, Search, MoreHorizontal } from 'lucide-vue-next'

definePageMeta({
  layout: 'app'
})

const leads = [
  { id: 1, name: 'Sarah Chen', company: 'TechVision Inc.', email: 'sarah.chen@techvision.io', score: 94, status: 'Qualified', lastContact: '2 hours ago' },
  { id: 2, name: 'Marcus Rodriguez', company: 'CloudScale Systems', email: 'm.rodriguez@cloudscale.com', score: 89, status: 'Qualified', lastContact: '1 day ago' },
  { id: 3, name: 'Emily Watson', company: 'DataFlow Analytics', email: 'e.watson@dataflow.ai', score: 87, status: 'Qualified', lastContact: '3 days ago' },
  { id: 4, name: 'David Kim', company: 'FutureNet', email: 'david.k@futurenet.com', score: 76, status: 'New', lastContact: '5 hours ago' },
  { id: 5, name: 'Jessica Lee', company: 'Innovate Corp', email: 'j.lee@innovate.co', score: 92, status: 'Negotiation', lastContact: '1 hour ago' },
  { id: 6, name: 'Michael Brown', company: 'Alpha Solutions', email: 'm.brown@alpha.com', score: 65, status: 'Contacted', lastContact: '2 days ago' },
  { id: 7, name: 'Lisa Wang', company: 'Global Tech', email: 'lisa.w@globaltech.com', score: 81, status: 'Qualified', lastContact: '4 hours ago' },
  { id: 8, name: 'James Wilson', company: 'NetSecure', email: 'j.wilson@netsecure.io', score: 72, status: 'New', lastContact: '1 day ago' },
  { id: 9, name: 'Robert Taylor', company: 'SmartSys', email: 'r.taylor@smartsys.com', score: 55, status: 'Cold', lastContact: '1 week ago' },
  { id: 10, name: 'Jennifer Davis', company: 'WebWorks', email: 'j.davis@webworks.net', score: 88, status: 'Negotiation', lastContact: '3 hours ago' }
]

const getScoreColor = (score: number) => {
  if (score >= 90) return 'text-green-400 bg-green-400/10'
  if (score >= 70) return 'text-blue-400 bg-blue-400/10'
  if (score >= 50) return 'text-yellow-400 bg-yellow-400/10'
  return 'text-red-400 bg-red-400/10'
}

const getStatusColor = (status: string) => {
  switch (status) {
    case 'Qualified': return 'bg-primary/10 text-primary'
    case 'New': return 'bg-blue-400/10 text-blue-400'
    case 'Negotiation': return 'bg-purple-400/10 text-purple-400'
    case 'Contacted': return 'bg-yellow-400/10 text-yellow-400'
    default: return 'bg-gray-400/10 text-gray-400'
  }
}
</script>

<template>
  <div class="space-y-6">
    <!-- Header -->
    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
      <div>
        <h1 class="text-2xl font-bold text-white">Leads Management</h1>
        <p class="text-gray-400">Track and manage your potential customers.</p>
      </div>
      <div class="flex items-center gap-3">
        <button class="btn btn-outline gap-2">
          <Filter class="w-4 h-4" />
          Filter
        </button>
        <button class="btn btn-outline gap-2">
          <Download class="w-4 h-4" />
          Export
        </button>
        <button class="btn btn-primary">
          + Add Lead
        </button>
      </div>
    </div>

    <!-- Table Card -->
    <div class="card overflow-hidden">
      <!-- Search Bar -->
      <div class="p-4 border-b border-[#2E2E3A]">
        <div class="relative max-w-sm">
          <Search class="absolute left-3 top-1/2 -translate-y-1/2 w-4 h-4 text-gray-400" />
          <input 
            type="text" 
            placeholder="Search leads..." 
            class="w-full bg-[#151520] border border-[#2E2E3A] rounded-lg pl-10 pr-4 py-2 text-sm text-white focus:outline-none focus:border-primary transition-colors"
          >
        </div>
      </div>

      <!-- Table -->
      <div class="overflow-x-auto">
        <table class="w-full text-left border-collapse">
          <thead>
            <tr class="border-b border-[#2E2E3A] bg-[#151520]/50">
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider">Name</th>
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider">Company</th>
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider">Lead Score</th>
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider">Status</th>
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider">Last Contacted</th>
              <th class="p-4 text-xs font-medium text-gray-400 uppercase tracking-wider text-right">Actions</th>
            </tr>
          </thead>
          <tbody class="divide-y divide-[#2E2E3A]">
            <tr v-for="lead in leads" :key="lead.id" class="group hover:bg-[#151520]/50 transition-colors">
              <td class="p-4">
                <div class="flex flex-col">
                  <span class="font-medium text-white">{{ lead.name }}</span>
                  <span class="text-xs text-gray-500">{{ lead.email }}</span>
                </div>
              </td>
              <td class="p-4 text-sm text-gray-300">{{ lead.company }}</td>
              <td class="p-4">
                <span :class="['px-2 py-1 rounded text-xs font-medium', getScoreColor(lead.score)]">
                  {{ lead.score }}
                </span>
              </td>
              <td class="p-4">
                <span :class="['px-2 py-1 rounded-full text-xs font-medium', getStatusColor(lead.status)]">
                  {{ lead.status }}
                </span>
              </td>
              <td class="p-4 text-sm text-gray-400">{{ lead.lastContact }}</td>
              <td class="p-4 text-right">
                <button class="text-gray-400 hover:text-white transition-colors">
                  <MoreHorizontal class="w-5 h-5" />
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      
      <!-- Pagination -->
      <div class="p-4 border-t border-[#2E2E3A] flex items-center justify-between text-sm text-gray-400">
        <span>Showing 1-10 of 124 leads</span>
        <div class="flex gap-2">
          <button class="px-3 py-1 rounded border border-[#2E2E3A] hover:bg-[#2E2E3A] disabled:opacity-50" disabled>Previous</button>
          <button class="px-3 py-1 rounded border border-[#2E2E3A] hover:bg-[#2E2E3A]">Next</button>
        </div>
      </div>
    </div>
  </div>
</template>
