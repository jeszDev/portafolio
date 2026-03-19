<template>
  <!-- Titulo (10%) -->
  <div class="flex items-center justify-center">
    <TitleSection title="Proyectos" />
  </div>

  <!-- Terminal (90%) -->
  <div class="grid grid-cols-3 gap-4">
    <!-- component -->
    <ProjectItem />
    <ProjectItem />
    <ProjectItem />
    <ProjectItem />
    <ProjectItem />
  </div>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
import ProjectItem from '../components/ProjectItem.vue';
</script>

<style scoped></style>
