<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted, onUnmounted } from 'vue';
import StatCard from '../src/components/StatCard.vue';
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
    let mm ;
    mm = gsap.matchMedia()
    mm.add('(min-width:768px)',()=>{
        const tl = gsap.timeline({scrollTrigger:{trigger:".statSection",start:"top 80%",end:"top 20%",scrub:2,markers:true}})

        tl.fromTo('.stat-mainheading ',{
            x:50,opacity:0
        },{x:0,opacity:1})
        .fromTo(
    ".meaningful-image-wrapper",
    {
        width: 0,
        opacity: 0
    },
    {
        width: window.innerWidth >= 768 ? "10rem" : "3.75rem",
        opacity: 1,
        ease: "none",
        // scrollTrigger: {
        //     trigger: ".meaningful-image-wrapper",
        //     start: "top 85%",
        //     end: "top 55%",
        //     scrub: true,
        //     markers: true
        // }
    },"<"
)
.fromTo(
    ".stat-line-text",
    {
        x: 50,
        opacity: 0
    },
    {
        x: 0,
        opacity: 1,
        ease: "none"
    },"<"
)
    })

})
</script>
<template>
     <div class="md:px-5 px-2 py-5 grid grid-cols-1 md:grid-cols-2 gap-6 statSection">
            <div class="w-full order-2 md:order-1  p-3 items-center gap-5 rounded-2xl  bg-linear-to-b from-black to-main text-gray-100 grid md:grid-cols-2 min-h-[calc(100vh-40px)]">
                <div class="flex flex-col gap-8 md:mb-16">
                    <StatCard v-for="(item, index) in [1,2,3]" :key="index" :heading="'bespoke concepts'" :description="'Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.'"/>
                </div>
                <div class="flex flex-col gap-8 md:mt-16">
                <StatCard v-for="(item, index) in [1,2,3]" :key="index" :heading="'bespoke concepts'" :description="'Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.'"/>

                </div>
            </div>
            <div class=" px-3 box-border w-full flex flex-col justify-end items-end-safe gap-4">
                <!-- heading -->
                <div class="flex flex-col items-end w-full gap-4 ">

                 <h2 class="flex flex-wrap justify-end font-heading text-3xl md:text-5xl font-semibold capitalize gap-x-4 leading-tight overflow-hidden"
>
    <div class="text-center overflow-hidden ">
        <span class="stat-mainheading inline-block">
        Where Detail Shapes
        </span>
    </div>

    <div class="flex items-center gap-4 ">
        <span class="italic">
            Meaningful
        </span>

        <div
            class="meaningful-image-wrapper overflow-hidden rounded-full md:w-40 md:h-20 w-15 h-8 shrink-0"
        >
            <img
                class="meaningful-image w-full h-full object-cover"
                src="https://i.pinimg.com/736x/db/48/75/db4875081f8248aa02d8420912fcf84e.jpg"
                alt=""
            />
        </div>

        <span class="italic  ">
            Design
        </span>
    </div>
</h2>
                    <h6 class="capitalize font-body font-bold flex items-center gap-1 md:gap-2 text-sm text-end overflow-hidden  
                    ">
                        <ArrowLeft class="w-5 text-black" /><span class=" h-[0.5px] bg-black w-25 md:w-50 stat-line"></span> <p class="stat-line-text">inside the
                        process</p>
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
</template>
<style scoped></style>