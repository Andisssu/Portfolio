<template>
    <section ref="skillsSection" class="skills-section px-4 py-16 text-white relative overflow-hidden" id="habilidades">
        <!-- Background elements -->
        <div class="absolute inset-0 z-0 opacity-10">
            <div class="absolute top-[20%] right-[10%] w-64 h-64 rounded-full bg-[#47c5ff] blur-[120px]"></div>
            <div class="absolute bottom-[10%] left-[5%] w-48 h-48 rounded-full bg-[#47c5ff] blur-[100px]"></div>
            <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
        </div>

        <!-- Section header -->
        <div class="relative z-10 flex flex-col items-center justify-center mb-16">
            <h2
                class="text-center text-4xl font-bold bg-gradient-to-r from-[#47c5ff] to-[#0098df] bg-clip-text text-transparent mb-3">
                Habilidades
            </h2>
            <div class="w-20 h-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full"></div>

            <!-- Category filters -->
            <div class="mt-8 flex flex-wrap justify-center gap-3" ref="categoryFilters">
                <button v-for="category in categories" :key="category.id" @click="filterCategory(category.id)" :class="[
                    'px-4 py-2 rounded-full text-sm font-medium transition-all duration-300',
                    activeCategory === category.id
                        ? 'bg-gradient-to-r from-[#47c5ff] to-[#0098df] text-white shadow-lg shadow-[#47c5ff]/20'
                        : 'bg-[#ffffff10] text-white hover:bg-[#ffffff20]'
                ]">
                    {{ category.name }}
                </button>
            </div>
        </div>

        <!-- Skills grid -->
        <div class="relative z-10 grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6 justify-items-center max-w-6xl mx-auto"
            ref="skillsGrid">
            <div v-for="(skill, index) in filteredSkills" :key="index" class="skill-card group" data-skill-item>
                <div class="flex flex-col items-center w-full">
                    <!-- Skill card -->
                    <div
                        class="skill-icon-wrapper relative mb-3 w-20 h-20 rounded-2xl flex items-center justify-center transition-all duration-300 group-hover:scale-110">
                        <div
                            class="absolute inset-0 rounded-2xl bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff20] group-hover:border-[#47c5ff50] transition-all duration-300 shadow-lg">
                        </div>
                        <div
                            class="absolute inset-0 rounded-2xl bg-[#47c5ff] opacity-0 blur-md group-hover:opacity-20 transition-all duration-300">
                        </div>
                        <img :src="skill.img" :alt="skill.nome"
                            class="relative z-10 w-10 h-10 object-contain transition-all duration-300 group-hover:scale-110" />
                    </div>

                    <!-- Skill name -->
                    <span
                        class="skill-name text-center text-sm font-medium text-gray-300 group-hover:text-white transition-all duration-300">
                        {{ skill.nome }}
                    </span>

                    <!-- Skill proficiency indicator -->
                    <div class="mt-2 w-16 h-1 rounded-full bg-[#ffffff20] overflow-hidden">
                        <div class="skill-bar h-full bg-gradient-to-r from-[#47c5ff] to-[#0098df] transition-all duration-1000 ease-out"
                            :style="{ width: `${skill.proficiency || 85}%` }"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.skills-section {
    font-family: 'Inter', sans-serif;
    background-color: #0a0c14;
    min-height: 80vh;
}

.skill-card {
    width: 100%;
    max-width: 140px;
    padding: 1rem;
    transition: all 0.3s ease;
}

