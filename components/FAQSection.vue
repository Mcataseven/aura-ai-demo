<script setup lang="ts">
import { ref } from 'vue'
import { ChevronDown } from 'lucide-vue-next'

const faqs = [
  {
    question: "How does the AI lead scoring work?",
    answer: "Our AI analyzes over 50 data points including email interactions, website behavior, and firmographic data to assign a predictive score to every lead, helping you prioritize the most promising opportunities."
  },
  {
    question: "Can I integrate Aura AI with my existing tools?",
    answer: "Yes! Aura AI offers native integrations with popular tools like Slack, Gmail, Outlook, and major CRMs. We also provide a comprehensive API for custom integrations."
  },
  {
    question: "Is my data secure?",
    answer: "Security is our top priority. We use enterprise-grade encryption for data at rest and in transit. We are SOC 2 Type II compliant and regularly undergo third-party security audits."
  },
  {
    question: "What happens if I exceed my plan limits?",
    answer: "We'll notify you when you're approaching your limits. You can choose to upgrade your plan or pay for overages. We never pause your service without ample warning."
  }
]

const openIndex = ref<number | null>(0)

const toggle = (index: number) => {
  openIndex.value = openIndex.value === index ? null : index
}
</script>

<template>
  <section class="py-20 px-6 max-w-3xl mx-auto">
    <div class="text-center mb-12">
      <h2 class="text-3xl font-bold text-white mb-4">Frequently Asked Questions</h2>
      <p class="text-gray-400">Everything you need to know about Aura AI</p>
    </div>

    <div class="space-y-4">
      <div 
        v-for="(faq, index) in faqs" 
        :key="index"
        class="border border-[#2E2E3A] rounded-xl bg-[#151520] overflow-hidden transition-all duration-200"
        :class="{ 'border-[#8C52FF]/50': openIndex === index }"
      >
        <button 
          @click="toggle(index)"
          class="w-full flex items-center justify-between p-6 text-left hover:bg-[#1E1E2D] transition-colors"
        >
          <span class="font-medium text-white text-lg">{{ faq.question }}</span>
          <ChevronDown 
            class="w-5 h-5 text-gray-400 transition-transform duration-300"
            :class="{ 'rotate-180 text-[#8C52FF]': openIndex === index }"
          />
        </button>
        
        <div 
          v-show="openIndex === index"
          class="px-6 pb-6 pt-0 text-gray-400 leading-relaxed"
        >
          {{ faq.answer }}
        </div>
      </div>
    </div>
  </section>
</template>
