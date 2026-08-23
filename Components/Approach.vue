<script setup>
import { onMounted } from 'vue';
import approach from '../src/assets/approach.png'
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
    const tl = gsap.timeline({
        scrollTrigger: {
            trigger: '.approach-container',
            start: 'top top',
            end: '+=500%',
            scrub: true,
            pin: true,
            pinSpacing: true,
        }
    })

    tl.fromTo('.image', {
        scale: 1.3,
        xPercent: 30
    }, {
        scale: 1,
        xPercent: 0,
        ease: 'none'
    },0)
    .fromTo('.approach-title',{yPercent:100,opacity:0},{yPercent:0,opacity:1},0)
    .fromTo('.approach-description',{yPercent:100,opacity:0},{yPercent:0,opacity:1},0)
        .fromTo('.feature',
        {
            y: 60,
            opacity: 0
        },
        {
            y: 0,
            opacity: 1,
            stagger: 0.2,
            ease: 'none'
        }
    )

})

</script>
<template>
    <div class="md:p-5 p-2 approach-container">
            <div class=" w-full rounded-3xl bg-gray-100 md:px-6 px-2 py-5 md:py-8 min-h-[calc(100vh-40px)] ">
                
             
                <div class="flex flex-col md:flex-row gap-3 md:gap-12 justify-between items-end md:items-start w-full pb-5">
                <div class="md:flex-5 overflow-hidden">
                    <h2
                        class="font-heading text-4xl md:text-5xl font-semibold approach-title">Elevating Everyday Spaces</h2>

                </div>
                <div class="md:flex-4 overflow-hidden">
                     <p class="font-body font-normal approach-description text-xs md:text-sm text-gray-700 md:text-end">Lorem ipsum dolor sit amet
                        consectetur adipisicing elit. <span class="font-semibold">Temporibus</span> quis voluptate vitae
                        eaque! Nostrum facilis minus, alias necessitatibus, <span class="font-semibold">maiores</span>
                        est beatae quaerat explicabo repudiandae</p>

                </div>
            </div>
                <!-- Material & Texture -->
                <!-- Lighting & Atmosphere -->
                 <div class="grid grid-cols-1 md:grid-cols-2 justify-items-center " >

                                        <img :src="approach" class="opacity-95 brightness-75 w-full image" alt="">
    <div class="flex flex-col gap-5 justify-center items-center md:pr-6">
                    <div
                        class="feature flex flex-row gap-4 bg-linear-to-t from-main to-black  hover:bg-black rounded-xl p-2.5 md:p-5 group w-full md:max-w-8/12">
                        <div class=" transition-all duration-300 ease-out">
                            <img src="https://i.pinimg.com/1200x/87/3f/89/873f8928e27c13c03bb5862951ddb09a.jpg"
                                class="rounded-lg aspect-square  transition-all duration-300 ease-out w-50 group-hover:scale-110 hover:transform-border border-2"
                                alt="">

                        </div>
                        <div class=" text-white flex flex-col  gap-1 items-start justify-center ">
                            <h3 class="font-heading font-medium text-lg md:text-2xl">Concept & Planning</h3>
                            <p class="font-body text-xs md:text-sm ">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                Laboriosam quas consequuntur </p>
                        </div>
                    </div>

                    <div class="feature flex flex-row-reverse gap-4 bg-black/85 rounded-xl p-2.5 md:p-5  w-full md:max-w-8/12 ">
                        <div>
                            <img src="https://i.pinimg.com/1200x/87/3f/89/873f8928e27c13c03bb5862951ddb09a.jpg"
                                class="rounded-lg aspect-sqaure w-50" alt="">

                        </div>
                        <div class=" text-white flex flex-col md:gap-2">
                            <h3 class="font-heading font-medium text-lg md:text-2xl">Lorem, ipsum dolor.</h3>
                            <p class="font-body text-xs md:text-sm">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                Laboriosam quas consequuntur cumque?</p>
                        </div>
                    </div>
                    <div class="feature flex gap-4 bg-black/85 rounded-xl p-2.5 md:p-5  w-full md:max-w-8/12">
                        <div>
                            <img src="https://i.pinimg.com/736x/ae/68/b6/ae68b669e2b0ce0174ab9a70980f4cf9.jpg"
                                class="rounded-lg aspect-sqaure w-50" alt="">

                        </div>
                        <div class=" text-white flex flex-col gap-1 md:gap-2">
                            <h3 class="font-heading font-medium text-lg md:text-2xl">Lorem, ipsum dolor.</h3>
                            <p class="font-body text-xs md:text-sm">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                Laboriosam quas consequuntur cumque?</p>
                        </div>
                    </div>
                </div>
                
                </div>
            </div>

        </div>
</template>
<style scoped></style>