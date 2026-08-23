<script setup>
import gsap from 'gsap';
import {  onMounted } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
import SplitType from 'split-type';
gsap.registerPlugin(ScrollTrigger)
// pin:true,pinSpacing:true

onMounted(()=>{
const mm = gsap.matchMedia()
    // animation for laptop
 mm.add("(min-width: 768px)",()=>{
      const tl = gsap.timeline({scrollTrigger:{
        start:'top top',end:"+=900",trigger:'.container',scrub:true,pin:true,pinSpacing:true
    }})
const split = new SplitType('.title',{
    types:'words'
})
const splitPara = new SplitType('.para',{
    types:'lines'
})

tl.from(".img-strips div",{
  xPercent: -100,
  stagger: 0.1,
  duration: 2,
  ease: "power3.inOut"
})

.from(".text-container", {
  scale: 0.8,
  opacity: 0,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(splitPara.lines, {
  x: -30,
  rotateX: 80,
  opacity: 0,
  stagger: 0.08,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(split.words, {
  x: -30,
  rotateX: 80,
  opacity: 0,
  stagger: 0.08,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(".right-img", {
  scale: 0.8,
  opacity: 0,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")
.from(".leftText", {
    xPercent: -200,
    width:0,
    stagger: 0.15,
    duration: 1,
    ease: 'power3.out'
}, "-=1.5")
.from(".interior",{
    x:-200
},'<')
}) 
// animation for mobile
mm.add("(max-width: 767px)", () => {
      const tl = gsap.timeline({
        scrollTrigger: {
            trigger: '.container',
            start: 'top top',
            end: '+=600',
            scrub: true,
            pin: false,
            pinSpacing: true,
            markers: true
        }
    })
    mm.add("(max-width: 767px)", () => {
   const tl = gsap.timeline({scrollTrigger:{
        start:'top top',end:"+=300",trigger:'.container',scrub:true,pinSpacing:true,pin:true
    }})
const split = new SplitType('.title',{
    types:'words'
})
const splitPara = new SplitType('.para',{
    types:'lines'
})

tl.from(".img-strips div",{
  xPercent: -100,
  stagger: 0.1,
  duration: 2,
  ease: "power3.inOut"
})

.from(".text-container", {
  scale: 0.8,
  opacity: 0,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(splitPara.lines, {
  x: -30,
  rotateX: 80,
  opacity: 0,
  stagger: 0.08,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(split.words, {
  x: -30,
  rotateX: 80,
  opacity: 0,
  stagger: 0.08,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")

.from(".right-img", {
  scale: 0.8,
  opacity: 0,
  duration: 1,
  ease: "power2.out"
}, "-=0.3")
.from(".leftText", {
    xPercent: -200,
    width:0,
    stagger: 0.15,
    duration: 1,
    ease: 'power3.out'
}, "-=1.5")
.from(".interior",{
    x:-200
},'<')
})

})
 })

</script>
<template>
 <div class="md:p-5 p-2 grid md:grid-cols-[7fr_3fr]  bg-white relative z-10 gap-4 md:gap-6 container ">
            <!-- col-1 -->
            <div>
                <div  class=" rounded-2xl md:rounded-4xl min-h-[50vh]  md:min-h-[calc(100vh-40px)] flex flex-col items-start overflow-hidden  justify-end relative ">
<div class=" absolute inset-0  img-grid w-full h-full img-strips">
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 0%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 20%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 40%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 60%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 80%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
<div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
); background-position: 0% 100%; background-size: 100% 600%;"  class="w-full h-1/6 bg-cover"></div>
</div>

                    <div
                        class="flex flex-col items-start justify-start rounded-4xl text-black font-poppins capitalize z-40">
                        <span class="md:pr-6 pr-2 pt-2 md:pt-4 rounded-tr-lg  bg-white leftText">
                            <h6 class="rounded-full interior border px-2 md:px-3 py-1 text-xs md:text-sm  w-max whitespace-nowrap">gorgeous interior</h6>
                        </span>
                        <span class="md:pr-6 pr-5 py-1 md:py-2 rounded-tr-lg bg-white leftText">
                            <h6
                                class="font-bold text-4xl md:text-6xl bg-linear-to-r from-black to-main text-transparent bg-clip-text  ">
                                Modern</h6>
                        </span>
                        <span class="md:pr-6 pr-3 py-1 md:py-2 rounded-tr-lg bg-white leftText">
                            <h6
                                class="font-bold text-4xl md:text-6xl  bg-linear-to-r from-black to-main text-transparent bg-clip-text ">
                                Minimalist</h6>
                        </span>
                    </div>
                </div>
            </div>
            <!-- col-2 -->
            <div class=" grid grid-cols-1 w-full md:grid-rows-2 gap-2 md:gap-6 md:min-h-[calc(100vh-40px)] ">

                <div
                    class="flex flex-col items-start justify-end gap-3 font-body rounded-2xl md:rounded-4xl bg-linear-120 from-black to-main text-white p-3 md:p-5 text-container">
                    <h6 class="md:rounded-full rounded-xl border px-3 py-1 text-xs md:text-sm  ">aesthetic</h6>
                    <p class="para md:text-base text-xs leading-tight">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis labore doloribus recusandae </p>
                    <h2 class="font-heading  text-xl md:text-4xl font-medium title ">
    Into A Gallery Of Elegance
                    </h2>
                </div>
                <div style="background-image: url(https://i.pinimg.com/1200x/ac/61/19/ac61196521cec3df1e94987c0b176b79.jpg);"
                    class="rounded-2xl md:h-auto h-[35vh] md:rounded-4xl right-img  bg-cover bg-center">

                </div>

            </div>
        </div>
</template>
<style scoped>
.title,
.para {
  perspective: 800px;
}
.para .line {
    display: block;
}
</style>