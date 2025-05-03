<template>
    <div class="corpo">
        <div class="min-h-[30vh]">
            <div class="flex flex-col items-center justify-center py-10 px-4 bg-[#0e0b1f]">
                <h2 class="text-center text-3xl font-bold text-[#47c5ff] mb-5">Contato</h2>
                <div class="barrax"></div>
            </div>
            <div class="contato py-10">
                <img src="@/assets/img/whatsapp.png" alt="whatsapp" class="w-13 h-13 mb-4" />
                <img src="@/assets/img/gmail.png" alt="email" class="w-13 h-13 mb-4" />
                <img src="@/assets/img/linkedin.png" alt="linkedin" class="w-13 h-13 mb-4" />
                <img src="@/assets/img/github.png" alt="github" class="w-13 h-13 mb-4" />
            </div>
        </div>
    </div>
    <!-- footer -->
    <div class="flex flex-row" id="footer">

        <span>© 2025
            <a href="" class="text">andersondev.com</a>
            Todos os direitos reservados
        </span>

        <div class="flex items-center gap-2">
            <!-- <img src="@/assets/img/dev.png" alt="devicon" class="w-10 h-10" /> -->
            <h1 class="text-4xl font-bold text-white">Anderson Dantas</h1>
          </div>
    </div>
</template>

<style scoped>
.barrax {
    height: 2px;
    width: 380px;
    background: linear-gradient(to left, #00000000, #47c5ff 50%, #00000000);
}

.contato {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    gap: 20px;
}

.text {
    color: #47c5ff;
    font-weight: bold;
}

#footer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 20px 50px;
    color: white;
    background: linear-gradient(#2121218c, #212121a4) padding-box,
    linear-gradient(145deg, transparent 35%, #47c5ff, #40c9ff) border-box;
}
</style>