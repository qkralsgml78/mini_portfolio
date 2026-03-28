<template>
  <nav class="fixed w-full z-[999] bg-black/40 backdrop-blur-lg border-b border-white/10">
    <div class="max-w-7xl mx-auto flex justify-between items-center py-6 px-8">
      <div class="text-2xl font-bold text-purple-400 tracking-tight select-none">Abhishek Ganvir</div>
      <ul class="flex space-x-10 text-white font-medium">
        <li>
          <a href="#hero" class="relative py-1 px-2 hover:text-purple-400 transition-colors group">
            Home
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded scale-x-100 group-hover:scale-x-100 transition-transform" style="opacity:0.7" v-if="isActive('#hero')"></span>
          </a>
        </li>
        <li>
          <a href="#about" class="relative py-1 px-2 hover:text-purple-400 transition-colors group">
            About
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded scale-x-100 group-hover:scale-x-100 transition-transform" style="opacity:0.7" v-if="isActive('#about')"></span>
          </a>
        </li>
        <li>
          <a href="#portfolio" class="relative py-1 px-2 hover:text-purple-400 transition-colors group">
            Portfolio
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded scale-x-100 group-hover:scale-x-100 transition-transform" style="opacity:0.7" v-if="isActive('#portfolio')"></span>
          </a>
        </li>
        <li>
          <a href="#contact" class="relative py-1 px-2 hover:text-purple-400 transition-colors group">
            Contact
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded scale-x-100 group-hover:scale-x-100 transition-transform" style="opacity:0.7" v-if="isActive('#contact')"></span>
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue';
const current = ref('#hero');
function onScroll() {
  const sections = ['#hero', '#about', '#portfolio', '#contact'];
  for (let i = sections.length - 1; i >= 0; i--) {
    const el = document.querySelector(sections[i]);
    if (el && window.scrollY + 80 >= el.offsetTop) {
      current.value = sections[i];
      break;
    }
  }
}
onMounted(() => {
  window.addEventListener('scroll', onScroll);
});
function isActive(hash) {
  return current.value === hash;
}
</script>

<style scoped>
nav {
  box-shadow: 0 2px 32px 0 rgba(80,0,120,0.08);
}
</style>
