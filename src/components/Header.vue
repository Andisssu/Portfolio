<template>
  <div class="header h-screen w-full" id="perfil">

    <!-- Mobile menu -->
    <div class="mobile-menu-container fixed top-0 right-0 pt-3 h-screen shadow-lg sm:hidden z-[200]">
      <!-- Checkbox controller (hidden) -->
      <input type="checkbox" id="burger" class="hidden" v-model="isMenuOpen" />

      <!-- hamburguer button -->
      <label
        class="burger-button flex flex-col justify-center items-center w-12 h-12 rounded-full cursor-pointer z-50 transition-all duration-300"
        :class="{ 'is-active': isMenuOpen }" for="burger">
        <span class="burger-line transition-all duration-300 ease-in-out"></span>
        <span class="burger-line transition-all duration-300 ease-in-out"></span>
        <span class="burger-line transition-all duration-300 ease-in-out"></span>
      </label>

      <!-- Overlay background -->
      <div class="menu-overlay fixed inset-0 bg-[#0a0c14] transition-all duration-500 backdrop-blur-md z-40"
        :class="{ 'opacity-90': isMenuOpen, 'opacity-0 pointer-events-none': !isMenuOpen }" @click="isMenuOpen = false">
      </div>

      <!-- Menu -->
      <div
        class="menu-panel fixed inset-y-0 right-0 w-64 sm:w-80 bg-gradient-to-br from-[#121a29] to-[#162339] shadow-xl z-40 transition-all duration-500 ease-in-out transform border-l border-[#ffffff15]"
        :class="{ 'translate-x-0': isMenuOpen, 'translate-x-full': !isMenuOpen }">
        <div class="menu-content flex flex-col h-full p-8">
          <!-- Logo/Branding no topo do menu -->
          <div class="menu-header mb-12 pt-4">
            <div class="flex items-center gap-3">
              <div
                class="w-10 h-10 rounded-full bg-gradient-to-br from-[#47c5ff] to-[#0098df] flex items-center justify-center text-white font-bold text-lg">
                AD
              </div>
              <h3 class="text-xl font-bold text-white">Anderson Dantas</h3>
            </div>
          </div>

          <!-- Lista de navegação -->
          <nav class="menu-nav flex-grow">
            <ul class="space-y-1">
              <li v-for="(item, index) in menuItemsmobi" :key="index" :style="{ transitionDelay: `${item.delay}ms` }"
                class="menu-item">
                <a :href="item.href"
                  class="menu-link flex items-center gap-3 px-4 py-3 rounded-lg text-gray-300 hover:text-white transition-all duration-300 group"
                  :class="{ 'active-link': item.active }" @click="isMenuOpen = false">
                  <div
                    class="w-8 h-8 rounded-full bg-[#ffffff10] flex items-center justify-center group-hover:bg-[#47c5ff20] transition-all duration-300">
                    <component :is="item.icon" class="w-4 h-4 text-[#47c5ff]" />
                  </div>
                  <span>{{ item.label }}</span>
                </a>
              </li>
            </ul>
          </nav>

          <!-- Footer do menu -->
          <div class="menu-footer pt-6 border-t border-[#ffffff15]">
            <div class="flex justify-center space-x-4">
              <a href="https://github.com/Andisssu" target="_blank" rel="noopener noreferrer" class="social-icon-link">
                <div
                  class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/github.png" alt="GitHub" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="https://www.linkedin.com/in/andersondantass/" target="_blank" rel="noopener noreferrer"
                class="social-icon-link">
                <div
                  class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/linkedin.png" alt="LinkedIn" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="https://mail.google.com/mail/?view=cm&fs=1&to=netodantas3@gmail.com" target="_blank"
                rel="noopener noreferrer" class="social-icon-link">
                <div
                  class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/gmail.png" alt="Email" class="w-5 h-5 object-contain" />
                </div>
              </a>
              <a href="https://wa.me/5568992192977" target="_blank" rel="noopener noreferrer" class="social-icon-link">
                <div
                  class="w-10 h-10 rounded-full bg-[#121a29] border border-[#ffffff15] hover:border-[#47c5ff40] flex items-center justify-center transition-all duration-300 hover:bg-[#47c5ff20]">
                  <img src="@/assets/img/whatsapp.png" alt="Email" class="w-5 h-5 object-contain" />
                </div>
              </a>
            </div>
            <p class="text-center text-xs text-gray-500 mt-4">© 2025 Anderson Dantas</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Menu Desktop -->
    <div class="flex items-center justify-between p-4 text-white top-0 left-0 w-full z-100 fixed" id="navbar">
      <div class="flex items-center gap-2">
        <img src="@/assets/img/dev.png" alt="devicon" class="w-10 h-10" />
        <h1 class="text-4xl font-bold">Anderson</h1>
      </div>

      <nav class="desktop-nav fixed top-0 w-full z-40 transition-all duration-300"
        :class="{ 'nav-scrolled': isScrolled }">
        <div class="container mx-auto px-6">
          <div class="flex items-center justify-end h-20">

            <!-- Navigation Links - Visible only on md screens and up -->
            <div class="hidden md:block">
              <ul class="flex space-x-1">
                <li v-for="(item, index) in navItems" :key="index">
                  <a :href="item.href"
                    class="nav-link relative px-4 py-2 text-gray-300 hover:text-white transition-colors duration-300 rounded-md flex items-center"
                    :class="{ 'active': item.active }" @click.prevent="scrollToSection(item.href)">
                    <span>{{ item.label }}</span>
                  </a>
                </li>
              </ul>
            </div>

            <!-- Mobile Menu Button - Only visible on small screens -->
            <div class="md:hidden">

              <!-- <depois eutiro la de cima e coloco aqui /> -->
            </div>
          </div>
        </div>

      </nav>
    </div>

    <section class="flex flex-col md:flex-row items-center justify-between h-screen p-24">

      <!-- Perfil Information -->
      <div class="text-center md:text-left">
        <h1 class="text-7xl font-bold text-white">Anderson Dantas</h1>
        <h2 class="text-3xl text-gray-400 mt-2" id="article">Desenvolvedor Front-End / Full Stack</h2>

        <div class="flex justify-center md:justify-start space-x-6 mt-6">
          <a href="https://www.linkedin.com/in/andersondantass/" target="_blank" rel="noopener noreferrer">
            <button
              class="flex items-center gap-3 cursor-pointer text-white font-semibold bg-[#0077B5] px-7 py-3 rounded-full transition-transform duration-200 hover:scale-105 hover:bg-[#005983]">
              <svg xmlns="http://www.w3.org/2000/svg" height="24" width="24" viewBox="0 0 48 48">
                <path fill="#ffffff"
                  d="M42,37c0,2.762-2.238,5-5,5H11c-2.761,0-5-2.238-5-5V11c0-2.762,2.239-5,5-5h26c2.762,0,5,2.238,5,5V37z" />
                <path fill="#0077B5"
                  d="M12 19H17V36H12zM14.485 17h-.028C12.965 17 12 15.888 12 14.499 12 13.08 12.995 12 14.514 12c1.521 0 2.458 1.08 2.486 2.499C17 15.887 16.035 17 14.485 17zM36 36h-5v-9.099c0-2.198-1.225-3.698-3.192-3.698-1.501 0-2.313 1.012-2.707 1.99C24.957 25.543 25 26.511 25 27v9h-5V19h5v2.616C25.721 20.5 26.85 19 29.738 19c3.578 0 6.261 2.25 6.261 7.274L36 36 36 36z" />
              </svg>
              LinkedIn
            </button>
          </a>
          <a href="https://github.com/Andisssu" target="_blank" rel="noopener noreferrer">
            <button
              class="flex gap-3 cursor-pointer text-white font-semibold bg-gradient-to-r from-gray-800 to-black px-7 py-3 rounded-full border border-gray-600 hover:scale-105 duration-200 hover:text-gray-500 hover:border-gray-800 hover:from-black hover:to-gray-900">
              <svg viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg">
                <path fill="#FFFFFF"
                  d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z">
                </path>
              </svg>
              Github
            </button>
          </a>
        </div>
      </div>

      <!-- Perfil Image -->
      <figure class="mb-8 md:mb-0 md:mr-12">
        <img src="@/assets/img/perfil.png" alt="Foto de Anderson Dantas" class="w-lg h-lg object-cover">
      </figure>
    </section>
  </div>
