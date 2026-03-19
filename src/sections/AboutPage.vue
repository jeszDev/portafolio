<template>
  <!-- Titulo (10%) -->
  <div class="flex items-center justify-center">
    <TitleSection title="Acerca de mí" />
  </div>

  <!-- Terminal (90%) -->
  <div class="flex items-center justify-center">
    <ExperienceTimeLine />
  </div>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
import ExperienceTimeLine from '../components/ExperienceTimeLine.vue';
</script>

<style scoped></style>
