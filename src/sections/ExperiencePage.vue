
<template>
  <section class="w-full py-12 gamer-experience relative">
    <div class="flex justify-center mb-16">
      <TitleSection title="EXPERIENCIA" data-aos="fade-up" />
    </div>

    <div class="flex justify-center">
      <div class="md:w-[80%] mx-auto px-4 relative border-l-2 border-slate-800 ml-6 md:mx-auto">
        <div class="mb-16 relative pl-8 group" data-aos="fade-left">
          <div class="absolute -left-[11px] top-1 w-5 h-5 bg-cyan-400 rounded-none rotate-45 shadow-[0_0_15px_rgba(34,211,238,0.8)] animate-pulse z-10"></div>
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-2 mb-4">
            <div>
              <span class="text-[10px] font-mono text-cyan-400 tracking-[0.2em] block uppercase mb-1">
                // CURRENT_MISSION_ACTIVE
              </span>
              <h3 class="text-2xl font-black text-white uppercase tracking-wide">
                Desarrollador Web
              </h3>
              <p class="text-sm text-slate-400 font-mono">
                Fiscalía General del Estado de Michoacán — DTI
              </p>
            </div>
            <span class="font-mono text-xs px-3 py-1 bg-cyan-500/10 border border-cyan-500/30 text-cyan-400 self-start md:self-center uppercase tracking-wider">
              Abril 2022 – En Curso
            </span>
          </div>
          <div class="mission-card p-6 bg-slate-950/40 border border-slate-800 rounded-xl backdrop-blur-sm relative">
            <p class="text-slate-300 font-mono text-sm leading-relaxed mb-4">
              Encargado del diseño, desarrollo y refactorización de arquitecturas web institucionales críticas, garantizando la optimización de procesos jurídicos y administrativos de la Fiscalía.
            </p>
            <ul class="space-y-2 font-mono text-xs text-slate-400 mb-4">
              <li class="flex items-start gap-2">
                <span class="text-cyan-400 font-bold">&gt;</span> Despliegue y mantenimiento de módulos avanzados en plataformas de producción.
              </li>
              <li class="flex items-start gap-2">
                <span class="text-cyan-400 font-bold">&gt;</span> Análisis técnico y adaptación de requerimientos operativos complejos a código escalable.
              </li>
            </ul>
            <div class="border-t border-slate-800/60 pt-4">
              <span class="text-[10px] text-slate-500 block uppercase mb-2 tracking-widest">// REWARDS_EQUIPPED:</span>
              <div class="flex flex-wrap gap-2 text-[10px] font-bold text-cyan-400">
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">LARAVEL</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">LIVEWIRE</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">ALPINE.JS</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">SQL SERVER</span>
                <span class="px-2 py-0.5 bg-slate-900 border border-slate-800 rounded">GIT</span>
              </div>
            </div>
          </div>
        </div>
        <div class="mb-6 relative pl-8 group" data-aos="fade-left" data-aos-delay="100">
          <div class="absolute -left-[7px] top-2 w-3 h-3 bg-slate-700 rounded-none rotate-45 group-hover:bg-fuchsia-500 transition-colors z-10"></div>
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-2 !mb-4">
            <div>
              <span class="text-[10px] font-mono text-slate-500 tracking-[0.2em] block uppercase mb-1">
                // MISSION_ACCOMPLISHED
              </span>
              <h3 class="text-2xl font-black text-slate-300 group-hover:text-white transition-colors uppercase tracking-wide">
                Operador de Bodega de Indicios y Evidencias
              </h3>
              <p class="text-sm text-slate-500 font-mono">
                Fiscalía General del Estado de Michoacán — Unidad Técnica de Preservación y Manejo de Evidencias (UTPYME)
              </p>
            </div>
            <span class="font-mono text-xs px-3 py-1 bg-slate-800 border border-slate-700 text-slate-400 self-start md:self-center uppercase tracking-wider">
              Oct 2017 – Mar 2022
            </span>
          </div>
          <div class="grid md:grid-cols-2 mission-card p-6 bg-slate-950/20 border border-slate-900 group-hover:border-slate-800 rounded-xl transition-all relative">
            <div>
              <h4>Actividades:</h4>
              <ul class="text-slate-400 font-mono text-sm leading-relaxed mb-4 list-disc !space-y-4">
                <li>Gestión y control de indicios y evidencias (EMP) conforme a protocolos de cadena de custodia.</li>
                <li>Recepción, verificación y registro de evidencias debidamente embaladas, selladas y etiquetadas, asegurando la integridad de la información.</li>
                <li>Custodia y resguardo de evidencias en espacios especializados, considerando condiciones específicas según su naturaleza (biológicos, armas, drogas y evidencia digital).</li>
                <li>Control y documentación de entradas y salidas de evidencias para garantizar la trazabilidad y autenticidad durante todo el proceso penal.</li>
                <li>Conservación a largo plazo de evidencias hasta su disposición final por autoridad competente.</li>
                <li>Atención y disponibilidad de evidencias para peritos, fiscales y autoridades judiciales.</li>
              </ul>
            </div>
            <div class="mt-4 p-4 border border-fuchsia-500/20 bg-fuchsia-950/10 rounded-lg relative overflow-hidden">
              <div class="absolute top-0 right-0 w-16 h-16 bg-fuchsia-500/5 rotate-45 translate-x-8 -translate-y-8 pointer-events-none"></div>
              <h4 class="text-xs font-bold text-fuchsia-400 font-mono uppercase tracking-[0.15em] mb-2 flex items-center gap-1.5">
                LOGRO DESBLOQUEADO
              </h4>
              <h5>Diseño y desarrollo de sistema web para la gestión de cadena de custodia y evidencias</h5>

              <div class="!space-y-4">
                <p class="text-xs text-slate-300 font-mono leading-relaxed">
                  A partir de la experiencia operativa en bodega de indicios y evidencias, diseñé y desarrollé una aplicación web orientada a digitalizar y optimizar el registro de la cadena de custodia y el seguimiento de evidencias, reduciendo errores operativos y mejorando la trazabilidad de la información.
                </p>
                <p>El sistema fue diseñado bajo un esquema de roles y responsabilidades, enfocado a dos perfiles principales:</p>
                <div>
                  <h5>Modulos del sistema</h5>

                  <ul class="list-decimal">
                    <li>
                      Registro de cadena de custodia

                      <div>Dirigido a Ministerios públicos, Peritos y Policías de investigación</div>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="border-t border-slate-900 pt-4 mt-4">
              <span class="text-[10px] text-slate-600 block uppercase mb-2 tracking-widest">// TECH_CRAFTED:</span>
              <div class="flex flex-wrap gap-2 text-[10px] font-bold text-fuchsia-400/80 group-hover:text-fuchsia-400 transition-colors">
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">PHP</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">LARAVEL</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">MYSQL</span>
                <span class="px-2 py-0.5 bg-slate-950 border border-slate-900 rounded">BOOTSTRAP</span>
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
  transition: transform 0.2s ease, border-color 0.2s ease;
}

.group:hover .mission-card {
  transform: translateY(-2px);
  background: rgba(15, 23, 42, 0.3);
}
</style>
