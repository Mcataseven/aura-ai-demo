<template>
  <div class="min-h-screen bg-[#0A0A1A] text-white font-sans selection:bg-[#8C52FF] selection:text-white flex items-center justify-center p-6 relative overflow-hidden">
    <!-- Background Mesh/Gradient -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-[#8C52FF]/20 rounded-full blur-[120px]"></div>
      <div class="absolute bottom-[-10%] right-[-10%] w-[40%] h-[40%] bg-blue-600/10 rounded-full blur-[120px]"></div>
    </div>

    <!-- Content -->
    <div class="w-full max-w-md relative z-10">
      <slot />
    </div>
  </div>
</template>
