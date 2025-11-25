<script setup lang="ts">
import { Check } from 'lucide-vue-next'

interface Props {
  tier: string
  price: string
  features: string[]
  highlight?: boolean
  period?: 'monthly' | 'yearly'
}

const props = withDefaults(defineProps<Props>(), {
  highlight: false,
  period: 'monthly'
})
</script>

<template>
  <div 
    class="relative p-8 rounded-2xl border transition-all duration-300 flex flex-col h-full"
    :class="[
      props.highlight 
        ? 'bg-[#151520] border-[#8C52FF] shadow-[0_0_30px_rgba(140,82,255,0.15)] scale-105 z-10' 
        : 'bg-[#0A0A1A] border-[#2E2E3A] hover:border-gray-700'
    ]"
  >
    <!-- Highlight Badge -->
    <div v-if="props.highlight" class="absolute -top-4 left-1/2 -translate-x-1/2">
      <span class="bg-[#8C52FF] text-white text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider">
        Most Popular
      </span>
    </div>

    <!-- Header -->
    <div class="mb-8">
      <h3 class="text-xl font-medium text-white mb-2">{{ props.tier }}</h3>
      <div class="flex items-baseline gap-1">
        <span class="text-4xl font-bold text-white">{{ props.price }}</span>
        <span v-if="props.price !== 'Custom'" class="text-gray-400">/{{ props.period === 'monthly' ? 'mo' : 'yr' }}</span>
      </div>
    </div>

    <!-- Features -->
    <ul class="space-y-4 mb-8 flex-1">
      <li v-for="(feature, index) in props.features" :key="index" class="flex items-start gap-3">
        <Check class="w-5 h-5 text-[#8C52FF] shrink-0 mt-0.5" />
        <span class="text-gray-300 text-sm leading-relaxed">{{ feature }}</span>
      </li>
    </ul>

    <!-- Action -->
    <button 
      class="w-full py-3 px-6 rounded-lg font-medium transition-all duration-200"
      :class="[
        props.highlight
          ? 'bg-[#8C52FF] hover:bg-[#7B42EE] text-white shadow-lg shadow-[#8C52FF]/25'
          : 'bg-[#151520] hover:bg-[#1E1E2D] text-white border border-[#2E2E3A]'
      ]"
    >
      {{ props.price === 'Custom' ? 'Contact Sales' : 'Get Started' }}
    </button>
  </div>
</template>