</template>

<style scoped>
@property --＠color-1 {
  syntax: "<color>";
  inherits: false;
  initial-value: hsl(278, 78%, 36%)
}

@property --＠color-2 {
  syntax: "<color>";
  inherits: false;
  initial-value: hsl(204 100% 59%)
}

@keyframes gradient-change {
  to {
    --＠color-1: hsl(204 100% 59%);
    --＠color-2: hsl(98 100% 68%);
  }
}

#article {
  animation: gradient-change 2s linear infinite alternate;
  background: linear-gradient(to right in oklch, var(--＠color-1), var(--＠color-2));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}

#navbar {
  background: rgb(0 0 0 / 10%);
  box-shadow: 0 8px 32px 0 rgb(0 0 0 / 37%);
  backdrop-filter: blur(6.5px);
  -webkit-backdrop-filter: blur(6.5px);
  border-radius: 0 0 10px 10px;
}

.desktop-nav {
  background-color: rgba(10, 12, 20, 0);
  backdrop-filter: blur(0px);
  transition: all 0.3s ease;
}

.nav-link {
  position: relative;
  overflow: hidden;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background: linear-gradient(to right, #47c5ff, #0098df);
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover::after {
  width: 80%;
}

.nav-link.active {
  color: white;
  font-weight: 500;
}

.nav-link.active::after {
  width: 80%;
}

.burger-line {
  width: 22px;
  height: 2px;
  background-color: #fff;
  margin: 3px 0;
  border-radius: 2px;
  transform-origin: center;
}

/* Animação do botão hamburguer para X */
.burger-button.is-active {
  background: rgba(71, 197, 255, 0.2);
  border-color: rgba(71, 197, 255, 0.4);
}

.burger-button.is-active .burger-line:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
  width: 22px;
}

.burger-button.is-active .burger-line:nth-child(2) {
  opacity: 0;
  transform: translateX(-10px);
}

.burger-button.is-active .burger-line:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
  width: 22px;
}

