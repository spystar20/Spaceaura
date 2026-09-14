<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { ArrowLeft } from 'lucide-vue-next';
import SplitType from 'split-type';
import { nextTick, onMounted, onUnmounted, ref } from 'vue';
gsap.registerPlugin(ScrollTrigger)
const galleryItems = [
    {
        title: "Modern Living Spaces",
        images: [
            "https://i.pinimg.com/736x/61/8f/46/618f4628b3c3e5ed2bd55098a19a47b4.jpg",
            "https://i.pinimg.com/736x/3a/a6/78/3aa678321d7d32ac82ec7062f2977c03.jpg",
            "https://i.pinimg.com/736x/3b/7e/5c/3b7e5c42d1deaa30e1f02f8b469a32f3.jpg"
        ]
    },
    {
        title: "Elegant Dining Spaces",
        images: [
            "https://i.pinimg.com/736x/14/37/5e/14375e0f0a68e1f4e1b6b070cd2143c3.jpg",
            "https://i.pinimg.com/736x/2a/0d/e4/2a0de44b057b25259fd1f6915c6c186c.jpg",
            "https://i.pinimg.com/736x/67/b6/72/67b672da8effa919678454fe6cc03c27.jpg"
        ]
    },
    {
        title: "Serene Bedroom Retreats",
        images: [
            "https://i.pinimg.com/1200x/2d/d3/a6/2dd3a6b9a35365f04c6fd764a9e398c1.jpg",
            "https://i.pinimg.com/736x/f8/aa/cb/f8aacbfa3bab07b1c77aaf945e813072.jpg",
            "https://i.pinimg.com/736x/e4/b9/85/e4b9858c2fbfab9cf5127e3f83c3a12f.jpg"
        ]
    },
    {
        title: "Creative Work Spaces",
        images: [
            "https://i.pinimg.com/736x/56/0c/25/560c25ce214b0060777f845cea2443b9.jpg",
            "https://i.pinimg.com/736x/f2/be/a7/f2bea75ab33134ccd57a22be0c775b0c.jpg",
            "https://i.pinimg.com/736x/09/e7/e8/09e7e8a37f0fffbcb23e0a05543abe16.jpg"
        ]
    }
]
   let ctx 
   const mm = gsap.matchMedia()
const mainRef = ref(null)
    let splitLines
onMounted(async()=>{
await nextTick()
if(document.fonts) await document.fonts.ready
    ctx=gsap.context(()=>{
const imageGallery  = gsap.utils.toArray(".gallery-div")
mm.add('(max-width:768px)',()=>{
        if (splitLines) splitLines.revert()
            splitLines= new SplitType('.gallery-subheading',{types:'lines'})

    const tl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,scrub:2,start:"top 90%",end:"top top",markers:true,once:true}})
tl.fromTo('.gallery-heading', {
    y: 120,
    opacity: 0,
},{y:0,opacity:1 ,duration: 2,
    ease: "power3.out"})
.fromTo(splitLines.lines, {
    y: 60,
    opacity: 0,
    rotateY: 50,
},{
    y:0,opacity:1,rotateY:0,  duration: 1.5,
    ease: "power3.out",
    stagger: 0.3
}, "-=1")
.from('.gallery-button', {
    y: 60,
    opacity: 0,
    duration: 1,
    ease: "power3.out"
}, "-=0.8")
    imageGallery.forEach(div=>{
        const images  = div.querySelectorAll(".gallery-image")
        const container = div.querySelector(".gallery-image-wrapper")
        console.log(container)
        div.addEventListener("mouseenter",()=>{
                gsap.killTweensOf([container, images])

            gsap.to(container,{gridTemplateRows:"1fr",duration:0.65,ease:"power2.out",overwrite:'auto'})
gsap.to(images,{opacity:1,stagger:0.14, scale:1,duration:0.7,y:0,ease:"power3.out",overwrite:"auto"})
        })
div.addEventListener("mouseleave",()=>{
        gsap.killTweensOf([container, images])

                gsap.to(container,{gridTemplateRows:"0fr",duration:0.6,ease:"power3.inOut",overwrite:"auto",delay:0.08})

    gsap.to(images,{
        opacity:0,stagger:{
            each:0.08,from:'end'
        },y:-25,scale:0.97,duration:0.45,ease:"power2.inOut",overwrite:"auto"
    })
})
    })
})
mm.add('(min-width:767px)',()=>{
            if (splitLines) splitLines.revert()
            splitLines= new SplitType('.gallery-subheading',{types:'lines'})

    const tl = gsap.timeline({scrollTrigger:{trigger:mainRef.value,scrub:2,start:"top 90%",end:"top top",markers:true,once:true}})
tl.fromTo('.gallery-heading', {
    y: 120,
    opacity: 0,
},{y:0,opacity:1 ,duration: 2,
    ease: "power3.out"})
.fromTo(splitLines.lines, {
    y: 60,
    opacity: 0,
    rotateY: 50,
},{
    y:0,opacity:1,rotateY:0,  duration: 1.5,
    ease: "power3.out",
    stagger: 0.3
}, "-=1")
.from('.gallery-button', {
    y: 60,
    opacity: 0,
    duration: 1,
    ease: "power3.out"
}, "-=0.8")
    imageGallery.forEach(div=>{
        const images  = div.querySelectorAll(".gallery-image")
        const container = div.querySelector(".gallery-image-wrapper")
        console.log(container)
        div.addEventListener("mouseenter",()=>{
                gsap.killTweensOf([container, images])

            gsap.to(container,{gridTemplateRows:"1fr",duration:0.65,ease:"power2.out",overwrite:'auto'})
gsap.to(images,{opacity:1,stagger:0.14, scale:1,duration:0.7,y:0,ease:"power3.out",overwrite:"auto"})
        })
div.addEventListener("mouseleave",()=>{
        gsap.killTweensOf([container, images])

                gsap.to(container,{gridTemplateRows:"0fr",duration:0.6,ease:"power3.inOut",overwrite:"auto",delay:0.08})

    gsap.to(images,{
        opacity:0,stagger:{
            each:0.08,from:'end'
        },y:-25,scale:0.97,duration:0.45,ease:"power2.inOut",overwrite:"auto"
    })
})
    })
})
   },mainRef.value)
})
onUnmounted(() => {
  if (splitLines) splitLines.revert();
  ctx.revert()
});
</script>

