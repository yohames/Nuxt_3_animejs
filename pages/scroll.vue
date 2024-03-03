<script setup>
import { useWindowScroll } from "@vueuse/core";

const { $anime } = useNuxtApp();

onMounted(() => {
  console.log("fire scroll trigger");
  let animation = $anime({
    targets: "#card",
    scale: 0,
    translateX: [0, 300, -600, 0],
    elasticity: 200,
    easing: "easeInOutCubic",
    autoplay: false,
    opacity: 0.7,
  });
  const cards = document.querySelector("#cards");

  window.onscroll = function () {
    const scrollPercent = window.pageYOffset - cards.offsetTop;
    console.log("cards", scrollPercent, window.pageYOffset, cards.pageYOffset);
    animation.seek((scrollPercent / 5000) * animation.duration);
  };
});

const currentCard = ref(0);
</script>
<template>
  <div class="flex flex-col">
    <NuxtLink
      to="/"
      class="bg-gray-100 shadow-lg flex justify-center ring-1 ring-gray-300 hover:bg-gray-200 duration-300 items-center self-start w-40 px-5 rounded-lg py-2"
      >Back</NuxtLink
    >
    <div v-for="i in 5" class="py-20">hello</div>

    <div class="snap-y snap-mandatory flex flex-col gap-y-10 p-20" id="cards">
      <div
        id="card"
        v-for="i in [
          'bg-green-100',
          'bg-green-200',
          'bg-green-300',
          'bg-green-400',
          'bg-green-500',
          'bg-green-600',
          'bg-green-700',
        ]"
        class="snap-always snap-center sticky top-40 min-w-[70%] rounded-lg text-6xl"
      >
        <div class="min-h-screen">
          <div
            class="h-[50vh] flex items-center justify-center rounded-2xl ring-1 ring-red-500"
            :class="i"
          >
            Test
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
