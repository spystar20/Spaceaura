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
    const tl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,start:'top 80%',invalidateOnRefresh:true}})
tl.from(splitText.chars,{
stagger:0.12,y:60,opacity:0,duration:1.2,rotateY:90,scale:0.5,
  ease:'power3.out'
})
.from('.github', {
  scale: 0,
  opacity: 0,
  duration: 0.5,
  ease: 'back.out(1.7)'
})
.from('.gmail', {
  scale: 0,
  opacity: 0,
  duration: 0.5,
  ease: 'back.out(1.7)'
}, '-=0.25')
.from('.linkedin', {
  scale: 0,
  opacity: 0,
  duration: 0.5,
  ease: 'back.out(1.7)'
}, '-=0.25')

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
           <div class="text-4xl flex md:flex-col gap-1 cursor-pointer">
  <Icon icon="mdi:github"  class="github"/>
    <Icon icon="mdi:gmail"  class="gmail" />
  <Icon icon="mdi:linkedin" class="linkedin" />

    </div>
    </div>
 
</template>

<style scoped>
    
</style>