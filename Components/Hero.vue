<script setup>
import gsap from 'gsap';
import { nextTick, onMounted, ref } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger)
const buttonHero = ref(null)
onMounted(async() => {
    await nextTick()
    const tl = gsap.timeline()
   
 tl.from('.hero-img',{
    duration:1.5, scale:1.2 ,ease:'power3.out'})
 .from(".hero-title", {
        yPercent:100, opacity: 0, duration: 1, ease: "power3.out",
    },'-=1.2')
    .from(".hero-subtitle", {
        yPercent:60, opacity: 0, duration:1, ease: "power3.out",
    },'-=0.8')
    gsap.from('.button-hero',{
       y:100,opacity:0.5,duration:2,ease:'power3.out'
    })
 gsap.to('.hero-img', {
    y: 100,scale:1.1,
    scrollTrigger: {
      trigger: '.hero-img',
      start: 'top top',
      end: 'bottom top',
      scrub: 1,
    }
  })
})

</script>
<template>
<div id="home" class="w-full hero  flex items-center justify-center relative  rounded-2xl md:rounded-4xl px-2 md:px-5 box-border ">
            <div 
                class="bg-black w-full  rounded-2xl md:rounded-4xl  bg-cover bg-center overflow-hidden">
                <img src="https://i.pinimg.com/1200x/21/f5/9c/21f59c5b923c8f866d7da4a87dda0b4d.jpg" class="hero-img object-cover w-full md:h-[87vh] h-[86vh] overflow-hidden" alt="">
                <div class=" absolute  flex justify-center  items-center inset-x-2 md:inset-x-5 inset-y-0 bg-black/40 rounded-2xl md:rounded-4xl ">
                    <div class="overflow-hidden  text-center flex flex-col items-center gap-2 md:gap-5  justify-center text-white  ">
                        <div class="overflow-hidden ">
                        <h2 class="font-semibold font-heading text-4xl md:text-5xl capitalize hero-title">Designed Around Your <span
                                class="italic bg-linear-to-r from-white to-main text-transparent bg-clip-text  ">Comfort</span>
                        </h2>
                        </div>
                    <div class="overflow-hidden flex  justify-center ">
                        <p class="hero-subtitle text-center font-body text-xs md:text-sm normal-case md:w-1/2 px-5 ">Lorem ipsum, dolor sit amet consectetur
                            adipisicing elit. Obcaecati animi explicabo maiores placeat labore alias, a error quis, qui
                            quia quas.</p>
                            </div>
                        <div class="overflow-hidden ">
                            <button
                               ref="buttonHero" class="button-hero border border-white hover:text-white   hover:bg-[#645a4e] hover:border-main font-body font-medium 
                                px-6 md:px-8 md:py-3 py-2 mt-3 md:mt-0 rounded-lg cursor-pointer hover:scale-105 scale-100 ease-linear duration-150">Get
                                Started</button>
                        </div>
                    </div>

                </div>

            </div>
        </div>
</template>
<style scoped>

</style>