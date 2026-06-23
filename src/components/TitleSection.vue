<template>
  <div class="mb-10 text-left">
    <span class="text-[10px] font-mono text-cyan-400/50 block tracking-[0.3em] uppercase mb-1">
      // LOCATION: {{ title }}
    </span>

    <h1
      class="font-arcade text-xl md:text-4xl font-bold tracking-tighter text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-purple-500 uppercase flex items-center gap-2"
    >
      <span class="text-cyan-500 font-mono">&lt;</span>
      <span class="text-white">{{ title }}</span>
      <span class="text-fuchsia-500 font-mono animate-ping text-4xl">/</span>
      <span class="text-cyan-500 font-mono">&gt;</span>
    </h1>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title: string;
}

defineProps<Props>();
</script>

<style scoped>
.font-arcade {
  font-family: 'Share Tech Mono', 'Orbitron', 'Press Start 2P', cursive;
}
</style>
