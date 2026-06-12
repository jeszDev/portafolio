<script setup lang="ts">
defineProps<{
  title: string
  description: string
  image: string
  tech: string[]
  demo: string
  github: string
}>()

const emit = defineEmits<{
  (e: 'open-details'): void
}>()
</script>

<template>
  <div
    @click="emit('open-details')"
    class="group relative rounded-xl overflow-hidden cursor-pointer transition-transform duration-300 hover:-translate-y-2 border border-slate-900 hover:border-cyan-500/30"
  >

    <!-- IMAGE -->
    <img
      :src="image"
      class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110"
    />

    <!-- OVERLAY -->
    <div class="absolute inset-0 bg-black/80 opacity-0 group-hover:opacity-100 transition duration-300 flex flex-col justify-end p-6">

      <h3 class="text-xl font-bold mb-2 text-white font-mono">{{ title }}</h3>

      <p class="text-sm text-white/70 mb-[10px]! line-clamp-2">
        {{ description }}
      </p>

      <!-- TECH -->
      <div class="flex flex-wrap gap-2 mb-[10px]! mb-4">
        <span
          v-for="techItem in tech"
          :key="techItem"
          class="text-[10px] bg-slate-900/60 border border-slate-800 text-slate-300 px-2 py-0.5 rounded font-mono"
        >
          {{ techItem }}
        </span>
      </div>

      <!-- BUTTONS -->
      <div class="flex gap-2 flex-wrap">
        <button @click.stop="emit('open-details')" class="btn-details font-mono text-xs cursor-pointer">
          Detalles
        </button>

        <a
          v-if="demo && demo !== '#'"
          :href="demo"
          target="_blank"
          @click.stop
          class="btn-primary font-mono text-xs"
        >
          Demo
        </a>

        <a
          v-if="github && github !== '#'"
          :href="github"
          target="_blank"
          @click.stop
          class="btn-secondary font-mono text-xs"
        >
          Code
        </a>
      </div>
    </div>

  </div>
</template>

<style scoped>
.btn-details {
  background: #06b6d4; /* cyan-500 */
  color: #000;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
  font-weight: bold;
  transition: all 0.2s ease;
  box-shadow: 0 0 8px rgba(6, 182, 212, 0.4);
}

.btn-details:hover {
  background: #22d3ee; /* cyan-400 */
  box-shadow: 0 0 12px rgba(6, 182, 212, 0.7);
  transform: translateY(-1px);
}

.btn-primary {
  background: #10b981;
  color: white;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
  transition: all 0.2s ease;
}

.btn-primary:hover {
  background: #059669;
  transform: translateY(-1px);
}

.btn-secondary {
  border: 1px solid rgba(255,255,255,0.3);
  color: white;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
  transition: all 0.2s ease;
}

.btn-secondary:hover {
  border-color: rgba(255,255,255,0.6);
  background: rgba(255,255,255,0.05);
  transform: translateY(-1px);
}
</style>
