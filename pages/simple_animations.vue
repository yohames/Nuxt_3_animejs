<script setup>
const { $anime } = useNuxtApp();

var battery = {
  charged: "0%",
  cycles: 120,
};
onMounted(() => {
  var counter = document.querySelector("#counter");
  var battery = {
    charged: "0%",
    cycles: 120,
  };
  $anime({
    targets: "#redSquare",
    translateX: 250,
    loop: true,
    easing: "easeInOutCubic",
  });
  $anime({
    targets: "#counter",
    innerHTML: [0, 100],
    duration: 2500,
    round: 1,
    easing: "easeOutExpo",
  });
  //   $anime({
  //     targets: "#counter",
  //     value: [0, 100],
  //     duration: 3000,
  //     round: 1,
  //     easing: "easeOutExpo",
  //   });
});
</script>
<template>
  <div class="flex flex-col gap-y-10 m-20">
    <NuxtLink
      to="/"
      class="bg-gray-100 shadow-lg flex justify-center ring-1 ring-gray-300 hover:bg-gray-200 duration-300 items-center self-start w-40 px-5 rounded-lg py-2"
      >Back</NuxtLink
    >
    <div class="mt-10">
      <h1>Square</h1>
      <div class="w-5 h-5 bg-red-600" id="redSquare"></div>
    </div>
    <div>
      <h1>Numerical Value</h1>
      <div class="text-4xl font-black text-red-600" id="counter"></div>
    </div>
  </div>
</template>

<style scoped></style>
