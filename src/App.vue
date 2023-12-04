<script setup>
import { ref } from 'vue';
var isLoading  = ref(false);

</script>

<template>
  <div class="flex flex-row justify-center text-blue-200 items-center w-screen h-screen">
    <div class="flex flex-col justify-center">
      <img src="./icon.png" alt="" class="mx-auto w-16 mb-10  inline">
      <p class=" text-4xl font-bold text-center mb-12 px-4">Join the waitlist for<br> <span
        class="from-green-700 via-cyan-600 to-green-500 bg-gradient-to-r bg-clip-text text-transparent">CopyNSync!</span>
    </p>
    <div class="w-5/6 relative mb-5 m-auto">
      <div class="absolute h-full flex flex-col justify-center px-3 "><i class="uil uil-user"></i></div>
    <input type="text" autocomplete="name" name="" placeholder="Full name" id="" class="font-medium w-full text-sm bg-neutral-800 pl-9 px-3 py-3 rounded-md bg-transparent border border-neutral-500">
    </div>
    <div class="w-5/6 relative mb-7 m-auto">
      <div class="absolute h-full flex flex-col justify-center px-3 "><i class="uil uil-envelope "></i></div>
    <input type="email" autocomplete="email" name="" placeholder="Email address" id="" class="font-medium w-full text-sm bg-neutral-800 pl-9 px-3 py-3 rounded-md bg-transparent border border-neutral-500">
    </div>
    <div class="w-5/6  m-auto">
      <button :disabled="isLoading"  class="hover:transition-all duration-500  transform hover:-translate-y-1  hover:duration-500 py-3 from-green-800 to-cyan-700 text-white font-semibold  w-full rounded-md " :class="[!isLoading ?  'bg-gradient-to-r' : '', 'bg-neutral-700 text-neutral-400']" > <span v-if="isLoading" class="loader"></span> <span v-if="!isLoading" > Continue<i class="uil uil-arrow-right"></i></span></button>
    </div>
    </div>
  </div>

  <div class="absolute bottom-6 left-0 right-0 flex flex-row justify-center text-neutral-500">
    <span>Made with  <img src="./heart.png" alt="" class="mx-1 w-4 inline"> by <a href="https://twitter.com/samshot_01" target="_blank" class="font-medium from-green-600 via-cyan-400 to-green-500 bg-gradient-to-r bg-clip-text text-transparent"> samshot_01</a></span>
  </div>
</template>

<style scoped></style>
