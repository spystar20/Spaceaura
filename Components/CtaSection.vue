<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { ArrowLeft } from 'lucide-vue-next';
import SplitType from 'split-type';
import { nextTick, onMounted, onUnmounted, ref } from 'vue';
gsap.registerPlugin(ScrollTrigger)
const mainRef = ref(null)
let ctx
onMounted(async()=>{
    await nextTick()
    if(document.fonts) await document.fonts.ready

    ctx= gsap.context(()=>{
        const tl = gsap.timeline({scrollTrigger:{start:'top 95%',end:"bottom top",trigger:mainRef.value,markers:true,scrub:2,invalidateOnRefresh:true}})
        gsap.set(".cta-img", {
    scale: 1.2,
    duration: 1,
    ease: "none"
})
tl.to(".cta-img", {
    scale: 1,
    duration: 2,
    ease: "none"
})
.to(".cta-img", {
    scale: 1.2,
    duration: 1,
    ease: "none"
})

const cardTl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,start:'top 85%',end:"bottom top",scrub:2,markers:true,invalidateOnRefresh:true
}})

cardTl.from('.cta-card',{y:40,duration:1,ease:"power3.out"})
    },mainRef.value)
    requestAnimationFrame(() => {
    ScrollTrigger.refresh()
})
})
onUnmounted(()=>{
ctx.revert()
})
</script>
<template>
      <div class="w-full cta-container" ref="mainRef" >
            <div class=" hero-img w-full min-h-[1024px] relative flex items-center justify-start  "
                >
               
                <div class="absolute inset-0  overflow-hidden">
                     <img class="cta-img h-full w-full bg-center bg-no-repeat object-cover" src="https://i.pinimg.com/1200x/1e/6b/a2/1e6ba2c54b4b7333d8db9e3a43cda791.jpg" alt="">
                </div>
                <div  class="absolute inset-0  bg-linear-to-bl from-white/10 to-black/45"></div>
                <div class=" bg-white/90 cta-card flex flex-col rounded-xl md:p-4  w-[300px] mx-3  md:mx-12 z-[12]">
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

</template>