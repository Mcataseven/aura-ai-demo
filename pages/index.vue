
<script setup lang="ts">
import AppHeader from '../components/AppHeader.vue'
import HeroSection from '../components/HeroSection.vue'
import SocialProof from '../components/SocialProof.vue'
import AppFooter from '../components/AppFooter.vue';

</script>



<style>
@import '../assets/css/main.css';
</style>


<template>



  <div class="antialiased">
    <AppHeader />
    <main>

      <HeroSection />
      <SocialProof />
    </main>
    <AppFooter />
  </div>



</template>
