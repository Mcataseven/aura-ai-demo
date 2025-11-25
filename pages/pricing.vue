<script setup lang="ts">
import { ref } from 'vue'
import PricingCard from '~/components/PricingCard.vue'
import FAQSection from '~/components/FAQSection.vue'
import AppHeader from '~/components/AppHeader.vue'
import AppFooter from '~/components/AppFooter.vue'

useHead({
  title: 'Pricing - Aura AI',
  meta: [
    { name: 'description', content: 'Simple, transparent pricing for teams of all sizes.' }
  ]
})

const isAnnual = ref(true)
</script>

<template>
  <div class="min-h-screen bg-[#0A0A1A] text-white font-sans selection:bg-[#8C52FF] selection:text-white">
    <AppHeader />

    <main class="pt-24 pb-20">
      <!-- Header -->
      <div class="text-center px-6 mb-16">
        <h1 class="text-4xl md:text-6xl font-bold mb-6 bg-clip-text text-transparent bg-gradient-to-r from-white to-gray-400">
          Simple, Transparent Pricing
        </h1>
        <p class="text-xl text-gray-400 mb-10">
          Choose the plan that's right for your business.
        </p>

        <!-- Toggle -->
        <div class="flex items-center justify-center gap-4">
          <span class="text-sm font-medium" :class="!isAnnual ? 'text-white' : 'text-gray-500'">Monthly</span>
          <button 
            @click="isAnnual = !isAnnual"
            class="relative w-14 h-8 bg-[#151520] border border-[#2E2E3A] rounded-full transition-colors focus:outline-none"
          >
            <div 
              class="absolute top-1 left-1 w-6 h-6 bg-[#8C52FF] rounded-full transition-transform duration-300 shadow-md"
              :class="{ 'translate-x-6': isAnnual }"
            ></div>
          </button>
          <span class="text-sm font-medium" :class="isAnnual ? 'text-white' : 'text-gray-500'">
            Yearly <span class="text-[#8C52FF] text-xs ml-1 font-bold">SAVE 20%</span>
          </span>
        </div>
      </div>

      <!-- Pricing Cards -->
      <div class="max-w-7xl mx-auto px-6 mb-32">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-start">
          <PricingCard
            tier="Starter"
            price="$0"
            :period="isAnnual ? 'yearly' : 'monthly'"
            :features="[
              'Up to 1,000 contacts',
              'Basic lead scoring',
              'Email integration',
              '1 User seat',
              'Community support'
            ]"
          />

          <PricingCard
            tier="Pro"
            :price="isAnnual ? '$39' : '$49'"
            :period="isAnnual ? 'yearly' : 'monthly'"
            :highlight="true"
            :features="[
              'Up to 10,000 contacts',
              'Advanced AI scoring',
              'Automated workflows',
              '5 User seats',
              'Priority email support',
              'API Access'
            ]"
          />

          <PricingCard
            tier="Enterprise"
            price="Custom"
            :features="[
              'Unlimited contacts',
              'Custom AI models',
              'Dedicated success manager',
              'SSO & Advanced Security',
              'Unlimited seats',
              '24/7 Phone support',
              'SLA Guarantee'
            ]"
          />
        </div>
      </div>

      <!-- FAQ -->
      <FAQSection />
    </main>

    <AppFooter />
  </div>
</template>
