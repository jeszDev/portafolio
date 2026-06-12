<script setup lang="ts">
import { ref } from 'vue';
import TitleSection from '../components/TitleSection.vue';
import ProjectCard from '../components/ProjectCard.vue';
import ProjectModal from '../components/ProjectModal.vue';

interface Project {
  title: string
  description: string
  image: string
  tech: string[]
  demo: string
  github: string
  detailedDescription?: string
  role?: string
  date?: string
  status?: string
  features?: string[]
}

const projects: Project[] = [
  {
    title: 'Cadena de custodia',
    description: 'Plataforma para el registro de la cadena de custodia y gestión de indicios.',
    image: '/src/assets/images/sistema-cadena-custodia.png',
    tech: ['Laravel', 'Bootstrap', 'jQuery', 'SQL Server'],
    demo: '#',
    github: '#',
    detailedDescription: 'Una solución digital especializada para la Fiscalía General del Estado, orientada a registrar y realizar el seguimiento estricto del flujo de custodia de indicios y elementos materiales probatorios. Este sistema garantiza que cada registro sea inmutable y cumpla con las normativas legales de preservación.',
    role: 'Full Stack Developer',
    date: '2023 - En Curso',
    status: 'ONLINE // EN PRODUCCIÓN',
    features: [
      'Trazabilidad completa e inmutable del ciclo de vida de las evidencias.',
      'Generación automática y descarga del formato digital oficial (PDF) de cadena de custodia.',
      'Búsqueda avanzada y filtros rápidos por número de carpeta de investigación o ID.',
      'Control estricto de accesos y firmas digitales para los custodios autorizados.'
    ]
  },
  {
    title: 'E-commerce Acceius',
    description: 'Tienda online con carrito de compras y pasarela de pagos integrada.',
    image: '/src/assets/images/sistema-acceius.png',
    tech: ['Vue.js', 'Vite', 'Stripe API', 'TailwindCSS'],
    demo: '#',
    github: '#',
    detailedDescription: 'Plataforma de comercio electrónico de alto rendimiento que integra un carrito de compras dinámico y reactivo, sincronización en tiempo real del estado de compra, y un flujo de checkout seguro a través de la integración de Stripe API. Diseñada con un enfoque en la velocidad de carga y experiencia de usuario fluida.',
    role: 'Frontend Developer',
    date: '2024',
    status: 'DEMO // ONLINE',
    features: [
      'Integración fluida con la API de pagos de Stripe Checkout.',
      'Carrito de compras reactivo con persistencia local en el navegador del cliente.',
      'Diseño responsivo y adaptativo optimizado para una alta conversión móvil.',
      'Panel administrativo integrado para la visualización del catálogo de productos.'
    ]
  },
  {
    title: 'Sistema de Registro y Auditoría',
    description: 'Plataforma para administración centralizada de usuarios, roles y logs.',
    image: '/src/assets/images/project-1.jpg',
    tech: ['Laravel', 'Bootstrap', 'jQuery', 'MySQL'],
    demo: '#',
    github: '#',
    detailedDescription: 'Un panel de control administrativo y sistema de seguridad centralizado enfocado en la gestión de roles, permisos granulares y auditoría de accesos. Permite crear esquemas dinámicos de permisos (RBAC) y registrar logs detallados de acciones del usuario para fines de seguridad institucional.',
    role: 'Backend Developer',
    date: '2023',
    status: 'COMPLETADO // EN PRODUCCIÓN',
    features: [
      'Control de acceso basado en roles (RBAC) con asignación de permisos a nivel de ruta.',
      'Módulo de auditoría que registra cada creación, edición y eliminación de datos (logs).',
      'Gráficos interactivos en tiempo real sobre la actividad de los usuarios en el sistema.',
      'Generación y exportación de reportes de accesos en formatos PDF y Excel.'
    ]
  },
  {
    title: 'Dashboard de Analítica',
    description: 'Panel interactivo para la visualización de métricas clave y analíticas.',
    image: '/src/assets/images/project-1.jpg',
    tech: ['Vue.js', 'Pinia', 'Chart.js', 'TailwindCSS'],
    demo: '#',
    github: '#',
    detailedDescription: 'Dashboard analítico diseñado para el monitoreo de indicadores de desempeño operativo de sistemas administrativos. Cuenta con componentes gráficos dinámicos que actualizan la información mediante peticiones asíncronas, permitiendo a los tomadores de decisiones visualizar estadísticas clave de manera interactiva.',
    role: 'Frontend Developer',
    date: '2024',
    status: 'COMPLETADO // PREVIEW',
    features: [
      'Gráficos interactivos dinámicos y mapas de calor utilizando Chart.js.',
      'Manejo de estado centralizado con Pinia para optimizar el flujo de datos entre componentes.',
      'Configuración personalizada de vistas y paneles de control según el rol de usuario.',
      'Actualizaciones asíncronas en tiempo real y descarga de reportes ejecutivos en PDF.'
    ]
  }
];

const selectedProject = ref<Project | null>(null);
const isModalOpen = ref(false);

const openProjectDetails = (project: Project) => {
  selectedProject.value = project;
  isModalOpen.value = true;
};
</script>

<template>
  <section class="w-full">
    <div class="flex justify-center">
      <TitleSection title="PROYECTOS" data-aos="fade-up" />
    </div>

    <!-- GRID -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      <ProjectCard
        v-for="(project, index) in projects"
        :key="index"
        v-bind="project"
        data-aos="fade-up"
        :data-aos-delay="index * 100"
        @open-details="openProjectDetails(project)"
      />
    </div>

    <!-- DETAILS MODAL -->
    <ProjectModal
      :project="selectedProject"
      :is-open="isModalOpen"
      @close="isModalOpen = false"
    />
  </section>
</template>
