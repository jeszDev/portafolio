<template>
  <!-- Titulo (10%) -->
  <div class="flex items-center justify-center">
    <TitleSection title="Bienvenido" />
  </div>

  <!-- Terminal (90%) -->
  <div class="flex items-center justify-center">
    <DeveloperTerminal />
  </div>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
import DeveloperTerminal from '@/components/DeveloperTerminal.vue';
</script>

<style scoped></style>
