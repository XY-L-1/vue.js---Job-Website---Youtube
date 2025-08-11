<script setup >
import picData from '@/pics.json';
import {ref} from 'vue';

const pics = ref(picData);
</script>

<template>
   <section class="bg-blue-50 px-4 py-10">
      <div class="container-xl lg:container m-auto">
         <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
            Browse Pics
         </h2>

         <div class="grid grid-cols-1 md:grid-cols gap-6">
            <div v-for="pic in pics" :key="pic.id">
               {{ pic.title }}
            </div>
         </div>
      </div>
   </section>
</template>