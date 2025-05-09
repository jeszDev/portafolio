<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import DeveloperTerminal from '@/components/DeveloperTerminal.vue'
</script>

<template>
  <!-- <main>
    <TheWelcome />
  </main> -->
  <div class="flex justify-center" id="welcome">
    <h1>Bienvenido</h1>
  </div>

  <div class="">
    <DeveloperTerminal />
  </div>
</template>

<style scoped>
h1 {
  display: inline;
  position: relative;
  font:
    130px Helvetica,
    Sans-Serif;
  letter-spacing: -5px;
  color: white;
}

h1:after {
  content: 'Bienvenido';
  position: absolute;
  left: 10px;
  top: 5px;
  color: hsla(160, 100%, 37%, 1);
}
</style>
