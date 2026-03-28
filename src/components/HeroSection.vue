<template>
  <section id="hero" class="relative min-h-screen flex flex-col justify-center items-start px-6 pt-36 overflow-hidden">
    <div class="hero-bg"></div>
    <div class="relative z-10 w-full max-w-3xl">
      <div class="mb-4">
        <span class="inline-flex items-center px-4 py-1 rounded-full border border-purple-400 bg-purple-900/30 text-purple-300 text-sm font-mono shadow-md">
          <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M13 16h-1v-4h-1m1-4h.01"/></svg>
          Ready to Innovate
        </span>
      </div>
      <h1 class="text-5xl md:text-7xl font-extrabold text-white mb-2 leading-tight">
        Full Stack <span class="text-purple-400">Developer</span>
      </h1>
      <div class="text-2xl md:text-3xl font-mono text-purple-200 mb-4 min-h-[2.5rem]">
        <span ref="typeTarget"></span>
      </div>
      <p class="text-lg text-gray-300 mb-8">Enhancing digital experiences that are smooth, scalable, and made to impress.</p>
      <div class="flex flex-wrap gap-3 mb-8">
        <span class="px-4 py-1 rounded-full bg-[#181926] text-gray-200 text-sm font-mono">Vue.js</span>
        <span class="px-4 py-1 rounded-full bg-[#181926] text-gray-200 text-sm font-mono">Javascript</span>
        <span class="px-4 py-1 rounded-full bg-[#181926] text-gray-200 text-sm font-mono">Node.js</span>
        <span class="px-4 py-1 rounded-full bg-[#181926] text-gray-200 text-sm font-mono">PostgreSQL</span>
      </div>
      <div class="flex gap-4 mb-8">
        <a href="#portfolio" class="px-8 py-3 rounded bg-purple-700 text-white font-bold shadow hover:bg-purple-600 transition flex items-center gap-2">Projects <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M14 3h7v7m0 0L10 21l-7-7 11-11z"/></svg></a>
        <a href="#contact" class="px-8 py-3 rounded bg-[#181926] text-white font-bold shadow hover:bg-[#23263a] transition flex items-center gap-2">Contact <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M21 10.5V6a2 2 0 0 0-2-2H5a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h7.5"/></svg></a>
      </div>
      <div class="flex gap-6 mt-2">
        <a href="#" class="text-gray-300 hover:text-purple-400 transition"><svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M16 8a6 6 0 1 1-12 0 6 6 0 0 1 12 0z"/><path d="M2 22c0-4 8-6 8-6s8 2 8 6"/></svg></a>
        <a href="#" class="text-gray-300 hover:text-purple-400 transition"><svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M16 8a6 6 0 1 1-12 0 6 6 0 0 1 12 0z"/><path d="M2 22c0-4 8-6 8-6s8 2 8 6"/></svg></a>
        <a href="#" class="text-gray-300 hover:text-purple-400 transition"><svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M16 8a6 6 0 1 1-12 0 6 6 0 0 1 12 0z"/><path d="M2 22c0-4 8-6 8-6s8 2 8 6"/></svg></a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue';
const typeTarget = ref(null);
const texts = [
  'Creative Coder',
  'Problem Solver',
  'UI/UX Enthusiast',
  'Open Source Contributor'
];
let idx = 0, char = 0, isDeleting = false;
function typeEffect() {
  if (!typeTarget.value) return;
  let current = texts[idx % texts.length];
  if (isDeleting) {
    char--;
  } else {
    char++;
  }
  typeTarget.value.textContent = current.substring(0, char);
  if (!isDeleting && char === current.length) {
    setTimeout(() => { isDeleting = true; typeEffect(); }, 1200);
    return;
  }
  if (isDeleting && char === 0) {
    isDeleting = false;
    idx++;
  }
  setTimeout(typeEffect, isDeleting ? 60 : 120);
}
onMounted(() => {
  typeEffect();
});
</script>

<style scoped>
@import '../assets/hero-bg.css';
</style>
