<template>
  <section class="experience-section text-white py-16 px-4 min-h-[30vh] relative overflow-hidden" id="experiencia">
    <!-- Background elements -->
    <div class="absolute top-0 left-0 w-full h-full opacity-5">
      <div class="absolute top-[10%] left-[5%] w-32 h-32 rounded-full bg-[#47c5ff] blur-[80px]"></div>
      <div class="absolute bottom-[20%] right-[10%] w-40 h-40 rounded-full bg-[#47c5ff] blur-[100px]"></div>
    </div>

    <!-- Section header -->
    <div class="flex flex-col items-center justify-center mb-12">
      <h2
        class="text-center text-4xl font-bold bg-gradient-to-r from-[#47c5ff] to-[#0098df] bg-clip-text text-transparent mb-3">
        Experiência
      </h2>
      <div class="w-20 h-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full"></div>
    </div>

    <!-- Experience content -->
    <div class="flex flex-col md:flex-row items-start justify-center gap-8 max-w-7xl mx-auto">
      <!-- Timeline navigation -->
      <div class="timeline-nav w-full md:w-auto md:min-w-[220px] mb-8 md:mb-0 relative">
        <!-- Timeline line (visible on md+ screens) -->
        <div
          class="hidden md:block absolute left-[18px] top-6 bottom-6 w-0.5 bg-gradient-to-b from-transparent via-[#47c5ff] to-transparent">
        </div>

        <!-- Timeline buttons -->
        <div
          class="flex flex-row flex-wrap content-center justify-center md:flex-col gap-4 overflow-x-auto md:overflow-visible pb-2 md:pb-0">
          <button v-for="option in options" :key="option.id" @click="selected = option.id" :class="[
            'timeline-btn flex items-center px-5 py-4 rounded-xl border backdrop-blur-sm transition-all duration-300 relative',
            selected === option.id
              ? 'bg-gradient-to-r from-[#121a29] to-[#162339] border-[#47c5ff] text-white shadow-lg scale-[1.02]'
              : 'bg-[#12121230] border-[#ffffff20] text-white hover:border-[#47c5ff50]'
          ]">
            <!-- Timeline dot indicator -->
            <div :class="[
              'hidden md:block absolute -left-[22px] w-4 h-4 rounded-full border-2 transition-all duration-300',
              selected === option.id
                ? 'bg-[#47c5ff] border-[#0098df] scale-125'
                : 'bg-[#121212] border-[#47c5ff50]'
            ]"></div>

            <div class="flex items-center">
              <div :class="[
                'w-10 h-10 rounded-lg mr-3 flex items-center justify-center transition-all duration-300',
                selected === option.id
                  ? 'bg-gradient-to-br from-[#47c5ff] to-[#0098df]'
                  : 'bg-[#ffffff10]'
              ]">
                <img :src="option.icon" alt="Ícone" class="w-6 h-6 rounded-sm" />
              </div>
              <span class="font-medium">{{ option.label }}</span>
            </div>
          </button>
        </div>
      </div>

      <!-- Experience card -->
      <transition name="fade">
        <div class="experience-card w-full rounded-2xl transition-all duration-500 transform"
          :class="{ 'scale-100 opacity-100': true, 'scale-95 opacity-0': false }">
          <div v-if="content[selected]" :key="selected" class="experience-card w-full rounded-2xl px-8">
            <div
              class="card-content bg-gradient-to-br from-[#121a29] to-[#162339] rounded-2xl p-8 border border-[#ffffff10] shadow-xl relative overflow-hidden">
              <!-- Card background accent -->
              <div class="absolute -top-24 -right-24 w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[50px]"></div>

              <!-- Card header -->
              <div class="mb-6">
                <h3 class="text-2xl font-bold text-[#47c5ff] mb-2">
                  {{ content[selected].title }}
                </h3>
                <div class="flex items-center gap-3 mb-4">
                  <div class="px-3 py-1 rounded-full bg-[#47c5ff20] text-[#47c5ff] text-sm font-medium">
                    {{ content[selected].period }}
                  </div>
                </div>
              </div>

              <!-- Card details -->
              <ul class="list-none space-y-4">
                <li v-for="(item, index) in content[selected].details" :key="index"
                  class="flex items-start gap-3 group">
                  <span
                    class="flex-shrink-0 w-6 h-6 rounded-full bg-[#47c5ff20] flex items-center justify-center mt-0.5 group-hover:bg-[#47c5ff40] transition-all duration-300">
                    <span class="text-[#47c5ff] text-sm">⟡</span>
                  </span>
                  <span class="text-gray-200 group-hover:text-white transition-all duration-300">{{ item }}</span>
                </li>
              </ul>

              <!-- Technology tags -->
              <div class="mt-8 pt-6 border-t border-[#ffffff15]">
                <div class="flex flex-wrap gap-2">
                  <div v-for="(tech, index) in extractTechnologies(content[selected].details)" :key="index"
                    class="px-3 py-1 rounded-full bg-[#ffffff10] text-sm text-gray-300 hover:bg-[#47c5ff20] hover:text-[#47c5ff] transition-all duration-300">
                    {{ tech }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ufacImg from '@/assets/img/ufac.png'
import freelancerImg from '@/assets/img/freelancer.png'

const selected = ref('UFAC')

const options = [
  { id: 'wbacademy', label: 'WebAcademy', icon: ufacImg },
  { id: 'UFAC', label: 'UFAC', icon: ufacImg },
  { id: 'freelancer', label: 'Freelancer', icon: freelancerImg },
]

const content = {
  UFAC: {
    title: 'Sistema de Gerenciamento do Hospital Universitário - Full Stack | NTI - UFAC',
    period: 'Março 2024 a Março 2025',
    details: [
      'Desenvolvimento de Interfaces de usuários e criação de páginas web com Django;',
      'Desenvolvimento e ajustes no backend com Framework Django;',
      'Criação e Ajustes no banco de dados;',
      'Implementação de funções de autenticação e autorização, impressão de PDF, restrição de acesso por usuário entre outros...;',
      'Tecnologias: JavaScript, HTML, CSS, Django, SQLite, Figma;',
    ]
  },
  wbacademy: {
    title: 'Sistema de Gerenciamento de Projetos e Setores para SEAGRI - Front-end | WebAcademy',
    period: '2024',
    details: [
      'Desenvolvimento de interfaces de usuários e criação das páginas web;',
      'Componentes para cadastros e listagem de entidades do sistema;',
      'Estilização e suporte a responsividade',
      'Integração com Back-end e interceptação de requisições HTTP com HttpInterceptor;',
      'Configuração de rotas e navegação entre as páginas utilizando Angular Router;',
      'Desenvolvimento do protótipo de alta fidelidade do sistema utilizando Figma;',
      'Tecnologias: Java, Angular, TypeScript, Spring Boot, HTML, CSS, MySQL, Figma;',
    ]
  },
  freelancer: {
    title: 'Suporte no Desenvolvimento | Freelancer',
    period: '2024',
    details: [
      'Suporte no teste de funcionalidades dos apps;',
      'Criação de páginas web e elementos das páginas;',
      'Criação de Arte para produtos',
      'Tecnologias: PhotoShop, Figma, WordPress;',
    ]
  }
}

// Função para extrair tecnologias dos detalhes
const extractTechnologies = (details) => {
  const techLine = details.find(line => line.includes('Tecnologias:'))
  if (!techLine) return []

  const techPart = techLine.split('Tecnologias:')[1]
  return techPart.split(',').map(tech => tech.trim().replace(';', ''))
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(10px);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}

.experience-section {
  font-family: 'Inter', sans-serif;
  background-color: #0a0c14;
}

.timeline-btn {
  min-width: 180px;
}

.experience-card {
  height: fit-content;
}

.timeline-nav::-webkit-scrollbar {
  height: 4px;
}

.timeline-nav::-webkit-scrollbar-track {
  background: #12121220;
  border-radius: 10px;
}

.timeline-nav::-webkit-scrollbar-thumb {
  background: #47c5ff50;
  border-radius: 10px;
}


.experience-card {
  animation: fadeIn 0.5s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>