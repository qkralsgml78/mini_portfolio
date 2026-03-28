<script setup>
import Navbar from './components/Navbar.vue';
import HeroSection from './components/HeroSection.vue';
import AboutSection from './components/AboutSection.vue';
import PortfolioSection from './components/PortfolioSection.vue';
import ContactSection from './components/ContactSection.vue';
</script>

<template>
  <div class="relative min-h-screen font-sans text-slate text-lg md:text-xl overflow-x-hidden">
    <!-- 블러 네온 원 배경: 각 위치에 분산 -->
    <div class="fixed inset-0 -z-20 pointer-events-none">
      <div class="absolute top-0 -left-4 md:w-96 md:h-96 w-72 h-72 bg-purple-500 rounded-full mix-blend-multiply filter blur-[128px] opacity-40 md:opacity-20"></div>
      <div class="absolute top-0 -right-4 w-96 h-96 bg-cyan-500 rounded-full mix-blend-multiply filter blur-[128px] opacity-40 md:opacity-20 hidden sm:block"></div>
      <div class="absolute -bottom-8 left-[-40%] md:left-20 w-96 h-96 bg-blue-500 rounded-full mix-blend-multiply filter blur-[128px] opacity-40 md:opacity-20"></div>
      <div class="absolute -bottom-10 right-20 w-96 h-96 bg-blue-500 rounded-full mix-blend-multiply filter blur-[128px] opacity-20 md:opacity-10 hidden sm:block"></div>
    </div>
    <!-- 그리드 배경 -->
    <div class="fixed inset-0 -z-30" style="background-image:linear-gradient(to right,#4f4f4f10 1px,transparent 1px),linear-gradient(to bottom,#4f4f4f10 1px,transparent 1px);background-size:24px 24px;"></div>
    <Navbar />
    <main class="mx-auto px-6 md:px-36 lg:px-48 max-w-[1600px]">
      <HeroSection />
      <AboutSection />
      <PortfolioSection />
      <ContactSection />
    </main>
    <footer class="flex flex-col items-center justify-center p-4 text-center min-h-[70px]">
      <a href="https://github.com/bchiang7/v4" target="_blank" rel="noopener noreferrer" class="font-mono text-[12px] text-slate hover:text-green transition-colors py-2">
        <div>Designed by Brittany Chiang</div>
        <div class="mt-1">Built by 박민희 (2026)</div>
      </a>
    </footer>
  </div>
</template>

<style>
body {
  font-family: 'Inter', ui-sans-serif, system-ui, sans-serif;
  background: #0a0a13;
}
</style>