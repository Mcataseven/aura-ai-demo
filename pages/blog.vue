<script setup lang="ts">
const posts = [
  {
    id: 1,
    category: 'Automation',
    title: 'How AI is Revolutionizing Sales Workflows',
    image: 'https://images.unsplash.com/photo-1488229297570-58520851e868?auto=format&fit=crop&q=80&w=800',
    readTime: '5 min read'
  },
  {
    id: 2,
    category: 'Productivity',
    title: 'The Future of CRM: Beyond Data Entry',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&q=80&w=800',
    readTime: '4 min read'
  },
  {
    id: 3,
    category: 'Sales Strategy',
    title: 'Closing Deals Faster with Predictive Analytics',
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&q=80&w=800',
    readTime: '6 min read'
  },
  {
    id: 4,
    category: 'AI Insights',
    title: 'Understanding Customer Sentiment with NLP',
    image: 'https://images.unsplash.com/photo-1555949963-ff9fe0c870eb?auto=format&fit=crop&q=80&w=800',
    readTime: '7 min read'
  },
  {
    id: 5,
    category: 'Growth',
    title: 'Scaling Your Sales Team Efficiently',
    image: 'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=800',
    readTime: '5 min read'
  },
  {
    id: 6,
    category: 'Technology',
    title: 'Integrating Aura AI with Your Tech Stack',
    image: 'https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&q=80&w=800',
    readTime: '4 min read'
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
            <h1 class="mb-4">Latest from Aura AI</h1>
            <p class="text-xl text-gray-400">Insights on sales, AI, and productivity to help you grow better.</p>
          </div>
        </div>
      </section>

      <!-- Blog Grid -->
      <section class="section pb-32">
        <div class="container">
          <div class="grid grid-3 gap-8">
            <article v-for="post in posts" :key="post.id" class="card rounded-xl overflow-hidden hover:transform hover:-translate-y-1 transition-all duration-300">
              <div class="aspect-video relative overflow-hidden">
                <img :src="post.image" :alt="post.title" class="object-cover w-full h-full hover:scale-105 transition-transform duration-500">
              </div>
              <div class="p-6">
                <div class="flex items-center justify-between mb-3">
                  <span class="text-xs font-semibold text-primary uppercase tracking-wider">{{ post.category }}</span>
                  <span class="text-xs text-gray-500">{{ post.readTime }}</span>
                </div>
                <h3 class="text-xl font-bold mb-4 leading-tight">{{ post.title }}</h3>
                <a href="#" class="text-sm font-medium text-white hover:text-primary transition-colors flex items-center gap-1">
                  Read more 
                  <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
                </a>
              </div>
            </article>
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
