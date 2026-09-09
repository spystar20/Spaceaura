<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted, onUnmounted } from 'vue';
import StatCard from '../src/components/StatCard.vue';
import SplitType from 'split-type';
gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
    let mm;
    mm = gsap.matchMedia()
    const split = new SplitType(".number-stat", { types: 'chars' })
    const splitText = new SplitType(".number-text-stat", { types: "chars" })
    const statImg = gsap.utils.toArray(".stat-image")

    mm.add('(min-width:768px)', () => {
        const tl = gsap.timeline({ scrollTrigger: { trigger: ".statSection", start: "top 85%", end: "top 5%", scrub:  2.5,markers:true} })
        gsap.set(statImg.slice(1), {
            clipPath: "inset(100% 0% 0% 0%)"
        })
        const imageTl = gsap.timeline({
            scrollTrigger: {
                trigger: ".stat-image-wrapper", start: "top 80%", once: true
            }
        })
        statImg.slice(1).forEach(img => {
            imageTl.to(img, {
                clipPath: 'inset(0% 0% 0% 0%)', ease: "power2.inOut", delay:1, duration: 0.8
            })
        })
            tl.to({}, { duration: 1 })
            .fromTo('.stat-mainheading ', {
                x: 120, opacity: 0
            }, { x: 0, opacity: 1, duration: 1.5, ease: "none" })
            .fromTo(
                ".meaningful-image-wrapper",
                {
                    width: 0,
                    opacity: 0
                },
                {
                    width: window.innerWidth >= 768 ? "10rem" : "3.75rem",
                    opacity: 1,
                    ease: "none",duration:1.5
                }, 
            )
.from(".img-text",{
    opacity:0,duration:0.5,ease:'none'
},"-=1.3")
            .fromTo(
                ".stat-line-text",
                {
                    x: 50,
                    opacity: 0
                },
                {
                    x: 0,
                    opacity: 1,
                    ease: "none",
                    duration: 0.4
                },
                
            )
            .fromTo(
                ".stat-button",
                {
                    scale: 0.9,
                    opacity: 0
                },
                {
                    scale: 1,
                    opacity: 1,
                    ease: "power3",
                    duration: 0.5
                },
                "<"
            )
            .fromTo(split.chars, { y: 40 }, { y: 0, stagger: 0.05, duration: 2 })
            .fromTo(splitText.chars, { y: -40 }, { y: 0, stagger: 0.05,duration:0.5 },"<")

            .fromTo(".stat-line", {
                width: "0"
            }, { width: "200px",duration:2 })
            .fromTo(".stat-spacer", { height: "0" }, { height: "20px" }, "<")

    })


})
</script>
<template>
    <div class="md:px-5 px-2 py-5 grid grid-cols-1 md:grid-cols-2 gap-6 statSection relative">
        <div
            class="w-full order-2 md:order-1  p-3 items-center gap-5 rounded-2xl  bg-linear-to-b from-black to-main text-gray-100 grid md:grid-cols-2 min-h-[calc(100vh-40px)]">
            <div class="flex flex-col gap-8 md:mb-16">
                <StatCard v-for="(item, index) in [1, 2, 3]" :key="index" :heading="'bespoke concepts'"
                    :description="'Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.'" />
            </div>
            <div class="flex flex-col gap-8 md:mt-16">
                <StatCard v-for="(item, index) in [1, 2, 3]" :key="index" :heading="'bespoke concepts'"
                    :description="'Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores necessitatibus t Lorem ipsum dolor sit amet.'" />

            </div>
        </div>
        <div class=" px-3 box-border w-full flex flex-col justify-end items-end-safe gap-4">
            <!-- heading -->
            <div class="flex flex-col items-end w-full gap-4 ">

                <h2
                    class="flex flex-wrap justify-end font-heading text-3xl md:text-5xl font-semibold capitalize gap-x-4 leading-tight overflow-hidden">
                    <div class="text-center overflow-hidden ">
                        <span class="stat-mainheading inline-block">
                            Where Detail Shapes
                        </span>
                    </div>

                    <div class="flex items-center gap-4 ">
                        <span class="italic img-text">
                            Meaningful
                        </span>

                        <div
                            class="meaningful-image-wrapper overflow-hidden rounded-full md:w-40 md:h-20 w-15 h-8 shrink-0">
                            <img class="meaningful-image w-full h-full object-cover"
                                src="https://i.pinimg.com/736x/db/48/75/db4875081f8248aa02d8420912fcf84e.jpg" alt="" />
                        </div>

                        <span class="italic  img-text">
                            Design
                        </span>
                    </div>
                </h2>
                <h6 class="capitalize font-body font-bold flex items-center gap-1 md:gap-2 text-sm text-end overflow-hidden  
                    ">
                    <ArrowLeft class="w-5 text-black" /><span class=" h-[0.5px] bg-black w-25 md:w-50 stat-line"></span>
                    <p class="stat-line-text">inside the
                        process</p>
                </h6>

                <div class="flex items-end flex-col md:flex-row-reverse gap-3 overflow-hidden">
                    <p class="max-w-11/12  md:w-[65%] text-xs font-body  text-end stat-line-text">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde rem accusamus, fuga saepe aut
                        eos optio repudiandae Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt enim
                        facere architecto.
                    </p>
                    <button class="px-6 py-2 cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in
                 bg-black text-white rounded-full stat-button">Learn More</button>
                </div>
            </div>
            <!-- stat -->
            <div class="flex flex-wrap items-center justify-center gap-4 py-6">
                <div class="flex flex-col items-center  gap-1 px-3 mx:px-6 overflow-hidden ">
                    <span class="overflow-hidden">
                        <h2 class="text-3xl md:text-4xl font-bold font-projects number-stat">150+</h2>
                    </span>
                    <span class="overflow-hidden">
                        <p class="md:text-base text-xs font-medium interior number-text-stat">Curated Interiors</p>
                    </span>
                </div>
                <span class="w-[0.5px]  bg-gray-400 flex self-center stat-spacer"></span>
                <div class="flex flex-col items-center  gap-1  px-3 mx:px-6 ">
                    <span class="overflow-hidden">
                        <h2 class="text-3xl md:text-4xl font-bold font-projects number-stat">50+</h2>
                    </span>
                    <span class="overflow-hidden">
                        <p class="md:text-base text-xs font-medium number-text-stat">Happy Customers</p>
                    </span>
                </div>
                <span class="w-[0.5px]  bg-gray-400 flex self-center stat-spacer"></span>
                <div class="flex flex-col items-center  gap-1  px-3 mx:px-6">
                    <span class="overflow-hidden">

                        <h2 class="text-3xl md:text-4xl font-bold font-projects number-stat">10+</h2>
                    </span>
                    <span class="overflow-hidden">
                        <p class="md:text-base text-xs font-medium number-text-stat">Industry Expertise</p>
                    </span>
                </div>
            </div>
            <div class="stat-image-wrapper relative w-full h-[280px] overflow-hidden rounded-2xl">
                <img class="stat-image absolute inset-0 w-full h-full object-cover"
                    src="https://i.pinimg.com/1200x/e5/b0/c7/e5b0c7297721a4be2f3e258a3afc5587.jpg" alt="">
                <img class="stat-image absolute inset-0 w-full h-full object-cover"
                    src="https://i.pinimg.com/1200x/8b/56/26/8b56266cc26f348af494e5c503506e48.jpg" alt="">
                <img class="stat-image absolute inset-0 w-full h-full object-cover"
                    src="https://i.pinimg.com/736x/78/53/09/78530948f1240d33b117f4397dc40283.jpg" alt="">
            </div>
        </div>

    </div>
</template>
<style scoped></style>