<script setup lang="ts">
import LogoTitle from '@/components/LogoTitle.vue';
import DeveloperTerminal from '@/components/DeveloperTerminal.vue';
const scrollToProjects = () => {
  const el = document.getElementById('section3');
  el?.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <div class="w-full gamer-mode py-12">
    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-10 items-center relative">
      <div
        class="absolute -top-10 -left-10 opacity-10 select-none pointer-events-none text-xs font-mono uppercase tracking-[0.5em]"
      >
        System.initialize(jeszDev)... <br />
        Loading_Assets... [OK] <br />
        Framework: Vue_3.x
      </div>

      <div class="z-10 ps-5" data-aos="fade-right">
        <div class="relative inline-block !mb-12">
          <!-- <p
            class="text-xs text-cyan-400 tracking-[0.3em] uppercase font-black mb-2 flex items-center gap-2"
          >
            <span class="w-2 h-2 bg-cyan-400 animate-pulse"></span>
            Lvl. 99 Frontend Architect
          </p> -->

          <h1
            class="text-4xl md:text-6xl font-black italic tracking-tighter leading-none"
          >
            Hola, soy <!-- <br /> -->
            <span class="text-glitch" data-text="jeszDev">
              <!-- <LogoTitle /> -->
              jeszDev
            </span>
          </h1>

          <div class="h-1 w-24 bg-cyan-400 mt-4 shadow-[0_0_15px_rgba(34,211,238,0.8)]"></div>
        </div>

        <!-- <p class="text-slate-400 text-lg font-mono border-l-2 border-slate-700 pl-4 max-w-md">
          // Construyo interfaces de alta velocidad y
          <span class="text-white">experiencias inmersivas</span> que dominan el DOM.
        </p> -->

        <div class="flex flex-wrap gap-6">
          <button @click="scrollToProjects" class="btn-gamer btn-cyan cursor-pointer">
            <span class="btn-glitch-content">_VER_PROYECTOS</span>
            <span class="btn-tag">R1</span>
          </button>

          <button @click="$emit('scrollToContact')" class="btn-gamer btn-outline cursor-pointer">
            <span class="btn-glitch-content">_CONTACTO</span>
            <span class="btn-tag">L1</span>
          </button>
        </div>
      </div>

      <div class="relative group" data-aos="zoom-in-left">
        <div
          class="absolute -inset-4 bg-grid-pattern opacity-20 group-hover:opacity-40 transition-opacity"
        ></div>

        <!-- <div
          class="relative z-10 border-2 border-cyan-500/30 bg-slate-900/80 backdrop-blur-xl p-1 shadow-[0_0_50px_rgba(6,182,212,0.15)]"
        >
          <div
            class="flex justify-between items-center bg-cyan-500/10 p-2 border-b border-cyan-500/30"
          >
            <span class="text-[10px] text-cyan-400 font-mono font-bold">NODE_TERMINAL v2.0</span>
            <div class="flex gap-1">
              <div class="w-2 h-2 rounded-full bg-red-500/50"></div>
              <div class="w-2 h-2 rounded-full bg-yellow-500/50"></div>
              <div class="w-2 h-2 rounded-full bg-green-500/50"></div>
            </div>
          </div> -->
          <DeveloperTerminal />
        <!-- </div> -->

        <div class="scanline"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>


.gamer-mode {
  font-family: 'Space Grotesk', sans-serif;
  color: #fff;
  background: radial-gradient(circle at 10% 20%, rgba(15, 23, 42, 1) 0%, rgba(2, 6, 23, 1) 90%);
}

/* EFECTO GLITCH PARA EL NOMBRE */
.text-glitch {
  position: relative;
  color: #fff;
  text-shadow:
    0.05em 0 0 #00fffc,
    -0.03em -0.04em 0 #fc00ff,
    0.025em 0.04em 0 #fffc00;
  animation: glitch 725ms infinite;
}

/* BOTONES GAMER */
.btn-gamer {
  position: relative;
  padding: 1rem 2rem;
  font-family: 'JetBrains Mono', monospace;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 2px;
  transition: all 0.2s;
  overflow: hidden;
  clip-path: polygon(10% 0, 100% 0, 100% 70%, 90% 100%, 0 100%, 0 30%);
}

.btn-cyan {
  background: #22d3ee;
  color: #000;
}

.btn-cyan:hover {
  background: #fff;
  box-shadow: 0 0 20px rgba(34, 211, 238, 0.6);
  transform: skewX(-5deg);
}

.btn-outline {
  background: transparent;
  border: 1px solid #334155;
  color: #94a3b8;
}

.btn-outline:hover {
  border-color: #22d3ee;
  color: #fff;
}

/* ETIQUETAS DE CONTROL (R1/L1) */
.btn-tag {
  position: absolute;
  top: 2px;
  right: 5px;
  font-size: 8px;
  opacity: 0.5;
}

/* ANIMACIONES */
@keyframes glitch {
  0% {
    text-shadow:
      0.05em 0 0 #00fffc,
      -0.03em -0.04em 0 #fc00ff,
      0.025em 0.04em 0 #fffc00;
  }
  15% {
    text-shadow:
      0.05em 0 0 #00fffc,
      -0.03em -0.04em 0 #fc00ff,
      0.025em 0.04em 0 #fffc00;
  }
  16% {
    text-shadow:
      -0.05em -0.025em 0 #00fffc,
      0.025em 0.025em 0 #fc00ff,
      -0.05em -0.05em 0 #fffc00;
  }
  /* ... más pasos ... */
  100% {
    text-shadow:
      -0.025em 0 0 #00fffc,
      -0.025em -0.025em 0 #fc00ff,
      -0.025em -0.05em 0 #fffc00;
  }
}

.scanline {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    to bottom,
    transparent 50%,
    rgba(0, 255, 255, 0.05) 51%,
    transparent 51%
  );
  background-size: 100% 4px;
  pointer-events: none;
  z-index: 20;
}

.bg-grid-pattern {
  background-image: radial-gradient(circle, #22d3ee 1px, transparent 1px);
  background-size: 30px 30px;
}

.gamer-mode h1 {
  font-family: 'Syne', sans-serif;
  letter-spacing: 2px; /* Mejor usar tracking-wide o normal aquí */
}
</style>
