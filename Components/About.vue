<script setup>
import gsap from 'gsap';
import {  onMounted } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
import SplitType from 'split-type';
gsap.registerPlugin(ScrollTrigger)

onMounted(()=>{
    const tl = gsap.timeline({scrollTrigger:{
        start:'top 70%',end:'top 10%',trigger:'.container',scrub:true,markers:true
    }})
const split = new SplitType('.title',{
    types:'words'
})
const splitPara = new SplitType('.para',{
    types:'lines'
})
tl.from(splitPara.lines,{
        x:-30,ease:'power2.inOut',stagger:0.08,duration:2,rotateX:80,opacity:0

})
.from(split.words,{
        x:-30,ease:'power2.inOut',stagger:0.08,duration:2,rotateX:80,opacity:0
})
 })

</script>
<template>
 <div class="md:p-5 p-2 flex  bg-white relative z-10  flex-col md:flex-row gap-8 container ">
            <!-- col-1 -->
            <div class="flex-7 ">
                <div style="background-image: url(https://i.pinimg.com/1200x/5d/2f/b8/5d2fb87f8c6aacb1d930e01e401f8a05.jpg
);" class="bg-black rounded-2xl md:rounded-4xl bg-center bg-cover  h-screen flex flex-col items-start  justify-end ">
                    <div
                        class="flex flex-col items-start justify-start rounded-4xl text-black font-poppins capitalize ">
                        <span class="pr-6 pt-4 rounded-tr-lg  bg-white">
                            <h6 class="rounded-full border px-3 py-1 text-sm  ">gorgeous interior</h6>
                        </span>
                        <span class="pr-6 py-2 rounded-tr-lg bg-white">
                            <h6
                                class="font-bold text-6xl bg-linear-to-r from-black to-main text-transparent bg-clip-text  ">
                                Modern</h6>
                        </span>
                        <span class="md:pr-6 pr-16 py-2 rounded-tr-lg bg-white">
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
                    class="flex flex-col items-start justify-center gap-3 font-body rounded-2xl md:rounded-4xl bg-linear-120 from-black to-main text-white p-5">
                    <h6 class="md:rounded-full rounded-xl border px-3 py-1 text-xs md:text-sm  ">aesthetic</h6>
                    <p class="para">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis labore doloribus recusandae </p>
                    <h2 class="font-heading  text-3xl md:text-4xl font-medium title ">
    Into A Gallery Of Elegance
                    </h2>
                </div>
                <div style="background-image: url(https://i.pinimg.com/1200x/ac/61/19/ac61196521cec3df1e94987c0b176b79.jpg);"
                    class="rounded-2xl md:rounded-4xl  bg-cover bg-center">

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