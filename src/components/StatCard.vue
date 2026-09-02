<script setup>
import { PenTool } from 'lucide-vue-next';


defineProps({
    heading:{
        type:String,
    },description:{type:String}
})
</script>
<template>
       <div
 class=" border-gray-200/20 border rounded-2xl flex flex-col gap-3 p-5 bg-white/5 backdrop-blur-md transition duration-300 hover:bg-white/10">
                        <div class="flex items-center gap-3">
                            <PenTool class="text-white w-6 h-6 opacity-80" />
                            <h2 class="text-xl font-semibold ">{{ heading }}</h2>
                        </div>
                        <p class="text-sm font-body  text-gray-300 leading-relaxed">{{description}}</p>
                    </div>
</template>
<style scoped></style>