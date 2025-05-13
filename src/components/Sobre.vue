<template>
  <section class="about-section text-white py-16 px-4 relative overflow-hidden" id="sobre">
    <!-- Background elements -->
    <div class="absolute inset-0 z-0">
      <div class="absolute top-[30%] right-[15%] w-64 h-64 rounded-full bg-[#47c5ff] opacity-5 blur-[120px]"></div>
      <div class="absolute bottom-[20%] left-[10%] w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[100px]"></div>

      <!-- Grid pattern -->
      <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
    </div>

    <div class="container mx-auto max-w-4xl relative z-10">
      <!-- header -->
      <div class="mb-8 text-center">
        <h2
          class="text-4xl font-bold bg-gradient-to-r from-[#47c5ff] to-[#0098df] bg-clip-text text-transparent inline-block mb-2">
          Sobre mim
        </h2>
        <div class="w-20 h-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full mx-auto mb-6"></div>
      </div>

      <!-- container sobre -->
      <div
        class="bg-gradient-to-br from-[#121a29] to-[#162339] rounded-2xl p-8 border border-[#ffffff15] shadow-xl relative overflow-hidden">
        <!-- Background element (canto direito) -->
        <div class="absolute -top-24 -right-24 w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[50px]"></div>

        <!-- Bubbles -->
        <div
          class="absolute top-6 right-8 w-16 h-16 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff20] flex items-center justify-center shadow-lg animate-float-slow">
          <img src="@/assets/img/vue.png" alt="Vue.js" class="w-8 h-8 object-contain" />
        </div>

        <div
          class="absolute top-24 right-16 w-14 h-14 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff20] flex items-center justify-center shadow-lg animate-float-medium">
          <img src="@/assets/img/angular.png" alt="Angular" class="w-7 h-7 object-contain" />
        </div>

        <div
          class="absolute top-16 right-32 w-12 h-12 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff20] flex items-center justify-center shadow-lg animate-float-fast">
          <img src="@/assets/img/django.png" alt="Django" class="w-6 h-6 object-contain" />
        </div>

        <div
          class="absolute top-40 right-6 w-10 h-10 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff20] flex items-center justify-center shadow-lg animate-float-medium">
          <img src="@/assets/img/electron.png" alt="Electron" class="w-5 h-5 object-contain" />
        </div>

        <!-- Bio text GSAP animation -->
        <div class="max-w-3xl pr-20" id="bio-sobre">
          <p class="text-lg text-gray-300 leading-relaxed mb-6" id="split">
            Sou um desenvolvedor com experiência prática em desenvolvimento Front-End, utilizando tecnologias como
            <span class="text-highlight">Django</span>,
            <span class="text-highlight">Angular</span>,
            <span class="text-highlight">Vue.js</span>,
            <span class="text-highlight">Electron</span> e outros.
            <span class="block h-4"></span>
            Também possuo capacitação em desenvolvimento <span class="text-highlight">Full Stack</span>.
            <span class="block h-4"></span>
            Além da programação, tenho habilidades em ferramentas como
            <span class="text-highlight">PowerPoint</span>,
            <span class="text-highlight">Photoshop</span> e <span class="text-highlight">Figma</span>,
            refletindo minha afinidade com tecnologia e design.
            <span class="block h-4"></span>
            Sou graduado em <span class="text-highlight">Sistemas de Informação</span> pela
            <span class="text-highlight">Universidade Federal do Acre (UFAC)</span>,
            onde atuei no desenvolvimento de sistemas para a instituição.
          </p>
        </div>

        <!-- Divider -->
        <div class="h-px w-full bg-gradient-to-r from-transparent via-[#ffffff20] to-transparent my-8" id="divider">
        </div>

        <!-- Personal traits -->
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-4 mt-8" id="personal-traits">
          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Proativo</span>
          </div>

          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Criativo</span>
          </div>

          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Colaborativo</span>
          </div>

          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Autodidata</span>
          </div>

          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Resiliente</span>
          </div>

          <div
            class="trait-item flex flex-col items-center gap-2 p-3 rounded-xl hover:bg-[#ffffff08] transition-all duration-300">
            <div class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <span class="text-white text-sm font-medium">Pontual</span>
          </div>
        </div>

        <!-- CTA buttons -->
        <div class="flex flex-wrap justify-center gap-4 mt-10" id="cta-buttons">
          <a href="#contato"
            class="px-6 py-3 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full text-white font-medium hover:shadow-lg hover:shadow-[#47c5ff]/20 transition-all duration-300 transform hover:-translate-y-1 flex items-center gap-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
            </svg>
            Entre em contato
          </a>

          <a href="/public/pdf/Currículo_Anderson_Dantas.pdf" download="Currículo_Anderson_Dantas.pdf"
            class="px-6 py-3 bg-transparent border border-[#47c5ff] rounded-full text-[#47c5ff] font-medium hover:bg-[#47c5ff20] transition-all duration-300 flex items-center gap-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
            </svg>
            Download CV
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.about-section {
  font-family: 'Inter', sans-serif;
  background-color: #0a0c14;
  min-height: 100vh;
}