.skill-name {
    width: 100%;
    max-width: 120px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

.bg-grid-pattern {
    background-image:
        linear-gradient(to right, #ffffff05 1px, transparent 1px),
        linear-gradient(to bottom, #ffffff05 1px, transparent 1px);
    background-size: 20px 20px;
}

.skill-card:hover .skill-icon-wrapper {
    box-shadow: 0 0 20px rgba(71, 197, 255, 0.2);
}

button {
    opacity: 0;
    transition: opacity 0.3s ease;
}
</style>

<script setup>
import { onMounted, ref, computed } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

import htmlImg from "@/assets/img/html.png";
import cssImg from "@/assets/img/css.png";
import jsImg from "@/assets/img/js.png";
import vueImg from "@/assets/img/vue.png";
import electronImg from "@/assets/img/electron.png";
import angularImg from "@/assets/img/angular.png";
import springbootImg from "@/assets/img/springboot.png";
import figmaImg from "@/assets/img/figma.png";
import bootstrapImg from "@/assets/img/bootstrap.png";
import tailwindImg from "@/assets/img/tailwind.png";
import mysqlImg from "@/assets/img/mysql.png";
import djangoImg from "@/assets/img/django.png";
import pythonImg from "@/assets/img/python.png";
import wordpressImg from "@/assets/img/wordpress.png";
import postgreImg from "@/assets/img/postgre.png";

gsap.registerPlugin(ScrollTrigger);

// Define skill categories
const categories = [
    { id: 'all', name: 'Todas' },
    { id: 'frontend', name: 'Frontend' },
    { id: 'backend', name: 'Backend' },
    { id: 'design', name: 'Design' },
    { id: 'database', name: 'Banco de Dados' },
];

const activeCategory = ref('all');

const skills = [
    { nome: "HTML", img: htmlImg, category: 'frontend', proficiency: 95 },
    { nome: "CSS", img: cssImg, category: 'frontend', proficiency: 90 },
    { nome: "JavaScript", img: jsImg, category: 'frontend', proficiency: 85 },
    { nome: "Vue.js", img: vueImg, category: 'frontend', proficiency: 90 },
    { nome: "Electron", img: electronImg, category: 'frontend', proficiency: 75 },
    { nome: "Angular", img: angularImg, category: 'frontend', proficiency: 80 },
    { nome: "Spring Boot", img: springbootImg, category: 'backend', proficiency: 70 },
    { nome: "Figma", img: figmaImg, category: 'design', proficiency: 85 },
    { nome: "Bootstrap", img: bootstrapImg, category: 'frontend', proficiency: 90 },
    { nome: "Tailwind", img: tailwindImg, category: 'frontend', proficiency: 95 },
    { nome: "MySQL", img: mysqlImg, category: 'database', proficiency: 80 },
    { nome: "Django", img: djangoImg, category: 'backend', proficiency: 75 },
    { nome: "Python", img: pythonImg, category: 'backend', proficiency: 85 },
    { nome: "WordPress", img: wordpressImg, category: 'frontend', proficiency: 80 },
    { nome: "PostgreSQL", img: postgreImg, category: 'database', proficiency: 75 }
];

// Filter skills based on active category
const filteredSkills = computed(() => {
  if (activeCategory.value === 'all') {
    return skills;
  }
  return skills.filter(skill => skill.category === activeCategory.value);
});

// Refs for animation targets
const skillsSection = ref(null);
const skillsGrid = ref(null);
const categoryFilters = ref(null);

// Filter function
const filterCategory = (category) => {
  // If same category clicked, do nothing
  if (activeCategory.value === category) return;
  
  // Set new active category
  activeCategory.value = category;
  
  // Animate out current skills
  const skillItems = skillsGrid.value.querySelectorAll('[data-skill-item]');
  
  gsap.to(skillItems, {
    opacity: 0,
    y: 20,
    stagger: 0.05,
    duration: 0.3,
    onComplete: () => {
      // After animation out completes, animate in the filtered skills
      setTimeout(() => {
        const newSkillItems = skillsGrid.value.querySelectorAll('[data-skill-item]');
        gsap.fromTo(newSkillItems, 
          { opacity: 0, y: 30 },
          { 
            opacity: 1, 
            y: 0, 
            stagger: 0.05, 
            duration: 0.5,
            ease: "power2.out"
          }
        );
      }, 50); // Small delay to ensure DOM updates
    }
  });
};

onMounted(() => {
  // Initial animation for category filters
  const filterButtons = categoryFilters.value.querySelectorAll('button');
  gsap.from(filterButtons, {
    opacity: 1,
    y: -20,
    stagger: 0.1,
    duration: 0.8,
    ease: "power2.out",
    delay: 0.3
  });

  // Initial animation for skill items
  const skillItems = skillsGrid.value.querySelectorAll('[data-skill-item]');
  
  // Create a staggered entrance animation
  gsap.from(skillItems, {
    opacity: 0.9,
    y: 20,
    scale: 1,
    duration: 0.8,
    stagger: {
      amount: 1.5, // Total stagger time
      grid: [5, 5], // Approximate grid size
      from: "center"
    },
    ease: "power3.out",
    scrollTrigger: {
      trigger: skillsSection.value,
      start: "top 70%",
      toggleActions: "play none none none"
    }
  });
  
//   // Add floating animation to some random skill items for visual interest
//   skillItems.forEach((item, index) => {
//     if (index % 3 === 0) { // Apply to every third item
//       gsap.to(item, {
//         y: "10px",
//         duration: 2 + Math.random(),
//         repeat: -1,
//         yoyo: true,
//         ease: "sine.inOut",
//         delay: Math.random() * 2
//       });
//     }
//   });
  
  // Animate skill proficiency bars
  const proficiencyBars = skillsGrid.value.querySelectorAll('.skill-card .mt-2 div');
  gsap.from(proficiencyBars, {
    width: 0,
    duration: 1.5,
    stagger: 0.1,
    ease: "power2.out",
    scrollTrigger: {
      trigger: skillsSection.value,
      start: "top 60%",
      toggleActions: "play none none none",
      scrub: false,
    }
  });
});
</script>