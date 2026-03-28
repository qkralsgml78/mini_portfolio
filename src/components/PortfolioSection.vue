<template>
  <section id="portfolio" class="py-20 bg-[#0a192f] text-[#ccd6f6]">
    <div class="container mx-auto px-6">
      <h2 class="text-3xl font-bold mb-10 text-[#64ffda]">Portfolio</h2>
      <div class="grid md:grid-cols-2 gap-8">
        <!-- Example Project Card -->
        <div class="bg-[#112240] rounded-lg shadow p-6 img-wrapper">
          <img src="/src/assets/hero.png" alt="Project 1" class="w-full h-48 object-cover rounded mb-4" />
          <h3 class="text-xl font-semibold mb-2">Project Title</h3>
          <p class="text-[#8892b0] mb-4">Short project description goes here.</p>
          <a href="#" class="text-[#64ffda] hover:underline">View Details</a>
        </div>
        <!-- Add more project cards as needed -->
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
</style>
