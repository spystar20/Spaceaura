<script setup>
import { ArrowUpRight, ArrowLeft, PenTool, TruckElectricIcon } from 'lucide-vue-next';
import approach from '../assets/approach.png'

import Hero from '../../Components/Hero.vue';
import About from '../../Components/About.vue';
import Approach from '../../Components/Approach.vue';
import Project from '../../Components/Project.vue';
import StatSection from '../../Components/StatSection.vue';
import Gallery from '../../Components/Gallery.vue';
import CtaSection from '../../Components/CtaSection.vue';



</script>

<template>
  <div class="w-full min-h-screen flex flex-col gap-5 md:gap-10 overflow-hidden">
    <!-- 1. Hero: Introduces the brand/product immediately -->
    <Hero />

    <!-- 2. About: Builds context right after the hook -->
    <!-- <About /> -->

    <!-- 3. Project / Portfolio: Shows proof of work early to build interest -->
    <!-- <Project /> -->

    <!-- 4. StatSection: Quantifies success / adds social proof -->
    <!-- <StatSection /> -->

    <!-- 5. Approach: Explains process ("How we work") after showing results -->
    <!-- <Approach /> -->

    <!-- 6. Gallery: Rich visual section ("Designed for Every Space") -->
    <Gallery />

    <!-- 7. CtaSection: Final high-converting closure at the very end -->
    <CtaSection />
  </div>
</template>



<style scoped></style>