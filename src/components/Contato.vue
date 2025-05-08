<template>
  <section
    class="contact-section text-white py-16 px-4 relative overflow-hidden min-h-screen flex flex-col items-center justify-center" id="contato">
    <!-- Background elements -->
    <div class="absolute inset-0 z-0">
      <div class="absolute top-[10%] right-[10%] w-64 h-64 rounded-full bg-[#47c5ff] opacity-5 blur-[100px]"></div>
      <div class="absolute bottom-[20%] left-[15%] w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[80px]"></div>

      <!-- Grid pattern -->
      <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
    </div>

    <!-- Section header -->
    <div class="relative z-10 flex flex-col items-center justify-center mb-16 w-full">
      <h2
        class="text-center text-4xl font-bold bg-gradient-to-r from-[#47c5ff] to-[#0098df] bg-clip-text text-transparent mb-3">
        Contato
      </h2>
      <div class="w-20 h-1 bg-gradient-to-r from-[#47c5ff] to-[#0098df] rounded-full mb-4"></div>
      <p class="text-center text-gray-300 max-w-md">
        Vamos trabalhar juntos? Entre em contato através de um dos canais abaixo.
      </p>
    </div>

    <!-- Contact content -->
    <div class="relative z-10 w-full max-w-5xl mx-auto">
      <div class="grid md:grid-cols-2 gap-10 items-center">
        <!-- Contact form -->
        <div class="contact-form-container">

          <div
            class="bg-gradient-to-br from-[#121a29] to-[#162339] p-8 rounded-2xl border border-[#ffffff15] shadow-xl relative overflow-hidden">
            <!-- Form background accent -->
            <div
              class="absolute inset-0 z-10 rounded-2xl backdrop-blur-[6px] bg-white/20 border border-white/20 flex items-center justify-center flex-col text-white text-center pointer-events-block">
              <img src="@/assets/img/perigo.png" alt="Em breve" class="w-12 h-12 mb-4 opacity-90" />
              <p class="text-lg font-semibold">Formulário temporariamente indisponível</p>
              <p class="text-sm opacity-75">Disponível em breve</p>
            </div>

            <div class="absolute -top-24 -right-24 w-48 h-48 rounded-full bg-[#47c5ff] opacity-5 blur-[50px]"></div>

            <h3 class="text-xl font-semibold mb-6 text-white">Envie uma mensagem</h3>

            <form class="space-y-5">
              <div class="space-y-2">
                <label for="name" class="text-sm text-gray-300 block">Nome</label>
                <div class="relative">
                  <input type="text" id="name"
                    class="w-full bg-[#0a0c14] border border-[#ffffff20] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#47c5ff] transition-all duration-300"
                    placeholder="Seu nome" />
                </div>
              </div>

              <div class="space-y-2">
                <label for="email" class="text-sm text-gray-300 block">Email</label>
                <div class="relative">
                  <input type="email" id="email"
                    class="w-full bg-[#0a0c14] border border-[#ffffff20] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#47c5ff] transition-all duration-300"
                    placeholder="seu@email.com" />
                </div>
              </div>

              <div class="space-y-2">
                <label for="message" class="text-sm text-gray-300 block">Mensagem</label>
                <div class="relative">
                  <textarea id="message" rows="4"
                    class="w-full bg-[#0a0c14] border border-[#ffffff20] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#47c5ff] transition-all duration-300"
                    placeholder="Sua mensagem aqui..."></textarea>
                </div>
              </div>

              <button type="submit"
                class="w-full bg-gradient-to-r from-[#47c5ff] to-[#0098df] text-white font-medium py-3 px-6 rounded-lg hover:shadow-lg hover:shadow-[#47c5ff]/20 transition-all duration-300 transform hover:-translate-y-1">
                Enviar mensagem
              </button>
            </form>
          </div>
        </div>

        <!-- Contact info and social media -->
        <div class="contact-info-container flex flex-col gap-8 w-full min-w-[600px] mx-auto px-4">
          <!-- Contact cards -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- Email card -->
            <div class="contact-card group ">
              <div
                class="bg-gradient-to-br from-[#121a29] to-[#162339] p-5 rounded-xl border border-[#ffffff15] hover:border-[#47c5ff40] transition-all duration-300 flex items-center gap-4 group-hover:shadow-lg">
                <div
                  class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center group-hover:bg-[#47c5ff25] transition-all duration-300">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                </div>
                <div>
                  <h4 class="text-sm text-gray-400 mb-1">Email</h4>
                  <a href="mailto:seu@email.com"
                    class="text-white hover:text-[#47c5ff] transition-all duration-300">netodantas3@gmail.com</a>
                </div>
              </div>
            </div>

            <!-- Phone card -->
            <div class="contact-card group">
              <div
                class="bg-gradient-to-br from-[#121a29] to-[#162339] p-5 rounded-xl border border-[#ffffff15] hover:border-[#47c5ff40] transition-all duration-300 flex items-center gap-4 group-hover:shadow-lg">
                <div
                  class="w-12 h-12 rounded-full bg-[#47c5ff15] flex items-center justify-center group-hover:bg-[#47c5ff25] transition-all duration-300">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#47c5ff]" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <div>
                  <h4 class="text-sm text-gray-400 mb-1">Telefone</h4>
                  <a href="tel:+5500000000000" class="text-white hover:text-[#47c5ff] transition-all duration-300">(68)
                    99219-2977</a>
                </div>
              </div>
            </div>
          </div>

          <!-- Social media links -->
          <div class="social-links-container">
            <h4 class="text-lg font-medium mb-5 text-white">Redes Sociais</h4>
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-6 ">
              <!-- WhatsApp -->
              <a href="#" class="social-link group flex flex-col items-center">
                <div
                  class="w-14 h-14 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff15] group-hover:border-[#47c5ff40] flex items-center justify-center mb-2 transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-lg group-hover:shadow-[#47c5ff]/10">
                  <div
                    class="w-10 h-10 rounded-full bg-[#47c5ff10] flex items-center justify-center group-hover:bg-[#47c5ff20] transition-all duration-300">
                    <img src="@/assets/img/whatsapp.png" alt="WhatsApp" class="w-6 h-6 object-contain" />
                  </div>
                </div>
                <span class="text-sm text-gray-400 group-hover:text-white transition-all duration-300">WhatsApp</span>
              </a>

              <!-- Gmail -->
              <a href="#" class="social-link group flex flex-col items-center">
                <div
                  class="w-14 h-14 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff15] group-hover:border-[#47c5ff40] flex items-center justify-center mb-2 transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-lg group-hover:shadow-[#47c5ff]/10">
                  <div
                    class="w-10 h-10 rounded-full bg-[#47c5ff10] flex items-center justify-center group-hover:bg-[#47c5ff20] transition-all duration-300">
                    <img src="@/assets/img/gmail.png" alt="Gmail" class="w-6 h-6 object-contain" />
                  </div>
                </div>
                <span class="text-sm text-gray-400 group-hover:text-white transition-all duration-300">Gmail</span>
              </a>

              <!-- LinkedIn -->
              <a href="#" class="social-link group flex flex-col items-center">
                <div
                  class="w-14 h-14 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff15] group-hover:border-[#47c5ff40] flex items-center justify-center mb-2 transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-lg group-hover:shadow-[#47c5ff]/10">
                  <div
                    class="w-10 h-10 rounded-full bg-[#47c5ff10] flex items-center justify-center group-hover:bg-[#47c5ff20] transition-all duration-300">
                    <img src="@/assets/img/linkedin.png" alt="LinkedIn" class="w-6 h-6 object-contain" />
                  </div>
                </div>
                <span class="text-sm text-gray-400 group-hover:text-white transition-all duration-300">LinkedIn</span>
              </a>

              <!-- GitHub -->
              <a href="#" class="social-link group flex flex-col items-center">
                <div
                  class="w-14 h-14 rounded-full bg-gradient-to-br from-[#121a29] to-[#162339] border border-[#ffffff15] group-hover:border-[#47c5ff40] flex items-center justify-center mb-2 transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-lg group-hover:shadow-[#47c5ff]/10">
                  <div
                    class="w-10 h-10 rounded-full bg-[#47c5ff10] flex items-center justify-center group-hover:bg-[#47c5ff20] transition-all duration-300">
                    <img src="@/assets/img/github.png" alt="GitHub" class="w-6 h-6 object-contain" />
                  </div>
                </div>
                <span class="text-sm text-gray-400 group-hover:text-white transition-all duration-300">GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.contact-section {
  font-family: 'Inter', sans-serif;
  background-color: #0a0c14;
}

/* Grid pattern background */
.bg-grid-pattern {
  background-image:
    linear-gradient(to right, #ffffff05 1px, transparent 1px),
    linear-gradient(to bottom, #ffffff05 1px, transparent 1px);
  background-size: 20px 20px;
}

/* Input focus effect */
input:focus,
textarea:focus {
  box-shadow: 0 0 0 2px rgba(71, 197, 255, 0.2);
}

/* Social link hover animation */
.social-link:hover img {
  animation: pulse 1s infinite alternate;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }

  100% {
    transform: scale(1.15);
  }
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .contact-form-container {
    order: 2;
  }

  .contact-info-container {
    order: 1;
    margin-bottom: 2rem;
  }
}

@media (max-width: 640px) {
  .contact-info-container {
    min-width: 80%; /* Ajuste conforme necessário */
  }
}
</style>

<script setup>
// You can add any necessary script logic here
// For example, form submission handling, validation, etc.
</script>