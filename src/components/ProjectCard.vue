<script setup>
import { ArrowUpRight } from 'lucide-vue-next';

defineProps({
    project: Object
})
</script>
<template>

    <div  class="h-[300px] md:h-[400px] relative group overflow-hidden rounded-3xl box-border">
        <div  :style='{ backgroundImage: `url(${project.img})` }'
            class="w-full bg-cover bg-center rounded-3xl h-full group-hover:scale-105 transition transform duration-500 ease-in projectCard-image">
        </div>
        <div
            class=" w-full h-auto  md:hover:bg-black/30 ease-in duration-300 transition-all rounded-2xl bg-linear-to-t from-black/90  md:from-0% via-black/40  md:via-25% to-transparent md:to-30% absolute inset-0 flex items-end justify-between p-2 lg:py-3 lg:px-6">
            <div class="transform md:translate-y-[65%]  md:group-hover:translate-y-0 transition duration-300 ">
                <div class="flex  justify-between items-center ">
                    <h1 class="text-2xl lg:text-3xl font-projects font-semibold  text-white">{{ project.title }}</h1>
                    <span class="  text-black bg-white rounded-full p-1 lg:p-2 ">
                        <ArrowUpRight class="hover:scale-125 transition-all ease-in duration-200 cursor-pointer" />
                    </span>
                </div>
                <div class="md:opacity-0 md:group-hover:opacity-100 transition duration-300 md:mt-3">

                    <p class="font-body text-white text-xs md:text-sm py-2 text-center">Lorem ipsum dolor sit amet,
                        consectetur
                        adipisicing elit. Cumque magni alias ipsam?</p>
                    <!-- buttons -->
                    <div class="flex items-center justify-center  gap-3 py-2 w-full">
                        <button
                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">view</button>
                        <button
                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">contact</button>
                        <button
                            class="px-4 py-0.5 text-white border border-white rounded-full capitalize hover:bg-white/5 hover:scale-95 ease-in transition-all duration-100 cursor-pointer">learn</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped></style>