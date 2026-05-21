<template>
  <div class="flex bg-neutral-950 text-white">
    <!-- SIDEBAR -->
    <aside
      class="w-64 h-screen hidden md:flex md:flex-col fixed justify-between p-6 border-r border-white/10 bg-neutral-950 text-white"
    >
      <!-- Logo -->
      <div class="flex flex-col items-center gap-4">
        <!-- <img src="@/assets/logo.svg" class="w-20 opacity-80" /> -->
        <!-- <h1 class="text-lg font-bold tracking-wide">JeszDev</h1> -->
        <LogoTitle />
      </div>

      <!-- NAV -->
      <nav class="flex flex-col gap-4 p-4 border border-slate-800 bg-slate-950/60 backdrop-blur-md rounded-xl max-w-xs shadow-[0_0_20px_rgba(0,0,0,0.8)]">

    <div class="text-[10px] font-mono text-cyan-500/60 tracking-[0.3em] uppercase px-3 mb-2 select-none">
      :: SELECT_STAGE
    </div>

    <button @click="scrollToSection('section1')" class="nav-gamer-item group">
      <div class="nav-gamer-bg"></div>
      <div class="flex items-center gap-3 relative z-10">
        <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
          <HomeIcon />
        </span>
        <span class="font-mono text-sm tracking-wider uppercase text-slate-300 group-hover:text-white transition-colors">
          Inicio
        </span>
      </div>
      <span class="nav-gamer-tag">01</span>
    </button>

    <button @click="scrollToSection('section2')" class="nav-gamer-item group">
      <div class="nav-gamer-bg"></div>
      <div class="flex items-center gap-3 relative z-10">
        <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
          <AboutIcon />
        </span>
        <span class="font-mono text-sm tracking-wider uppercase text-slate-300 group-hover:text-white transition-colors">
          Acerca de mí
        </span>
      </div>
      <span class="nav-gamer-tag">02</span>
    </button>

    <button @click="scrollToSection('section3')" class="nav-gamer-item group">
      <div class="nav-gamer-bg"></div>
      <div class="flex items-center gap-3 relative z-10">
        <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
          <AboutIcon />
        </span>
        <span class="font-mono text-sm tracking-wider uppercase text-slate-300 group-hover:text-white transition-colors">
          Experiencia
        </span>
      </div>
      <span class="nav-gamer-tag">02</span>
    </button>

    <button @click="scrollToSection('section4')" class="nav-gamer-item group">
      <div class="nav-gamer-bg"></div>
      <div class="flex items-center gap-3 relative z-10">
        <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
          <ProjectsIcon />
        </span>
        <span class="font-mono text-sm tracking-wider uppercase text-slate-300 group-hover:text-white transition-colors">
          Proyectos
        </span>
      </div>
      <span class="nav-gamer-tag">03</span>
    </button>

    <button @click="scrollToSection('section5')" class="nav-gamer-item group">
      <div class="nav-gamer-bg"></div>
      <div class="flex items-center gap-3 relative z-10">
        <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
          <ContactIcon />
        </span>
        <span class="font-mono text-sm tracking-wider uppercase text-slate-300 group-hover:text-white transition-colors">
          Contacto
        </span>
      </div>
      <span class="nav-gamer-tag">04</span>
    </button>

  </nav>

      <!-- Footer -->
      <div class="text-xs text-white/40 text-center">© 2026</div>
    </aside>

    <!-- CONTENT -->
    <main
      ref="contentContainer"
      id="scroll-container"
      class="w-full h-screen scroll-smooth md:!ml-64 !bg-neutral-950 text-white"
    >
      <section id="section0" class="section" :ref="(el) => setSectionRef(el, 'section1')">
        <HomePage />
      </section>

      <section id="section1" class="section" :ref="(el) => setSectionRef(el, 'section2')">
        <AboutMePage />
      </section>

      <section id="section1" class="section" :ref="(el) => setSectionRef(el, 'section3')">
        <ExperiencePage />
      </section>

      <!-- <section id="section2" class="section" :ref="(el) => setSectionRef(el, 'section4')">
        <AboutPage />
      </section> -->

      <section id="section3" class="section" :ref="(el) => setSectionRef(el, 'section4')">
        <ProjectsPage />
      </section>

      <section id="section4" class="section" :ref="(el) => setSectionRef(el, 'section5')">
        <ContactPage />
      </section>
    </main>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount, watch } from 'vue';

