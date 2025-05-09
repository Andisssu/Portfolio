<template>
    <footer class="footer-section relative overflow-hidden">
      <!-- Background elements -->
      <div class="absolute inset-0 z-0">
        <div class="absolute bottom-0 left-0 w-full h-full bg-gradient-to-t from-[#080a12] to-transparent opacity-70"></div>
        <div class="absolute bottom-0 left-[10%] w-64 h-64 rounded-full bg-[#47c5ff] opacity-5 blur-[100px]"></div>
        <div class="absolute bottom-0 right-[10%] w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[80px]"></div>
      </div>
  
      <!-- Main footer content -->
      <div class="footer-main relative z-10 container mx-auto px-6 pt-16 pb-8">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-10 mb-12">
          <!-- Brand column -->
          <div class="flex flex-col">
            <div class="flex items-center gap-3 mb-4">
              <!-- Logo or avatar could go here -->
              <div class="w-12 h-12 rounded-full bg-gradient-to-br from-[#47c5ff] to-[#0098df] flex items-center justify-center text-white font-bold text-xl">
                AD
              </div>
              <h3 class="text-xl font-bold text-white">Anderson Dantas</h3>
            </div>
            <p class="text-gray-400 mb-6 max-w-xs">
              Desenvolvedor Full Stack.
            </p>
            <!-- <div class="flex space-x-4">

              <a href="#" class="social-icon-link">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/github.png" alt="GitHub" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="#" class="social-icon-link">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/linkedin.png" alt="LinkedIn" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="#" class="social-icon-link">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/gmail.png" alt="Email" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="#" class="social-icon-link">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/whatsapp.png" alt="Email" class="w-5 h-5 object-contain" />
                </div>
              </a>
            </div> -->
          </div>
  
          <!-- Links -->
          <div class="flex flex-col">
            <h4 class="text-white font-semibold mb-6 text-lg">Links Rápidos</h4>
            <ul class="space-y-3">
              <li>
                <a href="#perfil" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Início
                </a>
              </li>
              <li>
                <a href="#sobre" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Sobre
                </a>
              </li>
              <li>
                <a href="#experiencia" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Experiência
                </a>
              </li>
              <li>
                <a href="#habilidades" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Habilidades
                </a>
              </li>
              <li>
                <a href="#projetos" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Projetos
                </a>
              </li>
              <li>
                <a href="#contato" class="text-gray-400 hover:text-[#47c5ff] transition-all duration-300 flex items-center gap-2">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#47c5ff]"></span>
                  Contato
                </a>
              </li>
            </ul>
          </div>
  
          <!-- Contact column -->
          <div class="flex flex-col">
            <h4 class="text-white font-semibold mb-6 text-lg">Contato</h4>
            <ul class="space-y-4">
              <li class="flex items-start gap-3">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] flex items-center justify-center mt-1">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-[#47c5ff]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                </div>
                <div>
                  <h5 class="text-sm text-gray-400 mb-1">Email</h5>
                  <a href="mailto:seu@email.com" class="text-white hover:text-[#47c5ff] transition-all duration-300">netodantas3@email.com</a>
                </div>
              </li>
              <li class="flex items-start gap-3">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] flex items-center justify-center mt-1">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-[#47c5ff]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <div>
                  <h5 class="text-sm text-gray-400 mb-1">Telefone</h5>
                  <a href="tel:+5500000000000" class="text-white hover:text-[#47c5ff] transition-all duration-300">(68) 99219-2977</a>
                </div>
              </li>
              <li class="flex items-start gap-3">
                <div class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] flex items-center justify-center mt-1">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-[#47c5ff]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                  </svg>
                </div>
                <div>
                  <h5 class="text-sm text-gray-400 mb-1">Localização</h5>
                  <p class="text-white">Rio Branco, Acre - Brasil</p>
                </div>
              </li>
            </ul>
          </div>
        </div>
  
        <!-- Divider -->
        <div class="h-px w-full bg-gradient-to-r from-transparent via-[#ffffff20] to-transparent my-8"></div>
  
        <!-- Bottom footer -->
        <div class="flex flex-col md:flex-row justify-between items-center gap-4">
          <div class="text-gray-400 text-sm">
            © 2025 <a href="https://andersondev.com" class="text-[#47c5ff] font-medium hover:text-white transition-all duration-300">andersondev.com</a>
            - Todos os direitos reservados
          </div>
          
          <div class="flex items-center gap-6">
            <a href="#" class="text-gray-400 text-sm hover:text-[#47c5ff] transition-all duration-300">Política de Privacidade</a>
            <a href="#" class="text-gray-400 text-sm hover:text-[#47c5ff] transition-all duration-300">Termos de Uso</a>
          </div>
          
          <!-- Back to top button -->
          <a href="#top" class="back-to-top w-10 h-10 rounded-full bg-gradient-to-r from-[#47c5ff] to-[#0098df] flex items-center justify-center text-white hover:shadow-lg hover:shadow-[#47c5ff]/20 transition-all duration-300 transform hover:-translate-y-1">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7" />
            </svg>
          </a>
        </div>
      </div>
    </footer>
  </template>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
  
  .footer-section {
    font-family: 'Inter', sans-serif;
    background-color: #0a0c14;
    border-top: 1px solid #ffffff10;
  }
  
  .social-icon-link:hover img {
    transform: scale(1.2);
    transition: transform 0.3s ease;
  }
  
  .back-to-top {
    box-shadow: 0 0 15px rgba(71, 197, 255, 0.3);
  }

  @media (max-width: 768px) {
    .footer-main {
      padding-top: 3rem;
      padding-bottom: 5rem;
    }
  }
  </style>
  
  <script setup>
  
  import { onMounted } from 'vue';
  
  onMounted(() => {
    // Smooth scroll for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        
        const targetId = this.getAttribute('href');
        if (targetId === '#top') {
          window.scrollTo({
            top: 0,
            behavior: 'smooth'
          });
        } else {
          const target = document.querySelector(targetId);
          if (target) {
            target.scrollIntoView({
              behavior: 'smooth'
            });
          }
        }
      });
    });
  });
  </script>
  