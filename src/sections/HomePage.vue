<script setup lang="ts">
import LogoTitle from '@/components/LogoTitle.vue';
import DeveloperTerminal from '@/components/DeveloperTerminal.vue';
const scrollToProjects = () => {
  const el = document.getElementById('section3');
  el?.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <div class="w-full gamer-mode py-[5rem] md:py-[6rem] md:px-[4rem]">
    <!-- <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-10 items-center relative"> -->
    <div class="grid gap-8 md:grid-cols-2 px-4 md:px-12">
      <div class="relative">
        <div
          class="absolute -top-16 md:-left-16 opacity-40 select-none pointer-events-none text-xs font-mono uppercase tracking-[0.5em]"
        >
          System.initialize(jeszDev)... <br />
          Loading_Assets... [OK] <br />
          Framework: Vue_3.x
        </div>
        <div class="" data-aos="fade-right">
          <div class="relative inline-block !mb-12">
            <h1 class="text-4xl md:text-6xl font-black italic tracking-tighter leading-none">
              Hola, soy
              <!-- <br /> -->
              <span class="text-glitch" data-text="jeszDev">
                <!-- <LogoTitle /> -->
                jeszDev
              </span>
            </h1>
            <div class="h-1 w-24 bg-cyan-400 mt-4 shadow-[0_0_15px_rgba(34,211,238,0.8)]"></div>
          </div>
          <div class="flex flex-wrap gap-6">
            <button @click="scrollToProjects" class="btn-gamer btn-cyan cursor-pointer">
              <span class="btn-glitch-content">_VER_PROYECTOS</span>
              <span class="btn-tag">R1</span>
            </button>
            <a
              href="/cv.pdf"
              target="_blank"
              download=";eszDev_cv.pdf"
              class="btn-gamer btn-fuchsia cursor-pointer flex items-center"
            >
              <span class="btn-glitch-content">_DESCARGAR_CV</span>
              <span class="btn-tag">X</span>
            </a>
            <!-- <button @click="$emit('scrollToContact')" class="btn-gamer btn-outline cursor-pointer">
                <span class="btn-glitch-content">_CONTACTO</span>
                <span class="btn-tag">L1</span>
              </button> -->
          </div>
        </div>
      </div>
      <div class="" data-aos="zoom-in-left">
        <!-- <div
            class="opacity-90 group-hover:opacity-40 transition-opacity"
          ></div> -->
        <DeveloperTerminal />
      </div>
    </div>
    <!-- </div> -->
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

.btn-fuchsia {
  background: rgba(217, 70, 239, 0.2);
  border: 1px solid #d946ef;
  color: #f5d0fe;
}

.btn-fuchsia:hover {
  background: #d946ef;
  color: #000;
  box-shadow: 0 0 20px rgba(217, 70, 239, 0.6);
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

.bg-grid-pattern {
  background-image: radial-gradient(circle, #22d3ee 1px, transparent 1px);
  background-size: 30px 30px;
}

.gamer-mode h1 {
  font-family: 'Syne', sans-serif;
  letter-spacing: 2px; /* Mejor usar tracking-wide o normal aquí */
}
</style>
