<script setup>
import gsap from 'gsap';
import {  onMounted } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
import SplitType from 'split-type';
gsap.registerPlugin(ScrollTrigger)

onMounted(()=>{
    const tl = gsap.timeline({scrollTrigger:{
        start:'top center',end:"+=700",trigger:'.container',scrub:true,markers:true
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
 })

</script>
<template>
 <div class="md:p-5 p-2 flex  bg-white relative z-10  flex-col md:flex-row gap-8 container ">
            <!-- col-1 -->
            <div class="flex-7 ">
                <div  class=" rounded-2xl md:rounded-4xl   h-screen flex flex-col items-start overflow-hidden  justify-end relative ">
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
                        <span class="pr-6 pt-4 rounded-tr-lg  bg-white leftText">
                            <h6 class="rounded-full border px-3 py-1 text-sm  w-max whitespace-nowrap">gorgeous interior</h6>
                        </span>
                        <span class="pr-6 py-2 rounded-tr-lg bg-white leftText">
                            <h6
                                class="font-bold text-6xl bg-linear-to-r from-black to-main text-transparent bg-clip-text  ">
                                Modern</h6>
                        </span>
                        <span class="md:pr-6 pr-16 py-2 rounded-tr-lg bg-white leftText">
                            <h6
                                class="font-bold text-6xl  bg-linear-to-r from-black to-main text-transparent bg-clip-text ">
                                Minimalist</h6>
                        </span>
                    </div>
                </div>
            </div>
            <!-- col-2 -->
            <div class="flex-3 grid grid-rows-2 gap-6">

                <div
                    class="flex flex-col items-start justify-center gap-3 font-body rounded-2xl md:rounded-4xl bg-linear-120 from-black to-main text-white p-5 text-container">
                    <h6 class="md:rounded-full rounded-xl border px-3 py-1 text-xs md:text-sm  ">aesthetic</h6>
                    <p class="para">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis labore doloribus recusandae </p>
                    <h2 class="font-heading  text-3xl md:text-4xl font-medium title ">
    Into A Gallery Of Elegance
                    </h2>
                </div>
                <div style="background-image: url(https://i.pinimg.com/1200x/ac/61/19/ac61196521cec3df1e94987c0b176b79.jpg);"
                    class="rounded-2xl md:rounded-4xl right-img  bg-cover bg-center">

                </div>

            </div>
        </div>
</template>
<style scoped>
.title,
.para {
  perspective: 800px;
}
</style>