<template>
    <div ref="mainRef" class="px-2 md:px-8 lg:px-12 py-10 md:py-16 flex flex-col md:flex-row gap-8 lg:gap-16 gallery-container">

        <!-- Left Content -->
        <div class="w-full md:w-[35%] lg:w-1/4 flex flex-col justify-between gap-6">
            <div class="flex flex-col gap-5">
                <span class="overflow-hidden">
                    <h2
                        class="gallery-heading font-bold font-heading text-4xl md:text-4xl lg:text-6xl leading-[0.95] tracking-tight bg-linear-to-r from-black to-main text-transparent bg-clip-text">
                        Designed for Every Space
                    </h2>
                </span>

                <span class="overflow-hidden block">
                    <p class="gallery-subheading  text-sm  font-medium font-body text-gray-600">
                        From quiet corners to spaces made for gathering, explore interiors designed around the way you live.
                    </p>
                </span>
                <span class="overflow-hidden">
                  <span class=" gallery-button overflow-hidden">
                <button
                    class="md:px-6  md:py-2.5 px-3 py-1 cursor-pointer border border-black bg-black text-white rounded-full
                    hover:bg-white hover:text-black transition-all duration-300 ease-in-out">
                    Learn More
                </button>
                </span>
            </span>

            </div>

          
        </div>

        <!-- Categories -->
        <ul class="flex flex-col gap-0 flex-1 min-w-0">

            <!-- Living -->
         <li
        v-for="(item, index) in galleryItems"
        :key="index"
        class="border-b-[0.2px] border-gray-700 py-4 flex flex-col gallery-div group first:border-t-[0.2px]"
    >

                <div
                    class="text-lg gallery-trigger md:text-2xl font-medium font-body w-full px-2 md:px-6 flex items-center justify-between">

                    <h2 class="transition-transform duration-300 group-hover:translate-x-2">
                       {{item.title}}
                    </h2>

                    <ArrowLeft
                        class="gallery-arrow w-7 h-7 md:w-8 md:h-8 rotate-130 text-black transition-transform duration-300 group-hover:translate-x-1" />
                </div>
<div class="grid grid-rows-[0fr]  gallery-image-wrapper ">
    <div class="overflow-hidden ">
                <div
                    class=" flex gap-1.5 m:gap-4 items-end justify-end md:pr-2 md:pr-6 pt-5">

                    <img v-for="(image, imgIndex) in item.images" :key="imgIndex"
                        class="md:w-[205px] h-[145px] w-[98px]  md:h-[260px] shrink-0 opacity-0 object-cover gallery-image rounded-2xl"
                       :src="image">

                 </div>

                </div>
                </div>
            </li>

        </ul>
    </div>
</template>
<style scoped>

</style>