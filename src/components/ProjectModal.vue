<script setup lang="ts">
import { watch, onBeforeUnmount } from 'vue';

interface Project {
  title: string
  description: string
  image: string
  tech: string[]
  demo: string
  github: string
  detailedDescription?: string
  role?: string
  date?: string
  status?: string
  features?: string[]
}

const props = defineProps<{
  project: Project | null
  isOpen: boolean
}>()

const emit = defineEmits<{
  (e: 'close'): void
}>()

const handleKeyDown = (e: KeyboardEvent) => {
  if (e.key === 'Escape') {
    emit('close');
  }
};

watch(() => props.isOpen, (newVal) => {
  if (newVal) {
    window.addEventListener('keydown', handleKeyDown);
    document.body.style.overflow = 'hidden';
  } else {
    window.removeEventListener('keydown', handleKeyDown);
    document.body.style.overflow = '';
  }
}, { immediate: true });

onBeforeUnmount(() => {
  window.removeEventListener('keydown', handleKeyDown);
  document.body.style.overflow = '';
});
</script>

<template>
  <Transition name="fade">
    <div
      v-if="isOpen && project"
      class="fixed inset-0 z-50 flex items-center justify-center p-4 md:p-6 bg-slate-950/85 backdrop-blur-md"
      @click.self="emit('close')"
    >
      <div
        class="relative w-full max-w-4xl max-h-[90vh] flex flex-col bg-slate-950 border border-cyan-500/30 rounded-xl overflow-hidden shadow-[0_0_40px_rgba(34,211,238,0.15)] data-file-card"
        @click.stop
      >
        <!-- Corner brackets -->
        <div class="absolute top-0 left-0 w-4 h-4 border-t-2 border-l-2 border-cyan-400"></div>
        <div class="absolute top-0 right-0 w-4 h-4 border-t-2 border-r-2 border-cyan-400"></div>
        <div class="absolute bottom-0 left-0 w-4 h-4 border-b-2 border-l-2 border-cyan-400"></div>
        <div class="absolute bottom-0 right-0 w-4 h-4 border-b-2 border-r-2 border-cyan-400"></div>

        <!-- Top bar (cyberpunk-ish) -->
        <div
          class="px-6 py-3 border-b border-slate-900 bg-slate-950/80 flex items-center justify-between select-none"
        >
          <span class="text-[9px] font-mono text-cyan-400/60 tracking-[0.25em] uppercase">
            // ACCESS_GRANTED // PROJECT_DOSSIER: {{ project.title }}
          </span>
          <button
            @click="emit('close')"
            class="text-slate-400 hover:text-cyan-400 font-mono text-xs transition-colors flex items-center gap-1 cursor-pointer"
          >
            <span>[ ESC_CLOSE ]</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

        <!-- Scrollable Content -->
        <div class="flex-1 overflow-y-auto p-6 md:p-8">
          <div class="grid md:grid-cols-12 gap-8">
            <!-- Left Column (Visuals) -->
            <div class="md:col-span-5 flex flex-col gap-4">
              <div
                class="relative rounded-lg overflow-hidden border border-slate-800 bg-slate-900/50 aspect-video md:aspect-auto md:h-64 flex items-center justify-center group/img shadow-[inset_0_0_20px_rgba(0,0,0,0.8)]"
              >
                <!-- Scanline effect / futuristic overlay -->
                <div class="absolute inset-0 bg-scanlines pointer-events-none opacity-20"></div>
                <img
                  :src="project.image"
                  class="w-full h-full object-cover group-hover/img:scale-105 transition-transform duration-500"
                  :alt="project.title"
                />
              </div>

              <!-- Metadata cards -->
              <div class="grid grid-cols-2 gap-3 font-mono text-xs">
                <div class="p-3 bg-slate-900/30 border border-slate-800/80 rounded-lg">
                  <span class="text-slate-500 block uppercase text-[8px] tracking-widest"
                    >// ROLE //</span
                  >
                  <span class="text-slate-200 font-bold">{{ project.role || 'Developer' }}</span>
                </div>
                <div class="p-3 bg-slate-900/30 border border-slate-800/80 rounded-lg">
                  <span class="text-slate-500 block uppercase text-[8px] tracking-widest"
                    >// DATE //</span
                  >
                  <span class="text-slate-200 font-bold">{{ project.date || 'N/A' }}</span>
                </div>
                <div
                  class="col-span-2 p-3 bg-slate-900/30 border border-slate-800/80 rounded-lg flex items-center justify-between"
                >
                  <div>
                    <span class="text-slate-500 block uppercase text-[8px] tracking-widest"
                      >// SYSTEM_STATUS //</span
                    >
                    <span class="text-emerald-400 font-bold text-xs animate-pulse">{{
                      project.status || 'COMPLETED // ONLINE'
                    }}</span>
                  </div>
                  <span
                    class="w-2 h-2 rounded-full bg-emerald-400 shadow-[0_0_8px_rgba(52,211,153,0.8)]"
                  ></span>
                </div>
              </div>
            </div>

            <!-- Right Column (Details) -->
            <div class="md:col-span-7 flex flex-col gap-6 font-mono text-sm">
              <div>
                <h2 class="text-2xl md:text-3xl font-black text-white uppercase tracking-wide mb-2">
                  {{ project.title }}
                </h2>
                <div class="h-[2px] w-20 bg-gradient-to-r from-cyan-400 to-transparent"></div>
              </div>

              <!-- Detailed Description -->
              <div class="text-slate-350 leading-relaxed space-y-3 text-justify">
                <p>{{ project.detailedDescription || project.description }}</p>
              </div>

              <!-- Features (Missions) -->
              <div v-if="project.features && project.features.length">
                <h4
                  class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-3 flex items-center gap-1.5 select-none"
                >
                  <span class="w-1.5 h-1.5 bg-cyan-400 animate-pulse"></span>
                  // CLAVES_DE_MISION (FEATURES)
                </h4>
                <ul class="space-y-2.5 text-xs text-slate-400">
                  <li
                    v-for="(feat, fIdx) in project.features"
                    :key="fIdx"
                    class="flex items-start gap-2 leading-relaxed"
                  >
                    <span class="text-cyan-400 font-bold select-none">&gt;</span>
                    <span>{{ feat }}</span>
                  </li>
                </ul>
              </div>

              <!-- Tech Stack -->
              <div>
                <h4
                  class="text-xs font-bold text-fuchsia-400 uppercase tracking-widest mb-3 flex items-center gap-1.5 select-none"
                >
                  <span class="w-1.5 h-1.5 bg-fuchsia-400 animate-pulse"></span>
                  // EQUIPAMIENTO_TEC (TECH)
                </h4>
                <div class="flex flex-wrap gap-2">
                  <span v-for="tItem in project.tech" :key="tItem" class="skill-tag">
                    {{ tItem }}
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Action Buttons Footer -->
        <div
          class="px-6 py-4 border-t border-slate-900 bg-slate-950/90 flex flex-wrap gap-3 items-center justify-end"
        >
          <a
            v-if="project.demo && project.demo !== '#'"
            :href="project.demo"
            target="_blank"
            class="btn-primary-glow font-mono text-xs uppercase tracking-wider flex items-center gap-1"
          >
            <span>PROBAR DEMO</span>
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
              />
            </svg>
          </a>
          <span v-else class="btn-disabled font-mono text-xs uppercase tracking-wider select-none">
            DEMO // OFFLINE
          </span>

          <a
            v-if="project.github && project.github !== '#'"
            :href="project.github"
            target="_blank"
            class="btn-secondary-glow font-mono text-xs uppercase tracking-wider flex items-center gap-1"
          >
            <span>VER CÓDIGO</span>
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
              />
            </svg>
          </a>
          <span v-else class="btn-disabled font-mono text-xs uppercase tracking-wider select-none">
            CÓDIGO // CLASSIFIED
          </span>

          <button
            @click="emit('close')"
            class="btn-close-terminal font-mono text-xs uppercase tracking-wider cursor-pointer"
          >
            Cerrar
          </button>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap');

