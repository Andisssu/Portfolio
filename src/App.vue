<script setup>
import MeshBackground from './components/MeshBackground.vue';
import Header from './components/Header.vue';
import Sobre from './components/Sobre.vue';
import Habilidades from './components/Habilidades.vue';
import Experiencia from './components/Experiencia.vue';
import Projetos from './components/Projetos.vue';
import Contato from './components/Contato.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <div id="app">

    <MeshBackground />
    <Header />

    <div class="corpo">
      <Sobre />
      <Habilidades />
      <Experiencia />
      <Projetos />
      <Contato />
    </div>

    <Footer />

  </div>
</template>

<style scoped></style>
