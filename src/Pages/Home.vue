<script setup>
import { ArrowUpRight, ArrowLeft, PenTool, TruckElectricIcon } from 'lucide-vue-next';
import approach from '../assets/approach.png'

import Hero from '../../Components/Hero.vue';
import About from '../../Components/About.vue';
import Approach from '../../Components/Approach.vue';
import Project from '../../Components/Project.vue';



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
        <div class="md:px-5 px-2 pb-12 grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="w-full order-2 md:order-1  p-6 items-center gap-5 rounded-2xl  bg-linear-to-b from-black to-main text-gray-100 grid md:grid-cols-2">
                <div class="flex flex-col gap-8 md:mb-16">
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                </div>
                <div class="flex flex-col gap-8 md:mt-16">
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                    <div
                        class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">Bespoke Concepts</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">Lorem ipsum dolor sit amet
                            consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.</p>
                    </div>
                </div>
            </div>
            <div class=" px-3 box-border w-full flex flex-col justify-end items-end-safe gap-4">
                <!-- heading -->
                <div class="flex flex-col items-end w-full gap-4 ">

                    <h2
                        class=" flex flex-wrap justify-end font-heading text-3xl md:text-5xl font-semibold capitalize gap-x-4  leading-tight ">
                        <span class="text-center">Where Detail Shapes</span>
                        <div class="flex gap-4"><span class="italic  ">Meaningful</span> <img
                                class="md:w-40  md:h-20 w-15 h-8 object-cover  rounded-full"
                                src="https://i.pinimg.com/736x/db/48/75/db4875081f8248aa02d8420912fcf84e.jpg" alt="">
                        </div>
                        <span class="italic"> Design </span>
                    </h2>
                    <h6 class="capitalize font-body font-bold flex items-center gap-1 md:gap-2 text-sm text-end">
                        <ArrowLeft class="w-5 text-black" /><span class=" h-[0.5px] bg-black w-25 md:w-50"></span>inside the
                        process
                    </h6>

                    <div class="flex items-end flex-col md:flex-row-reverse gap-3 ">
                        <p class="max-w-11/12  md:w-[65%] text-xs font-body  text-end">
                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde rem accusamus, fuga saepe aut
                            eos optio repudiandae Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt enim
                            facere architecto.
                        </p>
                        <button class="px-6 py-2 cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in
                 bg-black text-white rounded-full">Learn More</button>
                    </div>
                </div>
                <!-- stat -->
                <div class="flex flex-wrap items-center justify-center gap-4 py-6">
                    <div class="flex flex-col items-center  gap-1 px-3 mx:px-6 ">
                        <h2 class="text-3xl md:text-4xl font-bold font-projects">150+</h2>
                        <p class="md:text-base text-xs font-medium">Curated Interiors</p>
                    </div>
                    <span class="w-[0.5px] h-5 bg-gray-400 flex self-center"></span>
                    <div class="flex flex-col items-center  gap-1  px-3 mx:px-6 ">
                        <h2 class="text-3xl md:text-4xl font-bold font-projects">50+</h2>
                        <p class="md:text-base text-xs font-medium">Happy Customers</p>
                    </div>
                    <span class="w-[0.5px] h-5 bg-gray-400 flex self-center"></span>
                    <div class="flex flex-col items-center  gap-1  px-3 mx:px-6">
                        <h2 class="text-3xl md:text-4xl font-bold font-projects">10+</h2>
                        <p class="md:text-base text-xs font-medium">Industry Expertise</p>
                    </div>
                </div>
                <div class="w-full">
                    <img class="rounded-2xl h-[280px] object-cover w-full"
                        src="https://i.pinimg.com/1200x/e5/b0/c7/e5b0c7297721a4be2f3e258a3afc5587.jpg" alt="">
                </div>
            </div>

        </div>

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