.font-mono {
  font-family: 'JetBrains Mono', monospace;
}

.data-file-card {
  box-shadow:
    inset 0 0 25px rgba(34, 211, 238, 0.05),
    0 20px 50px rgba(0, 0, 0, 0.8);
  clip-path: polygon(0 0, 97% 0, 100% 3%, 100% 100%, 0 100%);
}

.bg-scanlines {
  background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%),
    linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
  background-size:
    100% 4px,
    6px 100%;
}

.skill-tag {
  font-size: 10px;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  background: rgba(15, 23, 42, 0.6);
  border: 1px solid rgba(240, 46, 170, 0.3);
  color: #d946ef;
  transition: all 0.2s ease;
}

.skill-tag:hover {
  transform: translateY(-1px);
  background: rgba(240, 46, 170, 0.15);
  box-shadow: 0 0 8px rgba(240, 46, 170, 0.3);
  color: #fff;
}

.btn-primary-glow {
  background: #10b981;
  border: 1px solid #34d399;
  color: white;
  padding: 8px 16px;
  border-radius: 6px;
  box-shadow: 0 0 10px rgba(16, 185, 129, 0.3);
  transition: all 0.2s ease;
  cursor: pointer;
}

.btn-primary-glow:hover {
  background: #059669;
  box-shadow: 0 0 15px rgba(16, 185, 129, 0.6);
  transform: translateY(-1px);
}

.btn-secondary-glow {
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: #e2e8f0;
  padding: 8px 16px;
  border-radius: 6px;
  transition: all 0.2s ease;
  cursor: pointer;
}

.btn-secondary-glow:hover {
  border-color: #22d3ee;
  color: white;
  box-shadow: 0 0 10px rgba(34, 211, 238, 0.3);
  transform: translateY(-1px);
}

.btn-disabled {
  background: rgba(30, 41, 59, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.05);
  color: #64748b;
  padding: 8px 16px;
  border-radius: 6px;
  cursor: not-allowed;
}

.btn-close-terminal {
  background: #ef4444;
  border: 1px solid #f87171;
  color: white;
  padding: 8px 16px;
  border-radius: 6px;
  transition: all 0.2s ease;
  cursor: pointer;
}

.btn-close-terminal:hover {
  background: #dc2626;
  box-shadow: 0 0 10px rgba(239, 68, 68, 0.4);
  transform: translateY(-1px);
}

/* Transitions */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active .data-file-card,
.fade-leave-active .data-file-card {
  transition: transform 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.fade-enter-from .data-file-card {
  transform: scale(0.95) translateY(10px);
}

.fade-leave-to .data-file-card {
  transform: scale(0.95) translateY(10px);
}
</style>
