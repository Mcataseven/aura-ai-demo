<script setup lang="ts">
interface Props {
  title: string
  description: string
  imageSide?: 'left' | 'right'
  imageSrc?: string
}

const props = withDefaults(defineProps<Props>(), {
  imageSide: 'left',
  imageSrc: ''
})
</script>

<template>
  <section class="py-20 px-6 md:px-12 max-w-7xl mx-auto">
    <div 
      class="flex flex-col md:flex-row items-center gap-12 md:gap-20"
      :class="{ 'md:flex-row-reverse': props.imageSide === 'right' }"
    >
      <!-- Image/Graphic Side -->
      <div class="w-full md:w-1/2">
        <div class="relative group">
          <div class="absolute -inset-1 bg-gradient-to-r from-[#8C52FF] to-blue-600 rounded-2xl blur opacity-25 group-hover:opacity-50 transition duration-1000 group-hover:duration-200"></div>
          <div class="relative rounded-2xl overflow-hidden border border-[#2E2E3A] bg-[#151520] aspect-video flex items-center justify-center">
            <img 
              v-if="props.imageSrc"
              :src="props.imageSrc" 
              :alt="props.title"
              class="w-full h-full object-cover opacity-90 hover:opacity-100 transition-opacity duration-500"
            />
            <slot v-else name="graphic"></slot>
          </div>
        </div>
      </div>

      <!-- Content Side -->
      <div class="w-full md:w-1/2 space-y-6">
        <h2 class="text-3xl md:text-4xl font-bold text-white leading-tight">
          {{ props.title }}
        </h2>
        <p class="text-lg text-gray-400 leading-relaxed">
          {{ props.description }}
        </p>
        <div class="pt-4">
          <slot name="cta"></slot>
        </div>
      </div>
    </div>
  </section>
</template>
