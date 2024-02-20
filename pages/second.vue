<script setup>
const { $anime } = useNuxtApp();

onMounted(() => {
  var textWrapper = document.querySelector(".ml7 .letters");
  textWrapper.innerHTML = textWrapper.textContent.replace(
    /\S/g,
    "<span class='letter'>$&</span>"
  );
  $anime
    .timeline({
      loop: true,
      targets: ".ml7 .letter",
      translateY: ["1.1em", 0],
      translateX: ["0.55em", 0],
      translateZ: 0,
      rotateZ: [180, 0],
      duration: 750,
      easing: "easeOutExpo",
      delay: (el, i) => 50 * i,
    })
    // .add({
    //   targets: ".ml7 .letter",
    //   translateY: ["1.1em", 0],
    //   translateX: ["0.55em", 0],
    //   translateZ: 0,
    //   rotateZ: [180, 0],
    //   duration: 750,
    //   easing: "easeOutExpo",
    //   delay: (el, i) => 50 * i,
    // })
    .add({
      targets: ".ml7",
      opacity: 0,
      duration: 1000,
      easing: "easeOutExpo",
      delay: 1000,
    });

  //   $anime({
  //     targets: "path",
  //     loop: true,
  //     direction: "alternate",
  //     strokeDashoffset: [$anime.setDashoffset, 0],
  //     easing: "easeInOutSine",
  //     duration: 700,
  //     delay: (el, i) => {
  //       return i * 500;
  //     },
  //   });
});
</script>
<template>
  <div>
    <NuxtLink to="/">Back</NuxtLink>
    <h1 class="ml7">
      <span class="text-wrapper">
        <span
          class="letters bg-gradient-to-r from-blue-600 via-green-500 to-indigo-400 inline-block text-transparent bg-clip-text"
          >Reality is broken</span
        >
      </span>
    </h1>
  </div>
</template>

<style scoped>
.ml7 {
  position: relative;
  font-weight: 900;
  font-size: 3.7em;
}
.ml7 .text-wrapper {
  position: relative;
  display: inline-block;
  padding-top: 0.2em;
  padding-right: 0.05em;
  padding-bottom: 0.1em;
  overflow: hidden;
}
.ml7 .letter {
  transform-origin: 0 100%;
  display: inline-block;
  line-height: 1em;
}
</style>
