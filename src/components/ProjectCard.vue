<script setup lang="ts">
defineProps<{
  title: string
  description: string
  image: string
  tech: string[]
  demo: string
  github: string
}>()
</script>

<template>
  <div class="group relative rounded-xl overflow-hidden cursor-pointer transition-transform duration-300 hover:-translate-y-2">

    <!-- IMAGE -->
    <img
      :src="image"
      class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110"
    />

    <!-- OVERLAY -->
    <div class="absolute inset-0 bg-black/70 opacity-0 group-hover:opacity-100 transition duration-300 flex flex-col justify-end p-6">

      <h3 class="text-xl font-bold mb-2">{{ title }}</h3>

      <p class="text-sm text-white/70 mb-[10px]!">
        {{ description }}
      </p>

      <!-- TECH -->
      <div class="flex flex-wrap gap-2 mb-[10px]!">
        <span
          v-for="techItem in tech"
          :key="techItem"
          class="text-xs bg-white/10 px-2 py-1 rounded"
        >
          {{ techItem }}
        </span>
      </div>

      <!-- BUTTONS -->
      <div class="flex gap-3">
        <a :href="demo" target="_blank" class="btn-primary">
          Demo
        </a>

        <a :href="github" target="_blank" class="btn-secondary">
          Code
        </a>
      </div>
    </div>

  </div>
</template>

<style scoped>
.btn-primary {
  background: #10b981;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
}

.btn-secondary {
  border: 1px solid rgba(255,255,255,0.3);
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
}
</style>
