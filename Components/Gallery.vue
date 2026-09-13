<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { ArrowLeft } from 'lucide-vue-next';
import SplitType from 'split-type';
import { onMounted, onUnmounted } from 'vue';
gsap.registerPlugin(ScrollTrigger)
onMounted(()=>{
    let mm 
   mm= gsap.matchMedia()
       const splitLines= new SplitType('.gallery-subheading',{types:'lines'})
const imageGallery  = gsap.utils.toArray(".gallery-div ")
   mm.add('(min-width:768px)',()=>{
    const tl = gsap.timeline({scrollTrigger:{trigger:".gallery-container",scrub:2,start:"top 90%",end:"top 60%",markers:true}})
    tl.from('.gallery-heading',{
        y:120,opacity:0,duration:2,
    })
    imageGallery.forEach(div=>{
        div.addEventListener("mouseenter",()=>{
gsap.to("div:nth-of-type(2) img",{opacity:1,height:'260px'})
        })

    })
    .from(splitLines.lines,{
        y:60,rotateY:50, opacity:0,duration:1.5,ease:"none",stagger:'0.3'
    },"-=0.3")
    .from('.gallery-button',{
        y:60,opacity:0,duration:1
    },"-=0.3")
   })
   
})
</script>

<template>
      <div class=" px-2 md:p-12 flex  flex-col md:flex-row gap-3 gallery-container">
            <div class="lg:max-w-1/4 flex flex-col gap-4 ">
                <span class="overflow-hidden">
                <h2
                    class="gallery-heading font-bold font-heading  text-4xl md:text-5xl bg-linear-to-r from-black to-main text-transparent bg-clip-text ">
                    Designed for Every Space
                </h2>
                </span >
<span class="overflow-hidden">
                <p class=" gallery-subheading text-xs font-medium font-body">Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                    Voluptas magni enim sunt, iusto totam mollitia tempore nisi ad quos expedita! Ipsa, error quas.</p>
                    </span>
                    <span class="gallery-button overflow-hidden">
                <button class="px-6 py-2 cursor-pointer hover:bg-white hover:border-black border hover:text-black transition-all duration-300 ease-in
                 bg-black text-white rounded-full w-1/2 ">Learn More</button>
                 </span>
            </div>
            <ul class="flex flex-col gap-2 flex-1 mt-5">
             <li
                    class="border-y-[0.2px] border-y-gray-700 py-4 flex flex-col gallery-div  ">
                    <div class="text-2xl font-medium font-body  w-full px-8 flex  items-center justify-between">
                 <h2>    
                    Modern Living Rooms
</h2>   
                    <ArrowLeft class="w-8 h-8 rotate-130 text-black " />
                    </div>
                      <div class="flex gap-3 items-end justify-end pr-12 pt-4 image-container">
                        
                        <img v-for="(item, index) in [1,2,3]" :key="index" class="w-[205px] h-0 opacity-0 object-cover  gallery-image  rounded-2xl" src="https://i.pinimg.com/736x/c1/a8/a9/c1a8a92894279e57c4e19ba092a79be4.jpg" alt="">
                    </div>
                </li>
                    <li
                    class="border-y-[0.2px] border-y-gray-700 py-4 flex flex-col gallery-div  ">
                    <div class="text-2xl font-medium font-body  w-full px-8 flex  items-center justify-between">
                 <h2>    
                    Modern Living Rooms
</h2>   
                    <ArrowLeft class="w-8 h-8 rotate-130 text-black " />
                    </div>
                      <div class="flex gap-3 items-end justify-end pr-12 pt-4 image-container">
                        
                        <img v-for="(item, index) in [1,2,3]" :key="index" class="w-[205px] h-0 opacity-0 object-cover  gallery-image  rounded-2xl" src="https://i.pinimg.com/736x/c1/a8/a9/c1a8a92894279e57c4e19ba092a79be4.jpg" alt="">
                    </div>
                </li>
                    <li
                    class="border-y-[0.2px] border-y-gray-700 py-4 flex flex-col gallery-div  ">
                    <div class="text-2xl font-medium font-body  w-full px-8 flex  items-center justify-between">
                 <h2>    
                    Modern Living Rooms
</h2>   
                    <ArrowLeft class="w-8 h-8 rotate-130 text-black " />
                    </div>
                      <div class="flex gap-3 items-end justify-end pr-12 pt-4 image-container">
                        
                        <img v-for="(item, index) in [1,2,3]" :key="index" class="w-[205px] h-0 opacity-0 object-cover  gallery-image  rounded-2xl" src="https://i.pinimg.com/736x/c1/a8/a9/c1a8a92894279e57c4e19ba092a79be4.jpg" alt="">
                    </div>
                </li>

            </ul>
        </div>
</template>
<style scoped>

</style>