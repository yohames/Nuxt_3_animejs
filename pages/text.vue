<script setup>
const { $anime } = useNuxtApp();

onMounted(() => {
  var textWrapper = document.querySelector(".ml10 .letters");
  textWrapper.innerHTML = textWrapper.textContent.replace(
    /\S/g,
    "<span class='letter' style='display: inline-block;'>$&</span>"
  );

  $anime
    .timeline({ loop: false, direction: "alternate" })
    .add({
      targets: ".ml10 .letter",
      loop: false,
      rotateY: [-90, 0],
      duration: 1300,
      //   color: [
      //     "#facc15",
      //     "#a3e635",
      //     "#4ade80",
      //     "#34d399",
      //     "#2dd4bf",
      //     "#2dd4bf",
      //     "#22d3ee",
      //     "#38bdf8",
      //   ],
      delay: (el, i) => 45 * i,
    })
    .add({
      targets: ".ml10",
      //   color: [
      //     "#facc15",
      //     "#a3e635",
      //     "#4ade80",
      //     "#34d399",
      //     "#2dd4bf",
      //     "#2dd4bf",
      //     "#22d3ee",
      //     "#38bdf8",
      //   ],
      duration: 1000,
      easing: "easeOutExpo",
      delay: 1000,
      update: function (params) {
        textWrapper.innerHTML = textWrapper.textContent;
      },
    });
  $anime.timeline({ loop: true, direction: "alternate" }).add({
    targets: ".ml10 .letter",
    duration: 5000,
    // color: [
    //   "#facc15",
    //   "#a3e635",
    //   "#4ade80",
    //   "#34d399",
    //   "#2dd4bf",
    //   "#2dd4bf",
    //   "#22d3ee",
    //   "#38bdf8",
    // ],
    delay: (el, i) => 45 * i,
  });

  //   ================================ M7 ================================
  var ml7textWrapper = document.querySelector(".ml7 .letters");
  ml7textWrapper.innerHTML = ml7textWrapper.textContent.replace(
    /\S/g,
    "<span class='letter' style='display: inline-block;'>$&</span>"
  );

  $anime
    .timeline({ loop: true })
    .add({
      targets: ".ml7 .letter",
      translateY: ["4.5em", 0],
      translateX: ["0.55em", 0],
      translateZ: 0,
      rotateZ: [40, 0],
      duration: 750,
      easing: "easeOutExpo",
      delay: (el, i) => 50 * i,
    })
    .add({
      targets: ".ml7",
      opacity: 0,
      duration: 1000,
      easing: "easeOutExpo",
      delay: 1000,
    });

  //   ================================ M13 ================================
  var m13textWrapper = document.querySelector(".ml13");
  m13textWrapper.innerHTML = m13textWrapper.textContent.replace(
    /\S/g,
    "<span class='letter' style='display: inline-block;'>$&</span>"
  );

  $anime
    .timeline({ loop: true })
    .add({
      targets: ".ml13 .letter",
      translateY: [100, 0],
      translateZ: 0,
      opacity: [0, 1],
      easing: "easeOutExpo",
      color: ["hsl(250, 75%, 50%)", "hsl(200, 50%, 50%)"],
      duration: 1400,
      delay: (el, i) => 300 + 30 * i,
    })
    .add({
      targets: ".ml13 .letter",
      translateY: [0, -100],
      opacity: [1, 0],
      easing: "easeInExpo",
      duration: 1200,
      delay: (el, i) => 100 + 30 * i,
    });
});
</script>
<template>
  <div class="p-10 flex flex-col gap-y-20">
    <div
      class="text-5xl text-gray-500 font-bold text-center bg-gradient-to-r bg-clip-text text-transparent from-green-300 via-cyan-600 to-orange-400 animate-text"
    >
      Text Animation
    </div>
    <div class="bg-green-100 px-10 py-5 rounded-xl shadow-xl">
      <h1>Effect 10</h1>
      <h1 class="ml10 max-w-[38rem] text-center">
        <span class="text-wrapper">
          <span
            class="letters text-sky-400 duration-500 transition-all tracking-[0.11px]"
            >Elevate Your Brand with a trailblazing Digital Creator</span
          >
        </span>
      </h1>
    </div>
    <div class="bg-green-100 px-10 py-5 rounded-xl shadow-xl">
      <h1 class="font-semibold text-xl">Effect 7</h1>
      <h1 class="ml7 max-w-[42rem] text-center">
        <span
          class="text-wrapper bg-gradient-to-r bg-clip-text text-transparent from-primary via-cyan-600 to-PrimaryOrange animate-text"
        >
          <span class="letters"
            >Elevate Your Brand with a trailblazing Digital Creator</span
          >
        </span>
      </h1>
    </div>
    <div
      class="flex justify-center text-center px-10 py-5 bg-red-100 rounded-lg shadow-xl"
    >
      <h1 class="ml13">
        Elevate Your Brand with a trailblazing Digital Creator
      </h1>
    </div>
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

/* ================================ M13 ================================ */
.ml13 {
  font-size: 1.9em;
  text-transform: uppercase;
  letter-spacing: 0.5em;
  font-weight: 600;
}

.ml13 .letter {
  display: inline-block;
  line-height: 1em;
}

/* ================================ M7 ANIMATION ================================ */
.ml10 {
  position: relative;
  font-weight: 900;
  font-size: 4em;
}

.ml10 .text-wrapper {
  position: relative;
  display: inline-block;
  padding-top: 0.2em;
  padding-right: 0.05em;
  padding-bottom: 0.1em;
  overflow: hidden;
}

.ml10 .letter {
  display: inline-block;
  line-height: 1em;
  transform-origin: 0 0;
}
</style>
