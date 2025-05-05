<template>
  <div class="header h-screen w-full">

    <div class="flex items-center justify-between p-4 text-white top-0 left-0 w-full z-100 fixed" id="navbar">
      <div class="flex items-center gap-2">
        <img src="@/assets/img/dev.png" alt="devicon" class="w-10 h-10" />
        <h1 class="text-4xl font-bold">Anderson</h1>
      </div>

      <!-- botão hamburguer + menu -->
      <div class="menu-container">
        <!-- Checkbox controlador -->
        <input type="checkbox" id="burger" class="hidden" />

        <!-- Botão hamburguer -->
        <label class="burger" for="burger">
          <span></span>
          <span></span>
          <span></span>
        </label>

        <!-- Lista de navegação -->
        <div class="menu-list">
          <ul>
            <li><a href="#">Perfil</a></li>
            <li><a href="#">Sobre</a></li>
            <li><a href="#">Habilidades</a></li>
            <li><a href="#">Trabalhos</a></li>
            <li><a href="#">Projetos</a></li>
            <li><a href="#">Contato</a></li>
          </ul>
        </div>
      </div>



      <!-- Menu de navegação -->
      <nav class="relative hidden md:block">
        <ul ref="menu" class="flex space-x-4 px-12 py-2 rounded-lg text-xl relative">
          <li v-for="(item, index) in menuItems" :key="index" @mouseenter="moveIndicator(index)" class="relative">
            <a href="#" class="hover:text-white">{{ item }}</a>
          </li>
        </ul>
        <aside id="indicator" class="absolute bottom-0 h-1 bg-gray-400 rounded transition-all duration-300"
          :style="indicatorStyle"></aside>
      </nav>
    </div>

    <section class="flex flex-col md:flex-row items-center justify-between h-screen p-24">

      <!-- Informações de Perfil -->
      <div class="text-center md:text-left">
        <h1 class="text-7xl font-bold text-white">Anderson Dantas</h1>
        <h2 class="text-3xl text-gray-400 mt-2" id="article">Desenvolvedor Front-End / Full Stack</h2>

        <div class="flex justify-center md:justify-start space-x-6 mt-6">
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

          <button
            class="flex gap-3 cursor-pointer text-white font-semibold bg-gradient-to-r from-gray-800 to-black px-7 py-3 rounded-full border border-gray-600 hover:scale-105 duration-200 hover:text-gray-500 hover:border-gray-800 hover:from-black hover:to-gray-900">
            <svg viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg">
              <path fill="#FFFFFF"
                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z">
              </path>
            </svg>
            Github
          </button>
        </div>
      </div>

      <!-- Imagem de Perfil -->
      <figure class="mb-8 md:mb-0 md:mr-12">
        <img src="@/assets/img/perfil.png" alt="Foto de Anderson Dantas" class="w-lg h-lg object-cover">
      </figure>
    </section>
  </div>
</template>

<style scoped>
/* texto gradiente animado*/
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

/* botão */
.burger {
  position: relative;
  width: 40px;
  height: 30px;
  background: transparent;
  cursor: pointer;
  display: block;
}

.burger span {
  display: block;
  position: absolute;
  height: 4px;
  width: 100%;
  background: rgb(255, 255, 255);
  border-radius: 9px;
  opacity: 1;
  left: 0;
  transform: rotate(0deg);
  transition: .25s ease-in-out;
}

.burger span:nth-of-type(1) {
  top: 0px;
  transform-origin: left center;
}

.burger span:nth-of-type(2) {
  top: 50%;
  transform: translateY(-50%);
  transform-origin: left center;
}

.burger span:nth-of-type(3) {
  top: 100%;
  transform-origin: left center;
  transform: translateY(-100%);
}

/* animação do botão quando checkbox está marcado */
#burger:checked+.burger span:nth-of-type(1) {
  transform: rotate(45deg);
  top: 0px;
  left: 5px;
}

#burger:checked+.burger span:nth-of-type(2) {
  width: 0%;
  opacity: 0;
}

#burger:checked+.burger span:nth-of-type(3) {
  transform: rotate(-45deg);
  top: 28px;
  left: 5px;
}

.menu-container {
  position: relative;
}

/* menu oculto por padrão */
.menu-list {
  display: none;
  position: absolute;
  top: 100%;
  /* logo abaixo do botão */
  right: 0;
  background: #1a1a1a;
  color: white;
  padding: 1rem;
  border-radius: 8px;
  z-index: 1000;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

/* mostra menu quando checkbox está checado */
#burger:checked~.menu-list {
  display: block;
}

/* esconde menu e botão em telas maiores */
@media (min-width: 768px) {

  .burger,
  #burger,
  .menu-list {
    display: none !important;
  }
}
</style>

<script setup>
import { ref, reactive, onMounted, nextTick } from 'vue'

const menuItems = ['Perfil', 'Sobre', 'Habilidades', 'Trabalhos', 'Projetos', 'Contato']
const indicatorStyle = reactive({
  width: '0px',
  left: '0px'
})
const menu = ref(null)

const moveIndicator = async (index) => {
  await nextTick()
  const liElements = menu.value.querySelectorAll('li')
  const target = liElements[index]
  indicatorStyle.width = `${target.offsetWidth}px`
  indicatorStyle.left = `${target.offsetLeft}px`
}

onMounted(() => {
  moveIndicator(0)
})
</script>