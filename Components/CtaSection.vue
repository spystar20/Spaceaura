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
        const tl = gsap.timeline({scrollTrigger:{start:'top 95%',end:"bottom top",trigger:mainRef.value,scrub:2,invalidateOnRefresh:true}})
        gsap.set(".cta-img", {
    scale: 1.12,
    yPercent: -3,
})

tl.to(".cta-img", {
    scale: 1.06,
    yPercent:3,
    duration: 0.5,
    ease: "none",
})
.to(".cta-img",{
    scale:1.12,yPercent:-3,duration:0.5
,ease:'none'})
const cardTl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,start:'top 85%',end:"bottom top",scrub:2,invalidateOnRefresh:true
}})

cardTl.from('.cta-card',{y:40,duration:1,ease:"power3.out"})
gsap.set('.cta-card-image',{
    clipPath:'inset(100% 0% 0% 0%)'
})
gsap.set([
    ".cta-card-heading",
    ".cta-card-text",
    ".cta-card-button"
], {
    y: 25,
    opacity: 0
});
const innerTl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,start:"top top",end:"+=200px",scrub:1.5,invalidateOnRefresh:true,once:true}})
innerTl.to('.cta-card-image',{
    clipPath: "inset(0% 0% 0% 0%)",
    duration: 0.5,
    ease: "power2.out"})
.to(".cta-card-heading", {
    y: 0,
    opacity: 1,
    duration: 0.25,
    ease: "power3.out"
})
.to(".cta-card-text", {
    y: 0,
    opacity: 1,
    duration: 0.2,
    ease: "power3.out"
}, "-=0.1")
.to(".cta-card-button", {
    y: 0,
    opacity: 1,
    duration: 0.2,
    ease: "power3.out"
}, "-=0.1");
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
            <div class=" hero-img w-full h-[700px] md:min-h-[1024px] relative flex items-center overflow-hidden justify-start  "
                >
               
                <div class="absolute inset-0  overflow-hidden">
                     <img class="cta-img h-full w-full bg-center bg-no-repeat object-cover" src="https://i.pinimg.com/1200x/1e/6b/a2/1e6ba2c54b4b7333d8db9e3a43cda791.jpg" alt="">
                </div>
                <div  class="absolute inset-0  bg-linear-to-bl from-white/10 to-black/45"></div>
<div class="bg-white/90 cta-card flex flex-col rounded-xl md:p-4 w-[270px] md:w-[300px] ml-6 md:ml-16 lg:ml-24 z-[12] overflow-hidden">   
     <div class="cta-card-image overflow-hidden rounded-xl">
        <img
            class="rounded-xl  p-1 w-full object-cover"
            src="https://i.pinimg.com/736x/b0/5f/dd/b05fdd196a902ebb945f3f085458aa9b.jpg"
            alt=""
        >
    </div>

    <div class="flex flex-col gap-1 pt-1 md:py-2">
        <h2 class="cta-card-heading md:text-xl text-base font-bold font-heading px-1">
            Modern Living Room Design
        </h2>

        <p class="cta-card-text text-xs font-body font-normal px-1">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magni veritatis repudiandae id.
        </p>

        <button class="cta-card-button md:px-6 md:py-2 py-1 md:mt-1 text-xs cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in bg-black text-white rounded-full m-0">
            Learn More
        </button>
    </div>
</div>

            </div>
        </div>

</template>