/* Grid pattern background */
.bg-grid-pattern {
  background-image:
    linear-gradient(to right, #ffffff05 1px, transparent 1px),
    linear-gradient(to bottom, #ffffff05 1px, transparent 1px);
  background-size: 20px 20px;
}

.text-highlight {
  color: #47c5ff;
  font-weight: 600;
}

/* Floating animations for technology bubbles */
@keyframes float-slow {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-10px);
  }
}

@keyframes float-medium {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-8px);
  }
}

@keyframes float-fast {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-6px);
  }
}

.animate-float-slow {
  animation: float-slow 6s ease-in-out infinite;
}

.animate-float-medium {
  animation: float-medium 5s ease-in-out infinite;
}

.animate-float-fast {
  animation: float-fast 4s ease-in-out infinite;
}

/* Trait items hover effect */
.trait-item {
  transition: all 0.3s ease;
}

.trait-item:hover {
  transform: translateY(-3px);
}

.trait-item:hover .w-12 {
  background-color: rgba(71, 197, 255, 0.3);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .pr-20 {
    padding-right: 0;
  }

  .trait-item {
    padding: 2px;
  }
}
</style>

<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import { ScrollTrigger, SplitText } from "gsap/all";

gsap.registerPlugin(ScrollTrigger, SplitText);

onMounted(() => {
  gsap.set("#split", { opacity: 1 });

  document.fonts.ready.then(() => {
    let text = document.querySelector("#split");

    // Create the split text animation
    SplitText.create(text, {
      type: "words,lines",
      linesClass: "line",
      autoSplit: true,
      onSplit: (instance) => {
        gsap.from(instance.lines, {
          yPercent: 120,
          opacity: 0,
          stagger: 0.2,
          duration: 1.2,
          ease: "power2.out",
          scrollTrigger: {
            trigger: "#sobre",
            start: "top 70%",
            end: "bottom 70%",
            scrub: false,
          }
        });
      }
    });

    // Animate the trait items
    const traitItems = document.querySelectorAll('.trait-item');
    gsap.from(traitItems, {
      opacity: 0,
      y: 20,      // de baixo para cima
      stagger: 0.1,
      duration: 1.8,
      ease: "power2.out",
      scrollTrigger: {
        trigger: "#bio-sobre",
        start: "top 60%",
        end: "bottom 60%",
        toggleActions: "play none none none",
      },
      clearProps: "all" // Remove estilos inline após a animação
    });


    // Animate the CTA buttons
    const ctaButtons = document.querySelectorAll('#cta-buttons');
    gsap.from(ctaButtons, {
      opacity: 0,
      y: 20,
      stagger: 0.2,
      duration: 1.8,
      ease: "power2.out",
      scrollTrigger: {
        trigger: ".trait-item",
        start: "top 60%",
        end: "bottom 60%",
        toggleActions: "play none none none",
      },
      clearProps: "all"
    });
  });
});
</script>
