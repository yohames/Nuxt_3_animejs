<script setup>
const { $anime } = useNuxtApp();
import { useWindowScroll } from '@vueuse/core'

function handleScroll(event) {
  console.log("fire scroll trigger", event);
}

onMounted(() => {
  const cards = document.querySelector("#cards");
  const card = document.querySelector("#card");
  // function fireScroll(event) {
  //   console.log("fire scroll trigger", event);
  // }
  // window.onscroll = () => {};
  // window.onscroll = () => {
  //   console.log("show scroll trigger");
  // };
  // card.addEventListener("scroll", (event) => {
  //   console.log("show scroll");
  //   card.innerHTML = "Scroll event fired!";
  //   setTimeout(() => {
  //     card.innerHTML = "Waiting on scroll events...";
  //     console.log("scrolling");
  //   }, 1000);
  // });

  // function fireScroll(){

  // }

  // $anime({
  //   targets: "#cards",
  //   scale: 0,
  //   translateX: [0, 300, -600, 0],
  //   elasticity: 200,
  //   easing: "easeInOutCubic",
  //   autoplay: false,
  //   opacity: 0.7,
  // });
});
</script>
<template>
  <div class="m-20">
    <NuxtLink
      to="/"
      class="bg-gray-100 shadow-lg flex justify-center ring-1 ring-gray-300 hover:bg-gray-200 duration-300 items-center self-start w-40 px-5 rounded-lg py-2"
      >Back</NuxtLink
    >
    <ul
      class="flex flex-col gap-y-5 my-10 items-center py-10 bg-red-400 max-h-[85vh] overflow-y-auto"
      @scroll="handleScroll"
      id="cards"
    >
      <div
        id="card"
        v-for="i in 5"
        class="bg-green-100 min-w-[70%] min-h-[70vh] rounded-lg skew-y-3 text-red-600 text-6xl"
      ></div>
    </ul>
  </div>
</template>

<style scoped></style>
