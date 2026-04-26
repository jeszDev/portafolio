<template>
  <h1
    class="md:text-5xl font-black text-transparent bg-clip-text bg-gradient-to-r from-blue-600 via-purple-600 to-pink-600 mb-10 tracking-wider uppercase"
    style="font-family: 'Lobster', cursive;"
  >
    <span class="text-blue-400">&lt;</span>
    <span>{{ title }}</span>
    <span class="text-blue-400 animate-pulse intense-blink">/</span>
    <span class="text-blue-400">&gt;</span>
  </h1>
  <!-- <h1
    class="font-['Press_Start_2P'] md:text-5xl font-black text-transparent bg-clip-text bg-gradient-to-r from-blue-600 via-purple-600 to-pink-600 mb-10 tracking-wider"
  >
    <span class="font-['Syne_Mono'] text-blue-400">&lt;</span>
    {{ title }}
    <span class="font-['Syne_Mono'] text-blue-400 animate-pulse">/</span>
    <span class="font-['Syne_Mono'] text-blue-400">&gt;</span>
  </h1> -->

  <!-- <div class="crt-effect bg-black p-8 rounded-lg border-2 border-purple-500 inline-block">
    <h1
      class="font-['Press_Start_2P'] text-4xl md:text-5xl text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-fuchsia-500 tracking-tight text-flicker"
    >
      <span class="text-cyan-300">&lt;</span>
      <span class="text-white">{{ title }}</span>
      <span class="text-fuchsia-400 animate-pulse">/</span>
      <span class="text-cyan-300">&gt;</span>
    </h1>
  </div> -->
</template>

<script setup lang="ts">
interface Props {
  title: string;
}

defineProps<Props>();
</script>

<style scoped>
@keyframes intense-blink {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.2;
  }
}
</style>
