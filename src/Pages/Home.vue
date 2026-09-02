<script setup>
import { ArrowUpRight, ArrowLeft, PenTool, TruckElectricIcon } from 'lucide-vue-next';
import approach from '../assets/approach.png'

import Hero from '../../Components/Hero.vue';
import About from '../../Components/About.vue';
import Approach from '../../Components/Approach.vue';
import Project from '../../Components/Project.vue';
import StatSection from '../../Components/StatSection.vue';



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
        <div class=" px-2 md:p-12 flex  flex-col md:flex-row gap-3">
            <div class="lg:max-w-1/4 flex flex-col gap-4 ">
                <h2
                    class="font-bold font-heading  text-4xl md:text-5xl bg-linear-to-r from-black to-main text-transparent bg-clip-text ">
                    Designed for Every Space
                </h2>
                <p class="text-xs font-medium font-body">Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                    Voluptas magni enim sunt, iusto totam mollitia tempore nisi ad quos expedita! Ipsa, error quas.</p>
                <button class="px-6 py-2 cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in
                 bg-black text-white rounded-full w-1/2 ">Learn More</button>
            </div>
            <ul class="flex flex-col gap-2 flex-1 mt-5">
                <li
                    class="  text-2xl font-medium font-body border-y-[0.2px] border-y-gray-700 py-4 w-full px-8 flex items-center justify-between">
                    Modern Living Rooms
                    <ArrowLeft class="w-5  rotate-130 text-black " />
                </li>
                <li
                    class="  text-2xl font-medium font-body border-y-[0.2px] border-y-gray-700 py-4 w-full px-8 flex items-center justify-between">
                    Modern Living Rooms
                    <ArrowLeft class="w-5  rotate-130 text-black " />
                </li>
                <li
                    class="  text-2xl font-medium font-body border-y-[0.2px] border-y-gray-700 py-4 w-full px-8 flex items-center justify-between">
                    Modern Living Rooms
                    <ArrowLeft class="w-5  rotate-130 text-black " />
                </li>
                <li
                    class="  text-2xl font-medium font-body border-y-[0.2px] border-y-gray-700 py-4 w-full px-8 flex items-center justify-between">
                    Modern Living Rooms
                    <ArrowLeft class="w-5  rotate-130 text-black " />
                </li>

            </ul>
        </div>
        <div class="w-full  ">
            <div class=" hero-img w-full relative flex items-center justify-start bg-cover bg-center min-h-screen bg-no-repeat "
                style="background-image: url(https://i.pinimg.com/1200x/1e/6b/a2/1e6ba2c54b4b7333d8db9e3a43cda791.jpg);">
                <div class="absolute inset-0  bg-linear-to-bl from-white/10 to-black/45"></div>
                <div class=" bg-white/90 flex flex-col rounded-xl md:p-4  w-[60%] mx-3 md:w-1/5 md:mx-12 z-[12]">
                    <img class="rounded-xl aspect-square p-1"
                        src="https://i.pinimg.com/736x/b0/5f/dd/b05fdd196a902ebb945f3f085458aa9b.jpg" alt="">
                    <div class="flex flex-col gap-1 pt-1 md:py-2 ">
                        <h2 class="md:text-xl text-base font-bold font-heading px-1">Modern Living Room Design</h2>
                        <p class="text-xs font-body font-normal px-1">Lorem ipsum dolor sit amet, consectetur adipisicing
                            elit. Magni veritatis repudiandae id.</p>
                        <button class="md:px-6 md:py-2 py-1 md:mt-1 text-xs cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in
                 bg-black text-white rounded-full m-0">Learn More</button>
                    </div>
                </div>

            </div>
        </div>



    </div>



</template>



<style scoped></style>