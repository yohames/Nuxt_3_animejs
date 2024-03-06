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

    <div class="snap-x flex snap-mandatory overflow-auto">
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1604999565976-8913ad2ddb7c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1540206351-d6465b3ac5c1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1622890806166-111d7f6c7c97?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1575424909138-46b05e5919ec?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1559333086-b0a56225a93c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1575424909138-46b05e5919ec?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-always snap-center ...">
        <img
          src="https://images.unsplash.com/photo-1559333086-b0a56225a93c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
    </div>
    <div class="snap-y snap-mandatory flex gap-20 mx-auto w-full overflow-auto">
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1604999565976-8913ad2ddb7c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1540206351-d6465b3ac5c1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1622890806166-111d7f6c7c97?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1575424909138-46b05e5919ec?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1559333086-b0a56225a93c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1604999565976-8913ad2ddb7c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1540206351-d6465b3ac5c1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1622890806166-111d7f6c7c97?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
      <div class="snap-center snap-always min-w-[20rem] h-[20rem]">
        <img
          src="https://images.unsplash.com/photo-1575424909138-46b05e5919ec?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=320&h=160&q=80"
        />
      </div>
    </div>

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
        class="snap-always snap-center snap-always min-w-[20rem] h-[20rem] sticky top-40 min-w-[70%] rounded-lg text-6xl"
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
