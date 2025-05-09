<template>
  <section class="projects-section text-white py-16 px-4 relative overflow-hidden" id="projetos">
    <!-- Background elements -->
    <div class="absolute inset-0 z-0">
      <div class="absolute top-[20%] right-[10%] w-64 h-64 rounded-full bg-[#47c5ff] opacity-5 blur-[120px]"></div>
      <div class="absolute bottom-[10%] left-[5%] w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[100px]"></div>

      <!-- Grid pattern -->
      <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
    </div>

    <!-- Section header -->
    <div class="relative z-10 flex flex-col items-center justify-center mb-16">
      <h2
        class="text-center text-4xl font-bold bg-gradient-to-r from-[#47c5ff] to-[#0098df] bg-clip-text text-transparent mb-3">
        Projetos
      </h2>
      <div class="w-20 h-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full mb-6"></div>
      <p class="text-center text-gray-300 max-w-2xl mx-auto mb-8">
        Conheça alguns dos projetos que desenvolvi, aplicando diversas tecnologias e solucionando problemas reais.
      </p>

      <!-- Project filters -->
      <div class="flex flex-wrap justify-center gap-3 mb-10">
        <button v-for="category in categories" :key="category.id" @click="filterCategory(category.id)" :class="[
          'px-4 py-2 rounded-full text-sm font-medium transition-all duration-300',
          activeCategory === category.id
            ? 'bg-gradient-to-r from-[#47c5ff] to-[#0098df] text-white shadow-lg shadow-[#47c5ff]/20'
            : 'bg-[#ffffff10] text-gray-300 hover:bg-[#ffffff20]'
        ]">
          {{ category.name }}
        </button>
      </div>
    </div>

    <!-- Projects grid -->
    <div class="relative z-10 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-3 gap-8 max-w-7xl mx-auto"
      ref="projectsGrid">
      <div v-for="(project, index) in filteredProjects" :key="index" class="project-card group"
        :class="{ 'featured-project': project.featured }">
        <!-- Project card -->
        <a :href="project.githubLink" target="_blank">
          <div
            class="relative flex flex-col h-full overflow-hidden rounded-xl bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff15] group-hover:border-[#47c5ff40] transition-all duration-500 shadow-xl">
            <!-- Featured badge -->
            <!-- <div v-if="project.featured"
        class="absolute top-4 right-4 z-20 px-3 py-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full text-xs font-medium text-white shadow-lg">
        Destaque
      </div> -->

            <!-- Canvas and image -->
            <div class="relative h-48 overflow-hidden group" style="--active-color: #e0f2fe">
              <!-- pixel-canvas (hover effect background) -->
              <pixel-canvas class="absolute inset-0 z-10" data-gap="10" data-speed="25"
                data-colors="#e0f2fe, #7dd3fc, #0ea5e9"></pixel-canvas>

              <!-- gradient -->
              <div class="absolute inset-0 bg-gradient-to-t from-[#0a0c14] to-transparent opacity-60 z-10"></div>

              <!-- Project image -->
              <img :src="project.image" :alt="project.title"
                class="w-full h-full object-cover transition-all duration-700 opacity-40 group-hover:scale-110 z-0 relative" />

              <!-- icone github -->
              <div
                class="absolute inset-0 flex items-center justify-center z-30 opacity-0 group-hover:opacity-100 transition duration-300">
                <svg xmlns="http://www.w3.org/2000/svg" width="60%" height="60%" fill="currentcolor" viewBox="0 0 50 50"
                  class="text-white hover:text-sky-400 transition">
                  <path
                    d="M17.791,46.836C18.502,46.53,19,45.823,19,45v-5.4c0-0.197,0.016-0.402,0.041-0.61C19.027,38.994,19.014,38.997,19,39 c0,0-3,0-3.6,0c-1.5,0-2.8-0.6-3.4-1.8c-0.7-1.3-1-3.5-2.8-4.7C8.9,32.3,9.1,32,9.7,32c0.6,0.1,1.9,0.9,2.7,2c0.9,1.1,1.8,2,3.4,2 c2.487,0,3.82-0.125,4.622-0.555C21.356,34.056,22.649,33,24,33v-0.025c-5.668-0.182-9.289-2.066-10.975-4.975 c-3.665,0.042-6.856,0.405-8.677,0.707c-0.058-0.327-0.108-0.656-0.151-0.987c1.797-0.296,4.843-0.647,8.345-0.714 c-0.112-0.276-0.209-0.559-0.291-0.849c-3.511-0.178-6.541-0.039-8.187,0.097c-0.02-0.332-0.047-0.663-0.051-0.999 c1.649-0.135,4.597-0.27,8.018-0.111c-0.079-0.5-0.13-1.011-0.13-1.543c0-1.7,0.6-3.5,1.7-5c-0.5-1.7-1.2-5.3,0.2-6.6 c2.7,0,4.6,1.3,5.5,2.1C21,13.4,22.9,13,25,13s4,0.4,5.6,1.1c0.9-0.8,2.8-2.1,5.5-2.1c1.5,1.4,0.7,5,0.2,6.6c1.1,1.5,1.7,3.2,1.6,5 c0,0.484-0.045,0.951-0.11,1.409c3.499-0.172,6.527-0.034,8.204,0.102c-0.002,0.337-0.033,0.666-0.051,0.999 c-1.671-0.138-4.775-0.28-8.359-0.089c-0.089,0.336-0.197,0.663-0.325,0.98c3.546,0.046,6.665,0.389,8.548,0.689 c-0.043,0.332-0.093,0.661-0.151,0.987c-1.912-0.306-5.171-0.664-8.879-0.682C35.112,30.873,31.557,32.75,26,32.969V33 c2.6,0,5,3.9,5,6.6V45c0,0.823,0.498,1.53,1.209,1.836C41.37,43.804,48,35.164,48,25C48,12.318,37.683,2,25,2S2,12.318,2,25 C2,35.164,8.63,43.804,17.791,46.836z">
                  </path>
                </svg>
              </div>
            </div>

            <!-- Project content -->
            <div class="p-6 flex-grow">
              <div class="flex flex-wrap gap-2 mb-4">
                <span v-for="(tech, techIndex) in project.technologies" :key="techIndex"
                  class="px-2 py-1 rounded-md bg-[#ffffff10] text-xs font-medium text-[#47c5ff]">
                  {{ tech }}
                </span>
              </div>

              <h3 class="text-xl font-bold text-white mb-2 group-hover:text-[#47c5ff] transition-all duration-300">
                {{ project.title }}
              </h3>

              <p class="text-gray-400 text-sm mb-4">
                {{ project.description }}
              </p>
            </div>

            <!-- Project footer -->
            <a :href="project.githubLink" target="_blank"
              class="inline-flex items-center gap-2 text-sm font-medium text-white hover:text-[#47c5ff] transition-all duration-300">
              <div class="p-6 pt-0 mt-auto">
                Ver mais detalhes
                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24"
                  stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
                </svg>
              </div>
            </a>
          </div>
        </a>
      </div>
    </div>

    <div class="relative z-10 flex justify-center mt-12">
      <a href="https://github.com/Andisssu" target="_blank" rel="noopener noreferrer"
        class="px-8 py-3 rounded-full bg-gradient-to-r from-[#121a29] to-[#162339] border border-[#ffffff20] hover:border-[#47c5ff40] text-white font-medium transition-all duration-300 hover:shadow-lg flex items-center gap-2 group">
        <span>Ver todos os projetos</span>
        <svg xmlns="http://www.w3.org/2000/svg"
          class="w-5 h-5 transform group-hover:translate-x-1 transition-transform duration-300" fill="none"
          viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
        </svg>
      </a>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.projects-section {
  font-family: 'Inter', sans-serif;
  background-color: #0a0c14;
  min-height: 100vh;
}

