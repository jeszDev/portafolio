<script setup lang="ts">
import HomePage from './pages/HomePage.vue';
import AboutPage from './pages/AboutPage.vue';
import ProjectsPage from './pages/ProjectsPage.vue';
import ContactPage from './pages/ContactPage.vue';

import HomeIcon from './icons/HomeIcon.vue';
import AboutIcon from './icons/AboutIcon.vue';
import ProjectsIcon from './icons/ProjectsIcon.vue';
import ContactIcon from './icons/ContactIcon.vue';

import { ref, onMounted, onBeforeUnmount } from 'vue';

// Tipos
interface MenuItem {
  id: string;
  title: string;
}

interface SectionRefs {
  [key: string]: HTMLElement | null;
}

// Datos del menú
const menuItems: MenuItem[] = [
  { id: 'section1', title: 'Sección 1' },
  { id: 'section2', title: 'Sección 2' },
  { id: 'section3', title: 'Sección 3' },
  { id: 'section4', title: 'Sección 4' },
  { id: 'section5', title: 'Sección 5' },
];

// Refs
const contentContainer = ref<HTMLElement | null>(null);
const sectionRefs = ref<SectionRefs>({});
const activeSection = ref<string>(menuItems[0].id);

// Configurar las refs de las secciones
const setSectionRef = (el: HTMLElement | null, id: string): void => {
  console.log('llega');

  sectionRefs.value[id] = el;
};

// Obtener clase CSS para la sección (alternar colores)
const getSectionClass = (id: string): string => {
  const index = menuItems.findIndex((item) => item.id === id);
  return index % 2 === 0 ? 'bg-gray-50' : 'bg-white';
};

// Función para hacer scroll a una sección
const scrollToSection = (sectionId: string): void => {
  const section = sectionRefs.value[sectionId];
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
    activeSection.value = sectionId;
  }
};

// Manejar el scroll para detectar la sección activa
const handleScroll = (): void => {
  if (!contentContainer.value) return;

  const scrollPosition = contentContainer.value.scrollTop + window.innerHeight / 2;

  for (const [id, section] of Object.entries(sectionRefs.value)) {
    if (!section) continue;

    const sectionTop = section.offsetTop;
    const sectionBottom = sectionTop + section.offsetHeight;

    if (scrollPosition >= sectionTop && scrollPosition <= sectionBottom) {
      activeSection.value = id;
      break;
    }
  }
};

// Debounce para mejorar rendimiento del scroll
let scrollTimeout: ReturnType<typeof setTimeout>;
const debouncedHandleScroll = (): void => {
  clearTimeout(scrollTimeout);
  scrollTimeout = setTimeout(handleScroll, 100);
};

// Configurar listeners al montar el componente
onMounted(() => {
  if (contentContainer.value) {
    contentContainer.value.addEventListener('scroll', debouncedHandleScroll);
    // Detectar sección activa inicial
    handleScroll();
  }
});

// Limpiar listeners al desmontar
onBeforeUnmount(() => {
  if (contentContainer.value) {
    contentContainer.value.removeEventListener('scroll', debouncedHandleScroll);
  }
  clearTimeout(scrollTimeout);
});
</script>

<template>
  <div class="grid grid-cols-[20%_80%] gap-4 h-screen bg-black">
    <div class="flex items-center justify-around">
      <div>
        <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
      </div>

      <div>
        <nav class="w-64">
          <div class="flex flex-col space-y-1">
            <div
              class="px-4 py-3 text-white hover:text-[hsla(160,100%,37%,1)] flex items-center text-2xl hover:cursor-pointer"
              @click="scrollToSection('section1')"
            >
              <span class="px-4"><HomeIcon /></span>
              Inicio
            </div>
            <div
              class="px-4 py-3 text-white hover:text-[hsla(160,100%,37%,1)] flex items-center text-2xl"
            >
              <span class="px-4"><AboutIcon /></span>
              Sobre mí
            </div>
            <div
              class="px-4 py-3 text-white hover:text-[hsla(160,100%,37%,1)] flex items-center text-2xl"
            >
              <span class="px-4"><ProjectsIcon /></span>
              Proyectos
            </div>
            <div
              class="px-4 py-3 text-white hover:text-[hsla(160,100%,37%,1)] flex items-center text-2xl"
            >
              <span class="px-4"><ContactIcon /></span>
              Contacto
            </div>
          </div>
        </nav>
      </div>
    </div>

    <div class="">
      <!-- <RouterView /> -->

      <div class="flex-1 ml-64 h-screen overflow-y-auto scroll-smooth" id="content-column">
        <section
          id="section1"
          class="min-h-screen p-10 grid grid-rows-[10%_90%] gap-4 scroll-snap-section"
          ref="setSectionRef(el, 'section1')"
        >
          <HomePage />
        </section>
        <section
          id="section2"
          class="min-h-screen p-10 grid grid-rows-[10%_90%] gap-4 scroll-snap-section"
        >
          <AboutPage />
        </section>
        <section
          id="section3"
          class="min-h-screen p-10 grid grid-rows-[10%_90%] gap-4 scroll-snap-section"
        >
          <ProjectsPage />
        </section>
        <section
          id="section3"
          class="min-h-screen p-10 grid grid-rows-[10%_90%] gap-4 scroll-snap-section"
        >
          <ContactPage />
        </section>
        <!-- <section
          id="section4"
          class="min-h-screen p-10 flex flex-col justify-center bg-white scroll-snap-section"
        >
          <h1 class="text-3xl font-bold mb-4">Contenido de la Sección 4</h1>
          <p class="text-lg">Más contenido con altura de pantalla completa.</p>
        </section> -->
        <!-- <section
          id="section5"
          class="min-h-screen p-10 flex flex-col justify-center bg-gray-50 scroll-snap-section"
        >
          <h1 class="text-3xl font-bold mb-4">Contenido de la Sección 5</h1>
          <p class="text-lg">Última sección con altura completa.</p>
        </section> -->
      </div>
    </div>
  </div>
</template>

<style scoped>
/*
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
*/
</style>
