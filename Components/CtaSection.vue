<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { ArrowLeft } from 'lucide-vue-next';
import SplitType from 'split-type';
import { nextTick, onMounted, onUnmounted, ref } from 'vue';
gsap.registerPlugin(ScrollTrigger)

</script>
<template>
      <div class="w-full  ">
            <div class=" hero-img w-full relative flex items-center justify-start bg-cover bg-center min-h-screen bg-no-repeat "
                style="background-image: url(https://i.pinimg.com/1200x/1e/6b/a2/1e6ba2c54b4b7333d8db9e3a43cda791.jpg);">
                <div class="absolute inset-0  bg-linear-to-bl from-white/10 to-black/45"></div>
                <div class=" bg-white/90 flex flex-col rounded-xl md:p-4  w-[450px] mx-3 md:w-1/5 md:mx-12 z-[12]">
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