.bg-grid-pattern {
  background-image:
    linear-gradient(to right, #ffffff05 1px, transparent 1px),
    linear-gradient(to bottom, #ffffff05 1px, transparent 1px);
  background-size: 20px 20px;
}

.project-card {
  height: 100%;
  transition: all 0.3s ease;
}

.project-card:hover {
  transform: translateY(-8px);
}

.featured-project {
  grid-column: span 1;
}

@media (min-width: 1024px) {
  .featured-project {
    grid-column: span 2;
  }
}
</style>

<script setup>
import { ref, computed } from 'vue';
import '@/assets/js/pixel_canvas.js';

import deagro from "@/assets/img/projetos/deagro.png";
import nai from "@/assets/img/projetos/nai.png";
import sismedico from "@/assets/img/projetos/sismedico.png";
import avasoft from "@/assets/img/projetos/avasoft.png";
import portfolio from "@/assets/img/projetos/portfolio.png";
import obras from "@/assets/img/projetos/obras.png";

const categories = [
  { id: 'all', name: 'Todos' },
  { id: 'web', name: 'Web' },
  { id: 'mobile', name: 'Mobile' },
  { id: 'desktop', name: 'Desktop' },
  // { id: 'backend', name: 'Backend' },
];

const activeCategory = ref('all');

// Project data
const projects = [
  {
    title: 'Sistema de Gerenciamento de Projetos e Setores para SEAGRI',
    description: 'Sistema desenvolvido para a Secretaria de Estado da Agricultura (SEAGRI) para gerenciar projetos e setores internos.',
    image: deagro,
    githubLink: 'https://github.com/webacademyufac/hands-on-t3-moto-e',
    demoLink: '#',
    technologies: ['Angular', 'Spring Boot', 'MySQL', 'Java', 'Figma', 'Html', 'CSS', 'Bootstrap'],
    category: 'web',
    featured: true
  },
  {
    title: 'Sistema de Gestão de Bolsistas do NAI',
    description: 'Plataforma para gerenciamento de bolsistas desenvolvida durante estágio supervisionado no NAI-UFAC.',
    image: nai,
    githubLink: 'https://github.com/Andisssu/estagio-supervisionado2023',
    demoLink: '#',
    technologies: ['Django', 'Python', 'SQLite', 'Bootstrap', 'Html', 'CSS'],
    category: 'web',
    featured: false
  },
  {
    title: 'Sistema de Gerenciamento do Hospital Universitário',
    description: 'Sistema completo para gerenciamento de processos hospitalares desenvolvido para o Hospital Universitário da UFAC.',
    image: sismedico,
    githubLink: 'https://github.com/Andisssu/sistema_medico',
    demoLink: '#',
    technologies: ['Django', 'Python', 'SQLite', 'Bootstrap', 'Html', 'CSS'],
    category: 'web',
    featured: false
  },
  {
    title: 'Software para Avaliação Antropométrica',
    description: 'Aplicativo para realizar e gerenciar avaliações antropométricas, desenvolvido como projeto pessoal na UFAC.',
    image: avasoft,
    githubLink: 'https://github.com/Andisssu/avasoft',
    demoLink: '#',
    technologies: ['Electron', 'Vue', 'JavaScript', 'PostgreSQL', 'Html', 'CSS', 'tailwindcss'],
    category: 'desktop',
    featured: false
  },
  {
    title: 'Portfólio Pessoal',
    description: 'Portfólio pessoal desenvolvido para apresentar meus projetos e habilidades.',
    image: portfolio,
    githubLink: 'https://github.com/Andisssu/Portfolio',
    technologies: ['Vue', 'JavaScript', 'Html', 'CSS', 'tailwindcss', 'GSAP'],
    category: 'web',
    featured: false
  },
  {
    title: 'Projetos Futuros',
    description: 'Reservado para futuros projetos.',
    image: obras,
    githubLink: '#',
    technologies: ['Fé em Deus'],
    category: ['all', 'web', 'mobile', 'desktop'],
    featured: false
  }
];

// Filtered projects based on active category
const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') {
    return projects;
  }
  return projects.filter(project => project.category === activeCategory.value);
});

// Filter function
const filterCategory = (category) => {
  activeCategory.value = category;
};


</script>