/* Estilo dos itens do menu */
.menu-item {
  opacity: 0;
  transform: translateX(20px);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.menu-panel[class*="translate-x-0"] .menu-item {
  opacity: 1;
  transform: translateX(0);
}

/* Link ativo */
.active-link {
  background: rgba(71, 197, 255, 0.1);
  color: white;
  font-weight: 500;
}

.active-link .w-8 {
  background: rgba(71, 197, 255, 0.2);
}

/* Adicione uma animação para o botão hambúrguer */
.burger-button {
  transition: background 0.3s ease, transform 0.3s ease;
}

.burger-button:hover {
  transform: scale(1.1);
  background: rgba(71, 197, 255, 0.3);
}

/* Adicione um efeito de escala para os ícones do menu */
.menu-link .w-8 {
  transition: transform 0.3s ease, background 0.3s ease;
}

.menu-link:hover .w-8 {
  transform: scale(1.2);
  background: rgba(71, 197, 255, 0.3);
}
</style>

<script setup>
import { ref, onMounted, watch, computed } from 'vue'

const navItems = [
  { label: 'Perfil', href: '#perfil', active: false },
  { label: 'Sobre', href: '#sobre', active: false },
  { label: 'Habilidades', href: '#habilidades', active: false },
  { label: 'Expêriencia', href: '#experiencia', active: false },
  { label: 'Projetos', href: '#projetos', active: false },
  { label: 'Contato', href: '#contato', active: false }
];

// Track scroll position for navbar background
const isScrolled = ref(false);
const activeSection = ref('#perfil');
const activeElement = ref(null);

// Scroll to section function
const scrollToSection = (sectionId) => {
  const element = document.querySelector(sectionId);
  if (element) {
    window.scrollTo({
      top: element.offsetTop - 80,
      behavior: 'smooth'
    });

    // Update active section
    activeSection.value = sectionId;
    updateActiveNavItem(sectionId);
  }
};

// Update active nav item
const updateActiveNavItem = (sectionId) => {
  navItems.forEach(item => {
    item.active = item.href === sectionId;
    if (item.active) {
      // Find the DOM element for this nav item
      setTimeout(() => {
        activeElement.value = document.querySelector(`.nav-link[href="${sectionId}"]`);
      }, 0);
    }
  });
};

// Check which section is in view
const checkActiveSection = () => {
  const sections = navItems.map(item => item.href);

  // Find the section that is currently in view
  for (const section of sections) {
    const element = document.querySelector(section);
    if (element) {
      const rect = element.getBoundingClientRect();
      const windowHeight = window.innerHeight;

      // Check if the section is in view
      if (rect.top <= windowHeight * 0.5 && rect.bottom >= windowHeight * 0.5) {
        if (activeSection.value !== section) {
          activeSection.value = section;
          updateActiveNavItem(section);
        }
        break;
      }
    }
  }
};

// Watch for changes in active section
watch(activeSection, (newSection) => {
  updateActiveNavItem(newSection);
});

const isMenuOpen = ref(false);

const menuItemsmobi = [
  { label: 'Perfil', href: '#perfil', active: true, icon: 'UserIcon', delay: 0 },
  { label: 'Sobre', href: '#sobre', active: false, icon: 'InfoIcon', delay: 50 },
  { label: 'Habilidades', href: '#habilidades', active: false, icon: 'CodeIcon', delay: 100 },
  { label: 'Expêriencia', href: '#experiencia', active: false, icon: 'BriefcaseIcon', delay: 150 },
  { label: 'Projetos', href: '#projetos', active: false, icon: 'FolderIcon', delay: 200 },
  { label: 'Contato', href: '#contato', active: false, icon: 'MailIcon', delay: 250 }
];

onMounted(() => {

  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape' && isMenuOpen.value) {
      isMenuOpen.value = false;
    }
  });

  // Disable scrolling when menu is open
  watch(isMenuOpen, (newVal) => {
    if (newVal) {
      document.body.style.overflow = 'hidden';
    } else {
      document.body.style.overflow = '';
    }
  });

  // Initialize active element
  setTimeout(() => {
    activeElement.value = document.querySelector('.nav-link.active');
  }, 100);

  // Add scroll event listener
  window.addEventListener('scroll', () => {
    // Update navbar background
    isScrolled.value = window.scrollY > 50;

    // Check which section is active
    checkActiveSection();
  });
  checkActiveSection();

})
</script>