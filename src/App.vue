<template>
  <div class="flex bg-neutral-950 text-white">
    <!-- SIDEBAR -->

    <div
      class="md:hidden fixed top-0 left-0 right-0 h-16 bg-neutral-950/80 backdrop-blur-md border-b border-white/10 z-50 flex items-center justify-between px-6"
    >
      <LogoTitle />

      <button
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="text-cyan-400 hover:text-cyan-300 focus:outline-none z-50 p-2 transition-colors"
      >
        <svg
          v-if="!isMobileMenuOpen"
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          />
        </svg>
        <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
    </div>

    <div
      v-if="isMobileMenuOpen"
      class="md:hidden fixed inset-0 bg-neutral-950/95 backdrop-blur-lg z-40 flex flex-col justify-center items-center p-6"
    >
      <nav
        class="flex flex-col gap-4 w-full max-w-xs border border-slate-800 bg-slate-950/60 p-4 rounded-xl shadow-[0_0_30px_rgba(34,211,238,0.15)]"
      >
        <div
          class="text-[10px] font-mono text-cyan-500/60 tracking-[0.3em] uppercase px-3 mb-2 select-none"
        >
          :: SELECT_STAGE
        </div>

        <button
          v-for="item in menuItems"
          :key="item.id"
          @click="scrollToSection(item.id)"
          class="nav-gamer-item group cursor-pointer"
          :class="{ active: activeSection === item.id }"
        >
          <div class="nav-gamer-bg"></div>
          <div class="flex items-center gap-3 relative z-10">
            <span class="icon-container text-cyan-400">
              <component :is="item.icon" />
            </span>
            <span
              class="font-mono text-sm tracking-wider uppercase transition-colors"
              :class="activeSection === item.id ? 'text-white' : 'text-slate-300'"
            >
              {{ item.label }}
            </span>
          </div>
          <span class="nav-gamer-tag">{{ item.tag }}</span>
        </button>
      </nav>
    </div>

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
      <nav
        class="flex flex-col gap-4 p-4 border border-slate-800 bg-slate-950/60 backdrop-blur-md rounded-xl max-w-xs shadow-[0_0_20px_rgba(0,0,0,0.8)]"
      >
        <div
          class="text-[10px] font-mono text-cyan-500/60 tracking-[0.3em] uppercase px-3 mb-2 select-none"
        >
          :: SELECT_STAGE
        </div>

        <button
          v-for="item in menuItems"
          :key="item.id"
          @click="scrollToSection(item.id)"
          class="nav-gamer-item group cursor-pointer"
          :class="{ active: activeSection === item.id }"
        >
          <div class="nav-gamer-bg"></div>
          <div class="flex items-center gap-3 relative z-10">
            <span class="icon-container text-cyan-400 group-hover:text-cyan-300">
              <component :is="item.icon" />
            </span>
            <span
              class="font-mono text-sm tracking-wider uppercase transition-colors"
              :class="
                activeSection === item.id ? 'text-white' : 'text-slate-300 group-hover:text-white'
              "
            >
              {{ item.label }}
            </span>
          </div>
          <span class="nav-gamer-tag">{{ item.tag }}</span>
        </button>
      </nav>

      <footer class="mt-auto pt-6">
        <div
          class="flex items-center justify-center gap-2 font-mono text-[10px] text-slate-400 select-none"
        >
          <span
            class="w-1.5 h-1.5 rounded-full bg-cyan-500 shadow-[0_0_8px_rgba(34,211,238,0.8)] animate-pulse"
          ></span>
          <span class="tracking-wider">© 2026 // SYSTEM_ACTIVE</span>
        </div>
      </footer>
    </aside>

    <!-- CONTENT -->
    <main
      ref="contentContainer"
      id="scroll-container"
      class="w-full h-screen scroll-smooth ml-0 md:!ml-64 !bg-neutral-950 text-white pt-16 md:pt-0"
    >
      <section id="section1" class="min-h-[100vh]" :ref="(el) => setSectionRef(el, 'section1')">
        <HomePage />
      </section>

      <!-- <section
        id="section2"
        class="min-h-[100vh] md:p-[4rem]"
        :ref="(el) => setSectionRef(el, 'section2')"
      >
        <AboutMePage />
      </section> -->

      <!-- <section
        id="section3"
        class="min-h-[100vh] md:p-[4rem]"
        :ref="(el) => setSectionRef(el, 'section3')"
      >
        <ExperiencePage />
      </section> -->

      <!-- <section id="section2" class="min-h-[100vh] md:p-[4rem]" :ref="(el) => setSectionRef(el, 'section4')">
        <AboutPage />
      </section> -->

      <!-- <section
        id="section4"
        class="min-h-[100vh] md:p-[4rem]"
        :ref="(el) => setSectionRef(el, 'section4')"
      >
        <ProjectsPage />
      </section> -->

      <!-- <section
        id="section5"
        class="min-h-[100vh] md:p-[4rem]"
        :ref="(el) => setSectionRef(el, 'section5')"
      >
        <EducationPage />
      </section> -->

      <!-- <section
        id="section6"
        class="min-h-[100vh] md:p-[4rem]"
        :ref="(el) => setSectionRef(el, 'section6')"
      >
        <ContactPage />
      </section> -->
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
import EducationPage from './sections/EducationPage.vue';
import ContactPage from './sections/ContactPage.vue';

