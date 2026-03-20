<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';
import ProjectCard from '../components/ProjectCard.vue';

const projects = [
  {
    title: 'Cadena de custodia',
    description: 'Plataforma el registro de la cadena de  custodia y gestion de indicios.',
    image: '/src/assets/images/sistema-cadena-custodia.png',
    tech: ['Laravel', 'Bootstrap', 'jQuery'],
    demo: '#',
    github: '#',
  },
  {
    title: 'E-commerce',
    description: 'Tienda online con carrito y pagos.',
    image: '/src/assets/images/sistema-acceius.png',
    tech: ['Vue', 'Stripe'],
    demo: '#',
    github: '#',
  },
  {
    title: 'Sistema de registro de cadena de custodia',
    description: 'Plataforma para administración de usuarios y roles.',
    image: '/src/assets/images/project-1.jpg',
    tech: ['Laravel', 'bootstrap', 'jQuery'],
    demo: '#',
    github: '#',
  },
  {
    title: 'E-commerce',
    description: 'Tienda online con carrito y pagos.',
    image: '/src/assets/images/project-1.jpg',
    tech: ['Vue', 'Stripe'],
    demo: '#',
    github: '#',
  },
];
</script>

<template>
  <section class="w-full">
    <div class="flex justify-center">
      <TitleSection title="PROYECTOS" data-aos="fade-up" />
    </div>

    <!-- GRID -->
    <div class="grid md:grid-cols-3 gap-8">
      <ProjectCard
        v-for="(project, index) in projects"
        :key="index"
        v-bind="project"
        data-aos="fade-up"
        :data-aos-delay="index * 100"
      />
    </div>
  </section>
</template>
