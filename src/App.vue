<template>
  <div class="flex bg-neutral-950 text-white">
    <!-- SIDEBAR -->
    <aside class="w-64 h-screen fixed left-0 top-0 flex flex-col justify-between p-6 border-r border-white/10">

      <!-- Logo -->
      <div class="flex flex-col items-center gap-4">
        <img src="@/assets/logo.svg" class="w-20 opacity-80" />
        <h1 class="text-lg font-bold tracking-wide">JeszDev</h1>
      </div>

      <!-- NAV -->
      <nav class="flex flex-col gap-6">
        <button @click="scrollToSection('section1')" class="nav-item">
          <HomeIcon /> <span>Inicio</span>
        </button>

        <button @click="scrollToSection('section2')" class="nav-item">
          <AboutIcon /> <span>Sobre mí</span>
        </button>

        <button @click="scrollToSection('section3')" class="nav-item">
          <ProjectsIcon /> <span>Proyectos</span>
        </button>

        <button @click="scrollToSection('section4')" class="nav-item">
          <ContactIcon /> <span>Contacto</span>
        </button>
      </nav>

      <!-- Footer -->
      <div class="text-xs text-white/40 text-center">
        © 2026
      </div>
    </aside>

    <!-- CONTENT -->
    <main
      ref="contentContainer"
      class="ml-64 w-full h-screen overflow-y-auto scroll-smooth"
    >
      <section
        id="section1"
        class="section"
        :ref="(el) => setSectionRef(el, 'section1')"
      >
        <HomePage />
      </section>

      <section
        id="section2"
        class="section"
        :ref="(el) => setSectionRef(el, 'section2')"
      >
        <AboutPage />
      </section>

      <section
        id="section3"
        class="section"
        :ref="(el) => setSectionRef(el, 'section3')"
      >
        <ProjectsPage />
      </section>

      <section
        id="section4"
        class="section"
        :ref="(el) => setSectionRef(el, 'section4')"
      >
        <ContactPage />
      </section>
    </main>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'

import HomePage from './sections/HomePage.vue'
import AboutPage from './sections/AboutPage.vue'
import ProjectsPage from './sections/ProjectsPage.vue'
import ContactPage from './sections/ContactPage.vue'

import HomeIcon from './icons/HomeIcon.vue'
import AboutIcon from './icons/AboutIcon.vue'
import ProjectsIcon from './icons/ProjectsIcon.vue'
import ContactIcon from './icons/ContactIcon.vue'

interface SectionRefs {
  [key: string]: HTMLElement | null
}

const contentContainer = ref<HTMLElement | null>(null)
const sectionRefs = ref<SectionRefs>({})
const activeSection = ref('section1')

const setSectionRef = (el: HTMLElement | null, id: string) => {
  sectionRefs.value[id] = el
}

const scrollToSection = (id: string) => {
  const section = sectionRefs.value[id]
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' })
    activeSection.value = id
  }
}

const handleScroll = () => {
  if (!contentContainer.value) return

  const scrollPosition =
    contentContainer.value.scrollTop + window.innerHeight / 2

  for (const [id, section] of Object.entries(sectionRefs.value)) {
    if (!section) continue

    const top = section.offsetTop
    const bottom = top + section.offsetHeight

    if (scrollPosition >= top && scrollPosition <= bottom) {
      activeSection.value = id
      break
    }
  }
}

let timeout: ReturnType<typeof setTimeout>

const onScroll = () => {
  clearTimeout(timeout)
  timeout = setTimeout(handleScroll, 50)
}

onMounted(() => {
  contentContainer.value?.addEventListener('scroll', onScroll)
  handleScroll()
})

onBeforeUnmount(() => {
  contentContainer.value?.removeEventListener('scroll', onScroll)
})
</script>

<style scoped>
.section {
  min-height: 100vh;
  padding: 4rem;
  display: flex;
  align-items: center;
}

/* NAV ITEM PRO */
.nav-item {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1rem;
  color: rgba(255,255,255,0.6);
  transition: all 0.3s ease;
}

.nav-item:hover {
  color: white;
  transform: translateX(5px);
}
</style>