import LogoTitle from '@/components/LogoTitle.vue';

import HomePage from './sections/HomePage.vue';
import AboutMePage from './sections/AboutMePage.vue';
import ExperiencePage from './sections/ExperiencePage.vue';
import AboutPage from './sections/AboutPage.vue';
import ProjectsPage from './sections/ProjectsPage.vue';
import ContactPage from './sections/ContactPage.vue';

import HomeIcon from './icons/HomeIcon.vue';
import AboutIcon from './icons/AboutIcon.vue';
import ProjectsIcon from './icons/ProjectsIcon.vue';
import ContactIcon from './icons/ContactIcon.vue';
import AOS from 'aos';

interface SectionRefs {
  [key: string]: HTMLElement | null;
}

const contentContainer = ref<HTMLElement | null>(null);
const sectionRefs = ref<SectionRefs>({});
const activeSection = ref('section1');

const setSectionRef = (el: HTMLElement | null, id: string) => {
  sectionRefs.value[id] = el;
};

const scrollToSection = (id: string) => {
  const section = sectionRefs.value[id];
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
    activeSection.value = id;
  }
};

const handleScroll = () => {
  if (!contentContainer.value) return;

  const scrollPosition = contentContainer.value.scrollTop + window.innerHeight / 2;

  for (const [id, section] of Object.entries(sectionRefs.value)) {
    if (!section) continue;

    const top = section.offsetTop;
    const bottom = top + section.offsetHeight;

    if (scrollPosition >= top && scrollPosition <= bottom) {
      activeSection.value = id;
      break;
    }
  }
};

let timeout: ReturnType<typeof setTimeout>;

const onScroll = () => {
  clearTimeout(timeout);
  timeout = setTimeout(handleScroll, 50);
};

onMounted(() => {
  contentContainer.value?.addEventListener('scroll', onScroll);
  handleScroll();
});

onBeforeUnmount(() => {
  contentContainer.value?.removeEventListener('scroll', onScroll);
});
</script>

<style scoped>
.section {
  background-color: black;
  @apply min-h-[100vh] p-[4rem] flex items-center;
}

/* NAV ITEM PRO */
.nav-item {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.6);
  transition: all 0.3s ease;
  cursor: pointer;
}

.nav-item:hover {
  color: white;
  transform: translateX(5px);
}

@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap');

/* Base del botón con estilo de celda de interfaz de juego */
.nav-gamer-item {
  position: relative;
  display: flex;
  align-items: center;
  justify-between;
  padding: 0.75rem 1rem;
  width: 100%;
  font-family: 'JetBrains Mono', monospace;
  background: rgba(15, 23, 42, 0.4);
  border-left: 3px solid #334155; /* Borde izquierdo inactivo */
  clip-path: polygon(0 0, 92% 0, 100% 25%, 100% 100%, 8% 100%, 0 75%);
  transition: all 0.2s ease-in-out;
  cursor: pointer;
}

/* Fondo animado tecnológico en el hover */
.nav-gamer-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, rgba(34, 211, 238, 0.15) 0%, transparent 100%);
  opacity: 0;
  transform: translateX(-10px);
  transition: all 0.25s ease;
  z-index: 1;
}

/* Comportamiento Hover general del botón */
.nav-gamer-item:hover {
  border-left-color: #22d3ee; /* Cambia al cian neón */
  transform: translateX(4px); /* Pequeño desplazamiento hacia adelante */
  box-shadow: -5px 0 15px rgba(34, 211, 238, 0.2);
}

.nav-gamer-item:hover .nav-gamer-bg {
  opacity: 1;
  transform: translateX(0);
}

/* Efecto de parpadeo leve en los íconos al pasar el cursor */
.icon-container {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s ease;
}

.nav-gamer-item:hover .icon-container {
  transform: scale(1.1);
  filter: drop-shadow(0 0 5px rgba(34, 211, 238, 0.6));
}

/* Pequeñas etiquetas numéricas (Estilo índice de inventario) */
.nav-gamer-tag {
  position: relative;
  z-index: 10;
  font-size: 10px;
  color: #64748b;
  margin-left: auto; /* Lo empuja totalmente a la derecha */
  transition: color 0.2s ease;
}

.nav-gamer-item:hover .nav-gamer-tag {
  color: #22d3ee;
  text-shadow: 0 0 4px rgba(34, 211, 238, 0.5);
}


</style>
