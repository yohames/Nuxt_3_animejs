<script setup>
import { useWindowScroll } from "@vueuse/core";

const { $anime } = useNuxtApp();
const { x, y } = useWindowScroll();
function handleScroll(event) {}

onMounted(() => {
  console.log("fire scroll trigger");

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

const dynamicClass = computed(() => {
  return `scale-[${y.value}]}`;
});
</script>
<template>
  <div class="flex flex-col m-20">
    <NuxtLink
      to="/"
      class="bg-gray-100 shadow-lg flex justify-center ring-1 ring-gray-300 hover:bg-gray-200 duration-300 items-center self-start w-40 px-5 rounded-lg py-2"
      >Back</NuxtLink>
    <div class="sticky top-10 -ml-10">hello</div>

    <div class="flex flex-col gap-y-10">
      <div
        id="card"
        v-for="i in 5"
        class="sticky top-40 min-w-[70%] rounded-lg text-6xl"
      >
        <div class="min-h-screen">
          <div
            class="bg-red-100 h-[50vh] flex items-center justify-center rounded-2xl"
            :class="dynamicClass"
          >
            {{ `scale-[${y / 100}] bg-red-${i * 100}` }}
            Test
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
