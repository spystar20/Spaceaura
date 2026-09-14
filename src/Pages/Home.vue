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
    <div class="w-full min-h-screen flex flex-col gap-5 md:gap-10  overflow-hidden">
  
        <!-- hero-section -->
       <Hero/>
        <!-- about -->
       <About/>
        <!-- approach -->
      <Approach/>
        <!-- project -->
        <Project/>

        <!-- stats section -->
   <StatSection/>

        <!-- Designed for Every Space -->
      <Gallery/>
      <CtaSection/>


    </div>



</template>



<style scoped></style>