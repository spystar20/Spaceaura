<script setup>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted, onUnmounted } from 'vue';
gsap.registerPlugin(ScrollTrigger);
import ProjectCard from '../src/components/ProjectCard.vue';
import { Col1, Col2, CenterCol } from '../src/data/Project';

let mm;

onMounted(() => {
  mm = gsap.matchMedia();
      const cards = gsap.utils.toArray(".projectCard-image");
     const projectBox = gsap.utils.toArray(".projectCard")
  mm.add("(min-width: 768px)", () => {
    console.log("matchMedia running")
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: ".project-container",
        start: "top 95%",
        end: "bottom 40%",
        scrub: true,
      }
    });


    tl.fromTo(".project-heading", { yPercent: 100 }, { yPercent: 0, ease: "power3.out" })
      .fromTo(".project-desc", { yPercent: 100 }, { yPercent: 0, ease: "power3.out" }, "<")
.fromTo(
  cards,
  {
    backgroundPosition: "center 120%",
    scale:1.1
  },
  {
    backgroundPosition: "center 50%",
    ease: "none",
    scale:1
  },"<0.3"
)
.fromTo(".projectCard-textContainer",{y:20},{y:0},"<")
  });

 mm.add("(max-width: 767px)", () => {

  gsap.fromTo(
    ".project-heading",
    {
      yPercent: 100,
      opacity: 0
    },
    {
      yPercent: 0,
      opacity: 1,
      scrollTrigger: {
        trigger: ".project-heading",
        start: "top 90%",
        end: "top 60%",
        scrub: true,
      }
    }
  );

  gsap.fromTo(
    ".project-desc",
    {
      yPercent: 100,
      opacity: 0
    },
    {
      yPercent: 0,
      opacity: 1,
      scrollTrigger: {
        trigger: ".project-desc",
        start: "top 90%",
        end: "top 60%",
        scrub: true,
      }
    }
  );
projectBox.forEach((card)=>{
  gsap.fromTo(card,{scaleY:0,opacity:0,transformOrigin:"center bottom"},{scaleY:1,opacity:100,scrollTrigger:{
    trigger:card,start:"top 90%",end:"top 50%",scrub:true,markers:true
  }})
})

});

})
</script>

<template>
  <div class="px-2 py-5 md:px-5 project-container">
    <!-- heading -->
    <div class="flex flex-col md:flex-row gap-3 md:gap-12 justify-between  md:items-start w-full">
      <div class="md:flex-5 overflow-hidden">
        <h2 class="font-semibold font-heading text-4xl md:text-5xl bg-linear-to-r from-black to-main text-transparent bg-clip-text project-heading">
        Explore   Our Collection
        </h2>
      </div>
      <div class="md:flex-4 overflow-hidden">
        <p class="md:text-end font-body font-medium text-xs md:text-sm project-desc">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rerum possimus atque dolores quasi
        </p>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-4 gap-5 py-5 w-full min-h-screen">
      <div class="grid grid-cols-1 md:grid-cols-1 h-full gap-3">
        <ProjectCard v-for="(item, i) in Col1" :key="item.id" :project="item" :index="i" />
      </div>

      <!-- column-2:  using ProjectCard instead of duplicated markup -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-1 md:col-span-2 h-full gap-3 box-border">
        <ProjectCard :project="CenterCol[0]" :index="0" class="flex-6" />
        <div class="flex-4 flex flex-col md:flex-row gap-5">
          <ProjectCard :project="CenterCol[1]" :index="1" class="w-full" />
          <ProjectCard :project="CenterCol[2]" :index="2" class="w-full" />
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-1 h-full gap-3">
        <ProjectCard v-for="(item, i) in Col2" :key="item.id" :project="item" :index="i" />
      </div>
    </div>
  </div>
</template>
<style scoped>
</style>