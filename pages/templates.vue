<script setup lang="ts">
import { Mail, BarChart2, Users, MessageSquare, Calendar, Zap } from 'lucide-vue-next'

const templates = [
  {
    id: 1,
    icon: Mail,
    title: 'Cold Email Sequence',
    description: 'Automated 5-step email sequence for outbound prospecting with AI personalization.',
    tags: ['Outbound', 'Email']
  },
  {
    id: 2,
    icon: BarChart2,
    title: 'Lead Scoring Model',
    description: 'Pre-configured scoring rules to identify your most promising leads automatically.',
    tags: ['Qualification', 'Analytics']
  },
  {
    id: 3,
    icon: Users,
    title: 'Onboarding Flow',
    description: 'Streamline new client onboarding with automated tasks and welcome messages.',
    tags: ['Customer Success', 'Workflow']
  },
  {
    id: 4,
    icon: MessageSquare,
    title: 'Meeting Follow-up',
    description: 'AI-generated meeting summaries and action items sent directly to your CRM.',
    tags: ['Productivity', 'Meetings']
  },
  {
    id: 5,
    icon: Calendar,
    title: 'Quarterly Review',
    description: 'Template for conducting comprehensive quarterly business reviews with clients.',
    tags: ['Account Management', 'Reporting']
  },
  {
    id: 6,
    icon: Zap,
    title: 'Deal Acceleration',
    description: 'Workflow triggers to re-engage stalled deals and move them through the pipeline.',
    tags: ['Sales', 'Automation']
  }
]
</script>

<template>
  <div class="page-wrapper min-h-screen bg-[#0A0A1A] relative">
    <AppHeader />
    <div class="hero-bg"></div>
    
    <main class="main-content relative z-10">
      <!-- Header -->
      <section class="section pt-32 pb-16">
        <div class="container">
          <div class="center max-w-2xl mx-auto">
            <h1 class="mb-4">Start with a Template</h1>
            <p class="text-xl text-gray-400">Pre-built workflows to automate your sales instantly. Choose a template and customize it to fit your needs.</p>
          </div>
        </div>
      </section>

      <!-- Templates Grid -->
      <section class="section pb-32">
        <div class="container">
          <div class="grid grid-3 gap-6">
            <div v-for="template in templates" :key="template.id" class="card p-6 rounded-xl hover:border-primary transition-colors group cursor-pointer">
              <div class="w-12 h-12 rounded-lg bg-white/5 flex items-center justify-center mb-6 group-hover:bg-primary/20 transition-colors">
                <component :is="template.icon" class="w-6 h-6 text-gray-300 group-hover:text-primary transition-colors" />
              </div>
              <h3 class="text-lg font-bold mb-2">{{ template.title }}</h3>
              <p class="text-gray-400 text-sm mb-4 leading-relaxed">{{ template.description }}</p>
              <div class="flex flex-wrap gap-2">
                <span v-for="tag in template.tags" :key="tag" class="text-xs px-2 py-1 rounded bg-white/5 text-gray-400 border border-white/5">
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <AppFooter />
  </div>
</template>

<style scoped>
.page-wrapper {
  /* background-color removed to allow hero-bg to show */
}
</style>
