<script setup>
const year = new Date().getFullYear()
import { Icon } from '@iconify/vue';
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger';
import SplitType from 'split-type';
import { nextTick, onMounted, onUnmounted, ref } from 'vue';
gsap.registerPlugin(ScrollTrigger)
const mainRef = ref(null)
let ctx
let splitText
onMounted(async ()=>{
  await nextTick()
  ctx = gsap.context(()=>{
    if(splitText)splitText.revert()
    splitText = new SplitType(
      ".footer-heading",{types:'chars'}
    )
    const tl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,start:'top 80%' ,end:'top 50%' ,invalidateOnRefresh:true}})
tl.from(splitText.chars,{
  filter:'blur(20px)',stagger:0.12,xPercent:-160,opacity:0,duration:0.8,
  ease:'power3.out'

})
  },mainRef.value)
})
onUnmounted(() => {
  splitText?.revert()
  ctx?.revert()
})
</script>

<template>
    <div  ref="mainRef" class="bg-black  w-full p-5  md:py-16 md:px-12 text-white flex flex-col md:flex-row justify-between gap-5 md:items-center">
        <div class="w-full">
          <span class="overflow-hidden block">
        <h2 class="font-footer footer-heading text-5xl md:text-9xl w-full text-white uppercase leading-none ">spaceaura</h2>
        </span>
        
        <p class="font-body capitalize">@{{year }} created By Santoshi</p>

        </div>
           <div class="text-3xl flex md:flex-col gap-1 ">
  <Icon icon="mdi:github"  />
    <Icon icon="mdi:gmail"  />
  <Icon icon="mdi:linkedin" />

    </div>
    </div>
 
</template>

<style scoped>
    
</style>