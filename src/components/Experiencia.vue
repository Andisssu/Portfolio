<template>
    <div class="corpo text-white py-10 px-4 bg-[#0e0b1f] min-h-[30vh]">
        <div class="flex flex-col items-center justify-center py-10 px-4 bg-[#0e0b1f]">
            <h2 class="text-center text-3xl font-bold text-[#47c5ff] mb-5">Experiencia</h2>
            <div class="barrax"></div>
        </div>

        <div class="flex flex-row items-start justify-center gap-10">

            <div class="barra"></div>
            
            <!-- Botões laterais -->
            <div class="flex flex-col gap-4">
                <button v-for="option in options" :key="option.id" @click="selected = option.id" :class="[
                    'flex items-center px-4 py-3 rounded-md border hover:scale-[1.03] transition-all',
                    selected === option.id ? 'bg-[#0098df] border-[#47c5ff] text-white shadow-md' : 'bg-transparent border-white text-white'
                ]">
                <img :src="option.icon" alt="Ícone" class="w-6 h-6 mr-2 rounded-sm" />
                <span>{{ option.label }}</span>
                </button>
            </div>

            <!-- Conteúdo do card -->
            <div class="card rounded-xl p-6 max-w-3xl w-full bg-[#121212] transition-all">
                <h3 class="text-xl font-bold text-[#47c5ff] mb-1">
                    {{ content[selected].title }}
                </h3>
                <p class="text-sm text-gray-300 mb-4 font-semibold">
                    {{ content[selected].period }}
                </p>
                <ul class="list-none space-y-2">
                    <li v-for="(item, index) in content[selected].details" :key="index" class="flex items-start gap-2">
                        <span class="text-[#47c5ff] mt-1">⟡</span>
                        <span>{{ item }}</span>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import ufacImg from '@/assets/img/ufac.png'
import freelancerImg from '@/assets/img/freelancer.png'

const selected = ref('UFAC')

const options = [
    { id: 'UFAC', label: 'UFAC', icon: ufacImg },
    { id: 'freelancer', label: 'Freelancer', icon: freelancerImg },
]

const content = {
    UFAC: {
        title: 'Sistema de Grenciamento do Hospital Universitario - Full Stack | NTI - UFAC',
        period: 'Março 2024 a Março 2025',
        details: [
            'Desenvolvimento de Interfaces e criação de paginas com Django;',
            'Desenvolvimento e ajustes no backend com Framework Django;',
            'Criação e Ajustes no banco de dados;',
            'Implementação de funções de autenticação e autorização, impressão de pdf, restrição de acesso por usuario entre outros...;',
            'Tecnologias: JavaScript, HTML, CSS, Django, SQLite, Figma;',
        ]
    },
    freelancer: {
        title: 'Suporte no Desenvolvimento | Freelancer',
        period: '2024',
        details: [
            'Suporte no teste de funcionalidades dos app;',
            'Criação de paginas web e elementos das paginas;',
            'Criação de Arte para produtos',
            'tecnologias: PhotoShop, Figma, WordPress;',
        ]
    }
}
</script>

<style scoped>
/* Fonte opcional que remete ao visual da imagem */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

.corpo {
    font-family: 'Inter', sans-serif;
}

.card {

    background: linear-gradient(#212121, #212121d3) padding-box,
        linear-gradient(145deg, transparent 35%, #47c5ff, #40c9ff) border-box;
    border: 2px solid transparent;
}

.barra {
    height: 38vh;
    width: 2px;
    background: linear-gradient(to bottom, #00000000, #47c5ff 50%, #00000000);
}

</style>