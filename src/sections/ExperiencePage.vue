<template>
  <section class="w-full gamer-experience relative mx-auto">
    <div class="flex justify-center mb-16">
      <TitleSection title="EXPERIENCIA" data-aos="fade-up" />
    </div>

    <div class="flex justify-center">
      <div class="w-full mx-auto px-4 relative border-l-2 border-slate-800 ml-6 md:mx-auto">
        <div class="mb-16 relative pl-8 group" data-aos="fade-left">
          <div
            class="absolute -left-[11px] top-1 w-5 h-5 bg-cyan-400 rounded-none rotate-45 shadow-[0_0_15px_rgba(34,211,238,0.8)] animate-pulse z-10"
          ></div>
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-2 mb-4">
            <div>
              <span
                class="text-[10px] font-mono text-cyan-400 tracking-[0.2em] block uppercase mb-1"
              >
                // CURRENT_MISSION_ACTIVE
              </span>
              <h3 class="text-2xl font-black text-white uppercase tracking-wide">
                Desarrollador Web
              </h3>
              <p class="text-sm text-slate-400 font-mono">
                Fiscalía General del Estado de Michoacán — Dirección de Tecnologías de la
                Información (DTI)
              </p>
            </div>
            <span
              class="font-mono text-xs px-3 py-1 bg-cyan-500/10 border border-cyan-500/30 text-cyan-400 self-start md:self-center uppercase tracking-wider"
            >
              Abril 2022 – En Curso
            </span>
          </div>

          <div
            class="mission-card p-6 bg-slate-950/40 border border-slate-800 rounded-xl backdrop-blur-sm relative"
          >
            <p class="text-slate-300 font-mono text-sm leading-relaxed mb-4">
              Desarrollo, soporte y refactorización de aplicaciones web institucionales críticas en
              producción, alineadas a los procesos administrativos y jurídicos de la Fiscalía.
            </p>

            <div class="grid md:grid-cols-2 gap-4 font-mono text-xs text-slate-400 mb-4">
              <div>
                <span class="text-cyan-500 block text-[10px] uppercase mb-1 tracking-wider"
                  >// CORE_TASKS:</span
                >
                <ul class="space-y-1.5">
                  <li class="flex items-start gap-2">
                    <span class="text-cyan-400 font-bold">&gt;</span> Implementación de módulos en
                    sistemas existentes.
                  </li>
                  <li class="flex items-start gap-2">
                    <span class="text-cyan-400 font-bold">&gt;</span> Análisis de requerimientos con
                    áreas usuarias.
                  </li>
                  <li class="flex items-start gap-2">
                    <span class="text-cyan-400 font-bold">&gt;</span> Soporte y optimización de
                    código en servidores de producción.
                  </li>
                </ul>
              </div>
              <div>
                <span class="text-purple-400 block text-[10px] uppercase mb-1 tracking-wider"
                  >// PLATAFORMAS_DESPLEGADAS:</span
                >
                <ul
                  class="space-y-1 bg-slate-950/50 p-2 border border-slate-900 rounded text-slate-300 text-[11px]"
                >
                  <li>• Sistema de Cartas de No Antecedentes</li>
                  <li>• Denuncia en Línea</li>
                  <li>
                    • Sistema ACCEIUS
                    <span class="text-slate-500 text-[10px]"
                      >(Módulos: Director de Carpetas, Denuncia en Línea, Agente MP)</span
                    >
                  </li>
                </ul>
              </div>
            </div>

            <div class="border-t border-slate-800/60 pt-4">
              <span class="text-[10px] text-slate-500 block uppercase mb-2 tracking-widest"
                >// REWARDS_EQUIPPED:</span
              >
              <div class="flex flex-wrap gap-2 text-[10px] font-bold text-cyan-400">
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >LARAVEL</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">PHP</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >SQL SERVER</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">MYSQL</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >LIVEWIRE</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >ALPINE.JS</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >JAVASCRIPT</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded"
                  >BOOTSTRAP</span
                >
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">GIT</span>
              </div>
            </div>
          </div>
        </div>

        <div class="mb-6 relative pl-8 group" data-aos="fade-left" data-aos-delay="100">
          <div
            class="absolute -left-[7px] top-2 w-3 h-3 bg-slate-700 rounded-none rotate-45 group-hover:bg-fuchsia-500 transition-colors z-10"
          ></div>

          <div class="flex flex-col md:flex-row md:items-center justify-between gap-2 mb-4">
            <div>
              <span
                class="text-[10px] font-mono text-slate-500 tracking-[0.2em] block uppercase mb-1"
              >
                // MISSION_ACCOMPLISHED
              </span>
              <h3
                class="text-xl md:text-2xl font-black text-slate-300 group-hover:text-white transition-colors uppercase tracking-wide"
              >
                Operador de Bodega de Indicios y Evidencias
              </h3>
              <p class="text-sm text-slate-500 font-mono">
                Fiscalía General del Estado de Michoacán — Unidad Técnica de Preservación y Manejo
                de Evidencias (UTPYME)
              </p>
            </div>
            <span
              class="font-mono text-xs px-3 py-1 bg-slate-800 border border-slate-700 text-slate-400 self-start md:self-center uppercase tracking-wider"
            >
              Oct 2017 – Mar 2022
            </span>
          </div>

          <div
            class="mission-card p-6 bg-slate-950/20 border border-slate-900 group-hover:border-slate-800 rounded-xl transition-all relative"
          >
            <div class="grid lg:grid-cols-12 gap-6 items-start">
              <div class="lg:col-span-6">
                <h4
                  class="text-xs font-bold text-slate-400 font-mono uppercase tracking-wider mb-3"
                >
                  // LOGISTICA_Y_CUSTODIA:
                </h4>
                <ul class="text-slate-400 font-mono text-xs leading-relaxed space-y-2">
                  <li class="flex items-start gap-2">
                    <span class="text-slate-600">&gt;</span> Recepción, verificación y resguardo
                    especializado de indicios según su naturaleza (biológicos, armas, digital).
                  </li>
                  <li class="flex items-start gap-2">
                    <span class="text-slate-600">&gt;</span> Control riguroso de trazabilidad,
                    documentación de entradas y salidas para asegurar la Cadena de Custodia en el
                    proceso penal.
                  </li>
                  <li class="flex items-start gap-2">
                    <span class="text-slate-600">&gt;</span> Conservación a largo plazo y atención
                    de disponibilidad para peritos, fiscales y jueces.
                  </li>
                </ul>
              </div>

              <div
                class="lg:col-span-6 p-4 border border-fuchsia-500/20 bg-fuchsia-950/10 rounded-lg relative overflow-hidden"
              >
                <div
                  class="absolute top-0 right-0 w-16 h-16 bg-fuchsia-500/5 rotate-45 translate-x-8 -translate-y-8 pointer-events-none"
                ></div>

                <h4
                  class="text-[10px] font-bold text-fuchsia-400 font-mono uppercase tracking-[0.15em] mb-1 flex items-center gap-1.5"
                >
                  🏆 LOGRO DESBLOQUEADO
                </h4>
                <h5 class="text-white font-mono text-xs font-bold mb-2 leading-tight">
                  Desarrollo de Sistema Web para Cadena de Custodia y Evidencias
                </h5>

                <div class="space-y-3 text-[11px] text-slate-300 font-mono leading-relaxed">
                  <p>
                    A partir de mi experiencia de campo, programé un sistema bajo roles para
                    digitalizar la bodega, optimizar el seguimiento y eliminar errores manuales.
                  </p>

                  <div class="grid grid-cols-2 gap-2 text-[10px]">
                    <div class="p-1.5 bg-slate-950/60 rounded border border-slate-900">
                      <span class="text-cyan-400 block font-bold mb-0.5">1. REGISTRO_CAMPO</span>
                      <p class="text-slate-400 text-[9px] leading-tight">
                        Para MP, Peritos y Policías. Automatiza Anexos 3, 4 y etiquetas.
                      </p>
                    </div>
                    <div class="p-1.5 bg-slate-950/60 rounded border border-slate-900">
                      <span class="text-fuchsia-400 block font-bold mb-0.5">2. RE_BODEGA</span>
                      <p class="text-slate-400 text-[9px] leading-tight">
                        Control de estatus, préstamos, bajas e indicadores de flujo.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="border-t border-slate-900 pt-4 mt-6">
              <span class="text-[10px] text-slate-600 block uppercase mb-2 tracking-widest"
                >// TECH_CRAFTED:</span
              >
              <div
                class="flex flex-wrap gap-2 text-[10px] font-bold text-fuchsia-400/60 group-hover:text-fuchsia-400 transition-colors"
              >
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">PHP</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded"
                  >LARAVEL</span
                >
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">MYSQL</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">JQUERY</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded"
                  >BOOTSTRAP</span
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap');

.gamer-experience {
  font-family: 'JetBrains Mono', monospace;
}

/* Tarjeta de misión con corte tecnológico angular */
.mission-card {
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
  clip-path: polygon(0 0, 98% 0, 100% 4%, 100% 100%, 0 100%);
  transition:
    transform 0.2s ease,
    border-color 0.2s ease;
}

.group:hover .mission-card {
  transform: translateY(-2px);
  background: rgba(15, 23, 42, 0.3);
}
</style>
