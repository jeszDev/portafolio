<script setup lang="ts">
import DeveloperTerminal from '@/components/DeveloperTerminal.vue';
const scrollToProjects = () => {
  const el = document.getElementById('section3')
  el?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <div class="w-full">
    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-10 items-center">

      <!-- TEXT -->
      <div class="space-y-6" data-aos="fade-up" data-aos-duration="400">
        <div>
          <p class="text-sm text-emerald-400 tracking-widest uppercase">
            Frontend Developer
          </p>
          <h1 class="text-5xl md:text-6xl font-bold leading-tight" data-aos="fade-up" data-aos-delay="300" data-aos-duration="500">
            Hola, soy
            <span class="gradient-text">JeszDev</span>
          </h1>
          <p class="text-white/70 text-lg leading-relaxed" data-aos="fade-right" data-aos-delay="1000" data-aos-duration="800">
            Construyo interfaces modernas, rápidas y con experiencia de usuario que realmente se siente.
          </p>
        </div>

        <!-- BUTTONS -->
        <div class="flex gap-4 mt-5 mb-5">
          <button
            @click="scrollToProjects"
            class="btn-primary cursor-pointer"
            data-aos="fade-up" data-aos-delay="400"
          >
            Ver proyectos
          </button>

          <button
            @click="$emit('scrollToContact')"
            class="btn-secondary cursor-pointer"
            data-aos="fade-up" data-aos-delay="500"
          >
            Contacto
          </button>
        </div>
      </div>

      <!-- VISUAL -->
      <!-- <div class="termina-wrapper">
        <DeveloperTerminal />
      </div> -->

      <div class="relative flex justify-center items-center"  data-aos="zoom-in" data-aos-delay="1300" data-aos-duration="1100">
        <div class="glow-bg"></div>

        <DeveloperTerminal />
      </div>

    </div>
  </div>
</template>

<style scoped>
.gradient-text {
  background: linear-gradient(90deg, #34d399, #22d3ee);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.btn-primary {
  background: #10b981;
  padding: 10px 20px;
  border-radius: 10px;
  font-weight: 500;
  transition: 0.3s;
}

.btn-primary:hover {
  background: #059669;
  transform: translateY(-2px);
}

.btn-secondary {
  border: 1px solid rgba(255,255,255,0.2);
  padding: 10px 20px;
  border-radius: 10px;
  transition: 0.3s;
}

.btn-secondary:hover {
  border-color: white;
  transform: translateY(-2px);
}

/* TERMINAL STYLE */
.terminal {
  background: #020617;
  border: 1px solid rgba(255,255,255,0.1);
  padding: 20px;
  border-radius: 12px;
  width: 300px;
  font-family: monospace;
  box-shadow: 0 0 40px rgba(16,185,129,0.2);
}

.terminal-wrapper {
  opacity: 0;
  transform: translateY(40px) scale(0.95);
  animation: terminalEnter 0.8s ease forwards;
  animation-delay: 0.4s;
}

@keyframes terminalEnter {
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.glow-bg {
  position: absolute;
  width: 300px;
  height: 300px;
  background: radial-gradient(circle, rgba(16,185,129,0.25), transparent);
  filter: blur(80px);
  z-index: -1;
}
</style>
