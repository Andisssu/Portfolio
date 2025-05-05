<template>
    <section class="flex items-center justify-center min-h-[70vh] bg-[#0e0b1f] px-4" id="corpo">
        <div class="p-8 max-w-3xl w-full text-white">
            <h2 class="text-4xl font-bold text mb-6 border-b border-[#47c5ff] pb-2">Sobre mim</h2>
            <p class="text-lg text-gray-300 leading-relaxed" id="split">
                Sou um desenvolvedor com experiência prática em desenvolvimento Front-End, utilizando tecnologias como
                <span class="text">Django</span>,
                <span class="text">Angular</span>,
                <span class="text">Vue.js</span>,
                <span class="text">Electron</span> e outros.
                <span id="spacer"></span>
                Também possuo capacitação em desenvolvimento <span class="text">Full Stack</span>.
                <span id="spacer"></span>
                Além da programação, tenho habilidades em ferramentas como 
                <span class="text">PowerPoint</span>,
                <span class="text">Photoshop</span> e <span class="text">Figma</span>,
                refletindo minha afinidade com tecnologia e design.
                <span id="spacer"></span>
                Sou graduado em <span class="text">Sistemas de Informação</span> pela
                <span class="text">Universidade Federal do Acre (UFAC)</span>, 
                onde atuei no desenvolvimento de sistemas para a instituição.
            </p>
        </div>
    </section>
</template>

<style scoped>
.text {
    color: #47c5ff;
    font-weight: bold;
}

#spacer{
    display: block;
    margin-bottom: 20px; /* Ajuste conforme necessário */
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
                        trigger: "#corpo",
                        start: "top 70%",
                        end: "bottom 70%",
                        scrub: false,
                    }
                });
            }
        });
    });
});
</script>