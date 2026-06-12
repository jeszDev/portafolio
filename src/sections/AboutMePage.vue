<template>
  <section class="w-full py-12 gamer-about relative overflow-hidden">
    <div class="flex justify-center !mb-12">
      <TitleSection title="ACERCA DE MÍ" data-aos="fade-up" />
    </div>

    <div class="flex justify-center gap-8 px-4">

      <div
        class="data-file-card p-6 rounded-xl border border-slate-800 bg-slate-950/40 backdrop-blur-md relative md:w-4xl"
        data-aos="fade-right"
      >
        <div class="absolute top-0 left-0 w-4 h-4 border-t-2 border-l-2 border-cyan-400"></div>
        <span class="text-[9px] font-mono text-cyan-400/40 block tracking-[0.2em] uppercase mb-4">
          // SUBJECT_DOSSIER: JESZDEV_INIT
        </span>

        <div class="text-slate-300 font-mono text-base !space-y-4 leading-relaxed text-justify">
          <p>
            <span class="text-cyan-400 font-bold">&gt;</span> Soy desarrollador web con enfoque en backend, especializado en <span class="text-white font-bold">Laravel</span> y en la construcción de sistemas administrativos y plataformas institucionales.
          </p>

          <p>
            <span class="text-cyan-400 font-bold">&gt;</span> He participado en el desarrollo de aplicaciones para la gestión de procesos, control de información y atención a usuarios, trabajando con bases de datos relacionales y flujos complejos de negocio.
          </p>

          <p>
            <span class="text-cyan-400 font-bold">&gt;</span> Mi objetivo es seguir creando soluciones robustas que resuelvan problemas reales y evolucionar sistemas existentes hacia arquitecturas modernas y de alta velocidad.
          </p>

          <div class="pt-4 flex justify-start">
            <a href="/cv.pdf" target="_blank" download="CV_Jesús.pdf" class="btn-cv-dossier cursor-pointer">
              <span class="text-cyan-400 font-bold">&gt;</span> [DESCARGAR_DOSSIER_CV.PDF]
            </a>
          </div>
        </div>
      </div>

      <!-- <div
        class="skills-card p-6 rounded-xl border border-slate-800 bg-slate-950/70 relative"
        data-aos="fade-left"
      >
        <div class="absolute top-0 right-0 w-4 h-4 border-t-2 border-r-2 border-fuchsia-500"></div>
        <span class="text-[9px] font-mono text-fuchsia-500/50 block tracking-[0.2em] uppercase mb-4">
          // LOADED_EQUIPMENT
        </span>

        <h3 class="text-white font-mono text-sm font-bold uppercase tracking-wider mb-4 flex items-center gap-2">
          <span class="w-2 h-2 bg-fuchsia-500 animate-pulse"></span>
          Tech Stack
        </h3>

        <div class="flex flex-wrap gap-2">
          <span class="skill-tag backend">Laravel</span>
          <span class="skill-tag backend">PHP</span>
          <span class="skill-tag database">SQL Server</span>
          <span class="skill-tag database">MySQL</span>
          <span class="skill-tag frontend">Livewire</span>
          <span class="skill-tag frontend">Alpine.js</span>
          <span class="skill-tag frontend">Vue.js</span>
          <span class="skill-tag frontend">JavaScript</span>
          <span class="skill-tag styles">Tailwind</span>
          <span class="skill-tag styles">Bootstrap</span>
        </div>
      </div> -->

    </div>
  </section>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap');

.gamer-about {
  font-family: 'JetBrains Mono', monospace;
}

/* Tarjeta de Expediente Principal */
.data-file-card {
  box-shadow: inset 0 0 20px rgba(34, 211, 238, 0.03), 0 10px 30px rgba(0,0,0,0.5);
  clip-path: polygon(0 0, 96% 0, 100% 6%, 100% 100%, 0 100%);
}

.btn-cv-dossier {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.6rem 1.2rem;
  border: 1px dashed rgba(34, 211, 238, 0.3);
  background: rgba(34, 211, 238, 0.05);
  color: #22d3ee;
  font-size: 0.85rem;
  font-weight: bold;
  letter-spacing: 1px;
  transition: all 0.2s ease;
  clip-path: polygon(0 0, 95% 0, 100% 25%, 100% 100%, 5% 100%, 0 75%);
}

.btn-cv-dossier:hover {
  border-color: #22d3ee;
  background: rgba(34, 211, 238, 0.15);
  box-shadow: 0 0 15px rgba(34, 211, 238, 0.3);
  transform: translateX(4px);
}

/* Tarjeta de Inventario de Habilidades */
.skills-card {
  box-shadow: inset 0 0 20px rgba(240, 46, 170, 0.03), 0 10px 30px rgba(0,0,0,0.5);
  clip-path: polygon(0 0, 100% 0, 100% 100%, 8% 100%, 0 92%);
}

/* Estilo Base para las Etiquetas Tecnológicas (Items del Inventario) */
.skill-tag {
  font-size: 11px;
  padding: 0.3rem 0.6rem;
  border-radius: 4px;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 1px;
  background: rgba(15, 23, 42, 0.6);
  border: 1px solid #334155;
  color: #94a3b8;
  transition: all 0.2s ease;
}

.skill-tag:hover {
  transform: translateY(-2px);
  color: #fff;
}

/* Colores Temáticos por Categoría (Raridades de Item) */
.skill-tag.backend {
  border-color: rgba(239, 68, 68, 0.4); /* Rojo Laravel */
  text-shadow: 0 0 5px rgba(239, 68, 68, 0.3);
}
.skill-tag.backend:hover {
  background: rgba(239, 68, 68, 0.2);
  box-shadow: 0 0 10px rgba(239, 68, 68, 0.3);
}

.skill-tag.frontend {
  border-color: rgba(34, 211, 238, 0.4); /* Cian Frontend */
  text-shadow: 0 0 5px rgba(34, 211, 238, 0.3);
}
.skill-tag.frontend:hover {
  background: rgba(34, 211, 238, 0.2);
  box-shadow: 0 0 10px rgba(34, 211, 238, 0.3);
}

.skill-tag.database {
  border-color: rgba(234, 179, 8, 0.4); /* Amarillo base de datos */
  text-shadow: 0 0 5px rgba(234, 179, 8, 0.3);
}
.skill-tag.database:hover {
  background: rgba(234, 179, 8, 0.2);
  box-shadow: 0 0 10px rgba(234, 179, 8, 0.3);
}

.skill-tag.styles {
  border-color: rgba(168, 85, 247, 0.4); /* Morado Tailwind/Bootstrap */
  text-shadow: 0 0 5px rgba(168, 85, 247, 0.3);
}
.skill-tag.styles:hover {
  background: rgba(168, 85, 247, 0.2);
  box-shadow: 0 0 10px rgba(168, 85, 247, 0.3);
}
</style>
