<script setup>
import { ArrowUpRight } from 'lucide-vue-next';

defineProps({
  project: Object
});
</script>

<template>
  <div class="relative group overflow-hidden rounded-3xl w-full h-full min-h-[280px]">
    <!-- Background Image -->
    <div 
      :style="{ backgroundImage: `url(${project.img})` }" 
      class="absolute inset-0 w-full h-full bg-cover bg-center projectCard-image transition-transform duration-700 ease-out group-hover:scale-105"
    ></div>

    <!-- Gradient Overlay & Reveal Container -->
    <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/40 to-transparent p-5 flex flex-col justify-end transition-colors duration-300 group-hover:bg-black/40">
      <div class="flex justify-between items-center w-full">
        <h1 class="text-xl lg:text-2xl font-semibold text-white">{{ project.title }}</h1>
        <span class="text-black bg-white rounded-full p-1.5 hover:scale-110 transition-transform cursor-pointer">
          <ArrowUpRight class="w-4 h-4" />
        </span>
      </div>

      <!-- CSS Height & Opacity Expansion on Hover -->
      <div class="max-h-0 opacity-0 group-hover:max-h-36 group-hover:opacity-100 transition-all duration-500 ease-in-out overflow-hidden">
        <p class="font-body text-gray-300 text-xs py-2">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cumque magni alias ipsam?
        </p>
        <div class="flex items-center gap-2 pt-1">
          <button class="px-3 py-1 text-xs text-white border border-white/70 rounded-full hover:bg-white hover:text-black transition-all">View</button>
          <button class="px-3 py-1 text-xs text-white border border-white/70 rounded-full hover:bg-white hover:text-black transition-all">Contact</button>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped></style>