import HomeIcon from './icons/HomeIcon.vue';
import AboutIcon from './icons/AboutIcon.vue';
import ExperienceIcon from './icons/ExperienceIcon.vue';
import ProjectsIcon from './icons/ProjectsIcon.vue';
import EducationIcon from './icons/EducationIcon.vue';
import ContactIcon from './icons/ContactIcon.vue';
import AOS from 'aos';

interface SectionRefs {
  [key: string]: HTMLElement | null;
}

const isMobileMenuOpen = ref(false);

const contentContainer = ref<HTMLElement | null>(null);
const sectionRefs = ref<SectionRefs>({});
const activeSection = ref('section1');

const menuItems = [
  { id: 'section1', label: 'Inicio', tag: '01', icon: HomeIcon },
  { id: 'section2', label: 'Acerca de mí', tag: '02', icon: AboutIcon },
  { id: 'section3', label: 'Experiencia', tag: '03', icon: ExperienceIcon },
  { id: 'section4', label: 'Proyectos', tag: '04', icon: ProjectsIcon },
  { id: 'section5', label: 'Educación', tag: '05', icon: EducationIcon },
  { id: 'section6', label: 'Contacto', tag: '06', icon: ContactIcon },
];

const setSectionRef = (el: any, id: string) => {
  sectionRefs.value[id] = el as HTMLElement | null;
};

const scrollToSection = (id: string) => {
  const section = sectionRefs.value[id];
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
    activeSection.value = id;
    isMobileMenuOpen.value = false;
  }
};

const handleScroll = () => {
  const viewportCenter = window.innerHeight / 2;

  for (const [id, section] of Object.entries(sectionRefs.value)) {
    if (!section) continue;

    const rect = section.getBoundingClientRect();

    // Si el centro de la pantalla está dentro de los límites de esta sección
    if (rect.top <= viewportCenter && rect.bottom >= viewportCenter) {
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
  window.addEventListener('scroll', onScroll);
  handleScroll();
});

onBeforeUnmount(() => {
  contentContainer.value?.removeEventListener('scroll', onScroll);
  window.removeEventListener('scroll', onScroll);
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

/* Estado activo del botón */
.nav-gamer-item.active {
  border-left-color: #22d3ee;
  transform: translateX(4px);
  background: rgba(34, 211, 238, 0.05);
  box-shadow: -5px 0 15px rgba(34, 211, 238, 0.2);
}

.nav-gamer-item.active .nav-gamer-bg {
  opacity: 1;
  transform: translateX(0);
}

.nav-gamer-item.active .icon-container {
  transform: scale(1.1);
  filter: drop-shadow(0 0 5px rgba(34, 211, 238, 0.6));
}

.nav-gamer-item.active .nav-gamer-tag {
  color: #22d3ee;
  text-shadow: 0 0 4px rgba(34, 211, 238, 0.5);
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
