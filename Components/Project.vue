<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted } from 'vue';
gsap.registerPlugin(ScrollTrigger)
import ProjectCard from '../src/components/ProjectCard.vue';
import { Col1 ,Col2} from '../src/data/Project'
import { ArrowUpRight } from 'lucide-vue-next';
;
onMounted(()=>{
    let mm = gsap.matchMedia()
    mm.add("(min-width:768px)",()=>{
const tl = gsap.timeline({scrollTrigger:{start:"top bottom",end:"bottom bottom",scrub:true,trigger:".project-container",markers:true}})
tl.fromTo(".project-heading",{
    yPercent:100,ease:"power3.in"
},{yPercent:0})
.fromTo(".project-desc",{
    yPercent:100,ease:"power3.in"
},{yPercent:0},"<")

.fromTo(".projectCard-image",{backgroundPositionY:100,},{backgroundPositionY:0})

    })
    
    
})
</script>
<template>
      <div class="px-2 py-5 md:px-5 project-container">
            <!-- heading -->
            <div class="flex flex-col md:flex-row gap-3 md:gap-12 justify-between items-end md:items-start w-full">
                <div class="md:flex-5 overflow-hidden">
                    <h2
                        class="font-bold  font-heading text-4xl md:text-5xl bg-linear-to-r from-black to-main text-transparent bg-clip-text project-heading">
                        Explore Our Collection
                    </h2>

                </div>
                <div class="md:flex-4 overflow-hidden">
                    <p class="md:text-end font-body font-medium text-xs md:text-sm  project-desc">
                        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rerum possimus atque dolores quasi
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. A
                    </p>

                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-4 gap-5 py-10 w-full min-h-screen">
                <div class="grid grid-cols-1  md:grid-cols-1 h-full gap-3 ">
                    <ProjectCard v-for="item in Col1" :key="item.id" :project="item" />
                </div>
                <!-- coloumn-2   -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-1 md:col-span-2 h-full gap-3 box-border ">
                    <div class=" flex-6 relative group overflow-hidden rounded-3xl box-border ">
                        <div style="background-image: url(https://i.pinimg.com/1200x/a3/1f/d3/a31fd30764e7b6c3652bbcf30be59db9.jpg);"
                            class="w-full h-[300px] projectCard-image md:h-full bg-cover bg-center rounded-3xl group-hover:scale-105 transition transform duration-500 ease-in">
                        </div>
                        <div
                            class=" w-full h-auto hover:bg-black/30 ease-in duration-300 transition-all rounded-2xl bg-linear-to-t from-black/90  md:from-0% via-black/40  md:via-25% to-transparent md:to-30% absolute inset-0 flex items-end justify-center  md:py-3 p-2 ">
                            <div class="transform md:translate-y-1/2 md:group-hover:translate-y-0 transition duration-300">
                                <div class="flex  justify-between items-center w-full">
                                    <h1 class="text-2xl md:text-3xl font-projects font-semibold  text-white"> Velvet Dusk Interiors
                                    </h1>
                                    <span class="  text-black bg-white rounded-full p-1 md:p-2 ">
                                        <ArrowUpRight
                                            class="hover:scale-125 transition-all ease-in duration-200 cursor-pointer" />
                                    </span>
                                </div>
                                <div class="md:opacity-0 md:group-hover:opacity-100 transition duration-300 md:mt-3">

                                    <p class="font-body text-white text-xs md:text-sm py-2 text-center">Lorem ipsum dolor sit amet,
                                        consectetur
                                        adipisicing elit. Cumque magni alias ipsam?</p>
                                    <!-- buttons -->
                                    <div class="flex items-center justify-center  gap-3 py-2 w-full">
                                        <button
                                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">view</button>
                                        <button
                                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">contact</button>
                                        <button
                                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">learn</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- row-2 -->
                    <div class="flex-4 flex flex-col md:flex-row  gap-5">
                        <div class=" w-full relative group overflow-hidden rounded-3xl">
                            <div style="background-image: url(https://i.pinimg.com/736x/1e/8b/5e/1e8b5e3b25be07a2114d891185a2263d.jpg);"
                                class="w-full bg-cover projectCard-image bg-center rounded-3xl h-[300px] md:h-full group-hover:scale-105 transition transform duration-500 ease-in">
                            </div>
                            <div
                                class=" w-full h-auto hover:bg-black/30 ease-in duration-300 transition-all rounded-2xl bg-linear-to-t from-black/90 md:from-0% via-black/40 md:via-25% to-transparent md:to-30% absolute inset-0 flex items-end justify-between md:py-3 p-2 md:px-6">
                                <div
                                    class="transform md:translate-y-[65%] group-hover:translate-y-0 transition duration-300">
                                    <div class="flex  justify-between items-center">
                                        <h1 class=" text-2xl md:text-3xl font-projects font-semibold text-white">Coal & Concrete</h1>
                                        <span class=" text-black bg-white rounded-full p-1 md:p-2 ">
                                            <ArrowUpRight
                                                class="hover:scale-125 transition-all ease-in duration-200 cursor-pointer" />
                                        </span>
                                    </div>
                                    <div class="md:opacity-0 group-hover:opacity-100 transition duration-300 md:mt-3">

                                        <p class="font-body text-white text-xs md:text-sm py-2 text-center">Lorem ipsum dolor sit
                                            amet, consectetur
                                            adipisicing elit. Cumque magni alias ipsam?</p>
                                        <!-- buttons -->
                                        <div class="flex items-center justify-center  gap-3 py-2 w-full">
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">view</button>
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">contact</button>
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">learn</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="w-full relative group overflow-hidden rounded-3xl">
                            <div style="background-image: url(https://i.pinimg.com/736x/e4/fe/01/e4fe01b5a543853d5e88e67e0ea0a27a.jpg);"
                                class="w-full bg-cover projectCard-image bg-center rounded-3xl h-[300px] md:h-full group-hover:scale-105 transition transform duration-500 ease-in  projectCard-image">
                            </div>
                            <div
                                class=" w-full h-auto hover:bg-black/30 ease-in duration-300 transition-all rounded-2xl bg-linear-to-t from-black/90 md:from-0% via-black/40 md:via-25% to-transparent md:to-30% absolute inset-0 flex items-end justify-between p-2 md:py-3 md:px-6">
                                <div
                                    class="transform md:translate-y-[65%] group-hover:translate-y-0 transition duration-300">
                                    <div class="flex  justify-between items-center ">
                                        <h1 class="text-2xl md:text-3xl font-projects font-semibold  text-white">The Ember House
                                        </h1>
                                        <span class="  text-black bg-white rounded-full p-1 md:p-2 ">
                                            <ArrowUpRight
                                                class="hover:scale-125 transition-all ease-in duration-200 cursor-pointer" />
                                        </span>
                                    </div>
                                    <div class="md:opacity-0 group-hover:opacity-100 transition duration-300 md:mt-3">

                                        <p class="font-body text-white text-xs md:text-sm py-2 text-center">Lorem ipsum dolor sit
                                            amet, consectetur
                                            adipisicing elit. Cumque magni alias ipsam?</p>
                                        <!-- buttons -->
                                        <div class="flex items-center justify-center  gap-3 py-2 w-full">
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">view</button>
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">contact</button>
                                            <button
                                                class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">learn</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-1 h-full gap-3 ">

                    <ProjectCard v-for="item in Col2" :key="item.id" :project="item" />

                </div>


            </div>
        </div>
</template>
<style scoped></style>