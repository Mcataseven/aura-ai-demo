<script setup lang="ts">
import FeatureSection from '~/components/FeatureSection.vue'
import AppHeader from '~/components/AppHeader.vue'
import AppFooter from '~/components/AppFooter.vue'
import { Zap, Mail, ArrowRight, Shield, Lock, User, MessageSquare } from 'lucide-vue-next'

useHead({
  title: 'Features - Aura AI',
  meta: [
    { name: 'description', content: 'Explore the powerful features of Aura AI including automated workflows, smart lead scoring, and unified inbox.' }
  ]
})
</script>

<template>
  <div class="min-h-screen bg-[#0A0A1A] text-white font-sans selection:bg-[#8C52FF] selection:text-white">
    <AppHeader />

    <main class="pt-24 pb-20">
      <!-- Hero -->
      <div class="text-center px-6 mb-20">
        <h1 class="text-4xl md:text-6xl font-bold mb-6 bg-clip-text text-transparent bg-gradient-to-r from-white to-gray-400">
          Supercharge Your Workflow
        </h1>
        <p class="text-xl text-gray-400 max-w-2xl mx-auto">
          Everything you need to manage customer relationships, automate tasks, and close more deals.
        </p>
      </div>

      <!-- Features -->
      <div class="space-y-12">
        <!-- Automated Workflows -->
        <FeatureSection
          title="Automated Workflows"
          description="Build complex automation flows with our visual drag-and-drop editor. Trigger actions based on user behavior, email interactions, or custom events."
          image-side="left"
        >
          <template #graphic>
            <div class="w-full h-full flex items-center justify-center bg-[#151520] p-8 relative overflow-hidden">
              <!-- Grid Background -->
              <div class="absolute inset-0 opacity-20" style="background-image: radial-gradient(#2E2E3A 1px, transparent 1px); background-size: 20px 20px;"></div>
              
              <div class="relative z-10 flex flex-col items-center gap-6">
                <!-- Trigger Box -->
                <div class="bg-[#1E1E2D] border border-[#2E2E3A] rounded-lg p-4 w-48 shadow-lg flex items-center gap-3">
                  <div class="w-8 h-8 rounded bg-blue-500/20 flex items-center justify-center text-blue-400">
                    <Zap class="w-4 h-4" />
                  </div>
                  <div>
                    <div class="text-xs text-gray-400">Trigger</div>
                    <div class="text-sm font-medium">New Lead</div>
                  </div>
                </div>

                <!-- Arrow -->
                <div class="h-8 w-px bg-[#2E2E3A] relative">
                  <div class="absolute bottom-0 left-1/2 -translate-x-1/2 translate-y-1/2 text-[#2E2E3A]">
                    <ArrowRight class="w-4 h-4 rotate-90" />
                  </div>
                </div>

                <!-- Action Box -->
                <div class="bg-[#1E1E2D] border border-[#8C52FF]/30 rounded-lg p-4 w-48 shadow-lg flex items-center gap-3 relative">
                  <div class="absolute -inset-px bg-gradient-to-r from-[#8C52FF] to-blue-600 rounded-lg opacity-20 blur-sm"></div>
                  <div class="relative flex items-center gap-3 w-full">
                    <div class="w-8 h-8 rounded bg-[#8C52FF]/20 flex items-center justify-center text-[#8C52FF]">
                      <Mail class="w-4 h-4" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-400">Action</div>
                      <div class="text-sm font-medium">Send Email</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </template>
        </FeatureSection>

        <!-- Smart Lead Scoring -->
        <FeatureSection
          title="Smart Lead Scoring"
          description="Stop guessing which leads to prioritize. Our AI analyzes thousands of data points to score leads based on their likelihood to convert."
          image-side="right"
        >
          <template #graphic>
            <div class="w-full h-full flex items-center justify-center bg-[#151520] p-8 relative">
              <div class="bg-[#1E1E2D] border border-[#2E2E3A] rounded-xl p-6 w-64 shadow-2xl relative overflow-hidden">
                <!-- Glow effect -->
                <div class="absolute top-0 right-0 w-32 h-32 bg-[#8C52FF]/10 blur-3xl rounded-full pointer-events-none"></div>

                <div class="flex flex-col items-center text-center">
                  <div class="w-16 h-16 rounded-full bg-gradient-to-br from-gray-700 to-gray-900 border-2 border-[#2E2E3A] flex items-center justify-center mb-3 overflow-hidden">
                    <User class="w-8 h-8 text-gray-400" />
                  </div>
                  <h3 class="text-lg font-bold text-white">Sarah Chen</h3>
                  <p class="text-xs text-gray-400 mb-4">TechVision Inc.</p>

                  <div class="w-full bg-[#0A0A1A] rounded-lg p-3 border border-[#2E2E3A] mb-4">
                    <div class="flex justify-between items-center mb-2">
                      <span class="text-xs text-gray-400">Lead Score</span>
                      <span class="text-sm font-bold text-[#8C52FF]">94/100</span>
                    </div>
                    <div class="w-full h-2 bg-[#2E2E3A] rounded-full overflow-hidden">
                      <div class="h-full bg-[#8C52FF] w-[94%] rounded-full"></div>
                    </div>
                  </div>

                  <div class="flex gap-2 w-full">
                    <button class="flex-1 bg-[#8C52FF] text-white text-xs py-2 rounded hover:bg-[#7B42EE] transition-colors">Contact</button>
                    <button class="flex-1 bg-[#2E2E3A] text-white text-xs py-2 rounded hover:bg-[#3E3E4A] transition-colors">View</button>
                  </div>
                </div>
              </div>
            </div>
          </template>
        </FeatureSection>

        <!-- Unified Inbox -->
        <FeatureSection
          title="Unified Inbox"
          description="Manage all your customer conversations in one place. Connect email, chat, and social media to a single, powerful interface."
          image-side="left"
        >
          <template #graphic>
            <div class="w-full h-full flex items-center justify-center bg-[#151520] p-8">
              <div class="bg-[#1E1E2D] border border-[#2E2E3A] rounded-xl w-full max-w-sm h-64 shadow-xl flex overflow-hidden">
                <!-- Sidebar -->
                <div class="w-1/3 border-r border-[#2E2E3A] bg-[#151520]/50 p-3 flex flex-col gap-3">
                  <div class="w-full h-8 bg-[#2E2E3A] rounded mb-2 opacity-50"></div>
                  <div class="flex items-center gap-2 p-2 rounded bg-[#2E2E3A]/50 border border-[#8C52FF]/30">
                    <div class="w-6 h-6 rounded-full bg-gray-700"></div>
                    <div class="w-12 h-2 bg-gray-600 rounded"></div>
                  </div>
                  <div class="flex items-center gap-2 p-2 rounded hover:bg-[#2E2E3A]/30 opacity-50">
                    <div class="w-6 h-6 rounded-full bg-gray-700"></div>
                    <div class="w-12 h-2 bg-gray-600 rounded"></div>
                  </div>
                  <div class="flex items-center gap-2 p-2 rounded hover:bg-[#2E2E3A]/30 opacity-50">
                    <div class="w-6 h-6 rounded-full bg-gray-700"></div>
                    <div class="w-12 h-2 bg-gray-600 rounded"></div>
                  </div>
                </div>
                <!-- Chat Area -->
                <div class="flex-1 p-4 flex flex-col relative">
                  <div class="flex items-start gap-3 mb-4">
                    <div class="w-8 h-8 rounded-full bg-gray-700 flex-shrink-0"></div>
                    <div class="bg-[#2E2E3A] p-3 rounded-2xl rounded-tl-none text-xs text-gray-300">
                      Hi, I'm interested in the Enterprise plan.
                    </div>
                  </div>
                  <div class="flex items-start gap-3 mb-4 flex-row-reverse">
                    <div class="w-8 h-8 rounded-full bg-[#8C52FF] flex-shrink-0 flex items-center justify-center">
                      <MessageSquare class="w-4 h-4 text-white" />
                    </div>
                    <div class="bg-[#8C52FF]/20 border border-[#8C52FF]/30 p-3 rounded-2xl rounded-tr-none text-xs text-white">
                      Great! I can help you with that.
                    </div>
                  </div>
                  
                  <!-- Input area -->
                  <div class="mt-auto pt-3 border-t border-[#2E2E3A]">
                    <div class="w-full h-8 bg-[#0A0A1A] rounded border border-[#2E2E3A]"></div>
                  </div>
                </div>
              </div>
            </div>
          </template>
        </FeatureSection>

        <!-- Enterprise Security -->
        <FeatureSection
          title="Enterprise Security"
          description="Sleep soundly knowing your data is safe. We provide role-based access control, SSO, and audit logs for complete visibility."
          image-side="right"
        >
          <template #graphic>
            <div class="w-full h-full flex items-center justify-center bg-[#151520] p-8 relative overflow-hidden">
              <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-[#8C52FF]/10 via-transparent to-transparent"></div>
              
              <div class="relative z-10">
                <div class="relative">
                  <Shield class="w-32 h-32 text-[#2E2E3A] fill-[#1E1E2D]" stroke-width="1" />
                  <div class="absolute inset-0 flex items-center justify-center">
                    <Shield class="w-24 h-24 text-[#8C52FF] opacity-20 animate-pulse" />
                  </div>
                  <div class="absolute inset-0 flex items-center justify-center">
                    <div class="bg-[#0A0A1A] p-3 rounded-full border border-[#8C52FF] shadow-[0_0_20px_rgba(140,82,255,0.3)]">
                      <Lock class="w-8 h-8 text-[#8C52FF]" />
                    </div>
                  </div>
                </div>
                
                <div class="absolute -bottom-4 left-1/2 -translate-x-1/2 bg-[#2E2E3A] px-3 py-1 rounded-full border border-[#8C52FF]/30 flex items-center gap-2 whitespace-nowrap">
                  <div class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></div>
                  <span class="text-xs font-medium text-white">System Secure</span>
                </div>
              </div>
            </div>
          </template>
        </FeatureSection>
      </div>

      <!-- CTA -->
      <section class="py-24 px-6">
        <div class="max-w-4xl mx-auto text-center bg-gradient-to-b from-[#151520] to-[#0A0A1A] border border-[#2E2E3A] rounded-3xl p-12 relative overflow-hidden">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full bg-[radial-gradient(circle_at_top,_var(--tw-gradient-stops))] from-[#8C52FF]/20 via-transparent to-transparent pointer-events-none"></div>
          
          <h2 class="text-3xl md:text-5xl font-bold mb-6 relative z-10">Ready to scale your business?</h2>
          <p class="text-xl text-gray-400 mb-10 max-w-xl mx-auto relative z-10">
            Join thousands of fast-growing companies using Aura AI to drive revenue.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center relative z-10">
            <button class="bg-[#8C52FF] hover:bg-[#7B42EE] text-white px-8 py-4 rounded-full font-medium text-lg transition-all shadow-lg shadow-[#8C52FF]/25">
              Start Free Trial
            </button>
            <button class="bg-[#151520] hover:bg-[#1E1E2D] text-white border border-[#2E2E3A] px-8 py-4 rounded-full font-medium text-lg transition-all">
              Schedule Demo
            </button>
          </div>
        </div>
      </section>
    </main>

    <AppFooter />
  </div>
</template>
