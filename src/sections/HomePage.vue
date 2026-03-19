<script setup lang="ts">
const scrollToProjects = () => {
  const el = document.getElementById('section3')
  el?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <div class="w-full">
    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-10 items-center">

      <!-- TEXT -->
      <div class="space-y-6">
        <p class="text-sm text-emerald-400 tracking-widest uppercase">
          Frontend Developer
        </p>

        <h1 class="text-5xl md:text-6xl font-bold leading-tight">
          Hola, soy
          <span class="gradient-text">JeszDev</span>
        </h1>

        <p class="text-white/70 text-lg leading-relaxed">
          Construyo interfaces modernas, rápidas y con experiencia de usuario que realmente se siente.
        </p>

        <!-- BUTTONS -->
        <div class="flex gap-4">
          <button
            @click="scrollToProjects"
            class="btn-primary"
          >
            Ver proyectos
          </button>

          <button
            @click="$emit('scrollToContact')"
            class="btn-secondary"
          >
            Contacto
          </button>
        </div>
      </div>

      <!-- VISUAL -->
      <div class="relative flex justify-center items-center">

        <!-- Glow -->
        <div class="absolute w-72 h-72 bg-emerald-500/20 blur-3xl rounded-full"></div>

        <!-- Card -->
        <div class="terminal">
          <p><span class="text-emerald-400">$</span> npm run dev</p>
          <p class="text-white/70">Iniciando proyecto...</p>
          <p class="text-white/70">✔ Compilado correctamente</p>
          <p class="text-emerald-400">Servidor listo 🚀</p>
        </div>
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
</style>
