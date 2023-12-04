<script setup>
import { ref } from 'vue';
var isLoading = ref(false);
var showModal = ref(false);

const joinWaitlist = async () => {
  if (email.value == "") {
    showError()
  }
  isLoading.value = true;

  await new Promise(resolve => setTimeout(resolve, 3000));
  showModal.value = true;
  isLoading.value = false;
  // await 

}

const showError = ()=> {

}

var email = ref('');
const onEmailChanged = (event) => {
  email.value = event.target.value;
  console.log(email.value);
}

</script>

<template>
  <div class="flex flex-row justify-center text-blue-200 items-center w-screen h-screen">
    <!-- <div class="p-3 bg-red-600 ">,</div> -->
    <div class="flex flex-col justify-center">
      <img src="./icon.png" alt="" class="mx-auto w-16 mb-10  inline">
      <p class=" text-4xl font-bold text-center mb-12 px-4">Join the waitlist for<br> <span
          class="from-green-700 via-cyan-600 to-green-500 bg-gradient-to-r bg-clip-text text-transparent">CopyNSync!</span>
      </p>
      <div class="w-5/6 relative mb-5 m-auto">
        <div class="absolute h-full flex flex-col justify-center px-3 "><i class="uil uil-user"></i></div>
        <input type="text" autocomplete="name" name="" placeholder="Full name" id=""
          class="font-medium w-full text-sm bg-neutral-800 pl-9 px-3 py-3 rounded-md bg-transparent border border-neutral-500">
      </div>
      <div class="w-5/6 relative mb-7 m-auto">
        <div class="absolute h-full flex flex-col justify-center px-3 "><i class="uil uil-envelope "></i></div>
        <input type="email" v-model="email" @input="onEmailChanged" autocomplete="email" name="" placeholder="Email address" id=""
          class="font-medium w-full text-sm bg-neutral-800 pl-9 px-3 py-3 rounded-md bg-transparent border border-neutral-500">
      </div>
      <div class="w-5/6  m-auto mb-20">
        <button :disabled="isLoading" @click="joinWaitlist()"
          class="hover:transition-all duration-500  transform hover:-translate-y-1  hover:duration-500 py-3 from-green-800 to-cyan-700 text-white font-semibold  w-full rounded-md "
          :class="[!isLoading ? 'bg-gradient-to-r' : '', 'bg-neutral-700 text-neutral-400']"> <span v-if="isLoading"
            class="loader"></span> <span v-if="!isLoading"> Continue<i class="uil uil-arrow-right"></i></span></button>
      </div>
    </div>
  </div>

  <div class="absolute bottom-6 left-0 right-0 flex flex-row justify-center text-neutral-500">
    <span>Made with <img src="./heart.png" alt="" class="mx-1 w-4 inline"> by <a href="https://twitter.com/samshot_01"
        target="_blank"
        class="font-medium from-green-600 via-cyan-400 to-green-500 bg-gradient-to-r bg-clip-text text-transparent">
        samshot_01</a></span>
  </div>

  <div v-if="showModal"
    class="backdrop-blur-sm flex flex-row justify-center bg-black top-0 bg-opacity-60 absolute text-blue-200 items-center w-screen h-screen">
    <div
      class="md:w-1/2 lg:w-2/5 xl:w-2/6 2xl:w-1/4 mx-3 p-7 bg-neutral-900 rounded-2xl from-gray-900 to-neutral-900 flex flex-col items-center  bg-gradient-to-r">
      <div class="flex flex-row justify-end mb-5 w-full">
        <button @click="showModal = false"
          class=" w-9 h-9 bg-gray-800 flex flex-row justify-center items-center rounded-lg "><i
            class="uil uil-times text-xl "></i></button>
      </div>
    <img src="./success.png" class="w-32" alt="">
    <p class=" text-2xl font-medium  text-center text-white mb-12 px-4">You have been added to the waitlist!
    </p>
    <p class=" text-base font-bold  text-center text-neutral-500 mb-12 "><span class="to-white via-cyan-400 from-green-500 bg-gradient-to-r bg-clip-text text-transparent">{{email}}</span> will be informed as soon as CopyNSync is
      ready!
    </p>
  </div>
</div></template>

<style scoped></style>
