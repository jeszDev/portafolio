<template>
  <section class="w-full">
    <div class="flex justify-center">
      <TitleSection title="Contáctame" />
    </div>

    <div class="flex justify-center">
      <div
        class="w-full max-w-6xl mx-auto flex justify-center flex-col gap-8 px-4 sm:px-6 lg:px-8 py-12"
      >
        <!-- <div class="flex items-center justify-center mb-4">
        <TitleSection title="Contacto" />
      </div> -->

        <div
          class="border border-slate-800 bg-slate-950/60 backdrop-blur-md rounded-xl shadow-[0_0_40px_rgba(0,0,0,0.7)] overflow-hidden relative"
        >
          <div
            class="bg-slate-900/80 border-b border-slate-800 px-4 py-2.5 flex items-center justify-between select-none"
          >
            <div class="flex items-center gap-2">
              <span class="w-2.5 h-2.5 rounded-full bg-red-500/70"></span>
              <span class="w-2.5 h-2.5 rounded-full bg-yellow-500/70"></span>
              <span
                class="w-2.5 h-2.5 rounded-full bg-cyan-500/70 shadow-[0_0_8px_rgba(34,211,238,0.5)]"
              ></span>
              <span class="font-mono text-xs text-slate-500 ml-2 tracking-widest"
                >CONTACT-INTERFACE.EXE</span
              >
            </div>
            <span
              class="font-mono text-[10px] text-cyan-500/50 uppercase tracking-wider animate-pulse"
            >
              [STATUS: READY_TO_TRANSMIT]
            </span>
          </div>

          <div
            class="grid grid-cols-1 md:grid-cols-2 divide-y md:divide-y-0 md:divide-x divide-slate-800/60"
          >
            <div
              class="p-8 flex flex-col justify-between gap-8 bg-gradient-to-br from-slate-950/20 to-transparent"
            >
              <div>
                <div class="font-mono text-xs text-cyan-500/70 tracking-[0.2em] uppercase mb-1">
                  :: INITIALIZE_SEQUENCE
                </div>
                <h2 class="text-3xl sm:text-4xl font-mono font-bold tracking-tight text-white mb-4">
                  Ponte en contacto<span class="text-cyan-500 animate-pulse">_</span>
                </h2>
                <p class="font-mono text-sm text-slate-400 leading-relaxed max-w-sm">
                  Envía una transmisión cifrada llenando el formulario para iniciar una
                  conversación.
                </p>
              </div>

              <div class="flex flex-col gap-5 font-mono">
                <div class="flex items-start group">
                  <div
                    class="p-2 border border-slate-800 bg-slate-900/40 rounded-lg text-cyan-400 group-hover:border-cyan-500/50 group-hover:text-cyan-300 transition-colors"
                  >
                    <svg
                      fill="none"
                      stroke="currentColor"
                      stroke-width="1.5"
                      viewBox="0 0 24 24"
                      class="w-5 h-5"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"
                      />
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"
                      />
                    </svg>
                  </div>
                  <div class="ml-4">
                    <div class="text-[10px] text-slate-500 tracking-wider uppercase">Ubicación</div>
                    <div class="text-sm text-slate-300 group-hover:text-white transition-colors">
                      Michoacán, México
                    </div>
                  </div>
                </div>

                <!-- <div class="flex items-start group">
              <div
                class="p-2 border border-slate-800 bg-slate-900/40 rounded-lg text-cyan-400 group-hover:border-cyan-500/50 group-hover:text-cyan-300 transition-colors"
              >
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  class="w-5 h-5"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-2.824-1.47-5.112-3.758-6.58-6.58l1.293-.97c.362-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"
                  />
                </svg>
              </div>
              <div class="ml-4">
                <div class="text-[10px] text-slate-500 tracking-wider uppercase">
                  Red de voz Directa
                </div>
                <div class="text-sm text-slate-300 group-hover:text-white transition-colors">
                  +52 443 123 4567
                </div>
              </div>
            </div> -->

                <div class="flex items-start group">
                  <div
                    class="p-2 border border-slate-800 bg-slate-900/40 rounded-lg text-cyan-400 group-hover:border-cyan-500/50 group-hover:text-cyan-300 transition-colors"
                  >
                    <svg
                      fill="none"
                      stroke="currentColor"
                      stroke-width="1.5"
                      viewBox="0 0 24 24"
                      class="w-5 h-5"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
                      />
                    </svg>
                  </div>
                  <div class="ml-4">
                    <div class="text-[10px] text-slate-500 tracking-wider uppercase">
                      Enlace Seguro (Email)
                    </div>
                    <div class="text-sm text-slate-300 group-hover:text-white transition-colors">
                      jjcr.dev@gmail.com
                    </div>
                  </div>
                </div>
              </div>

              <div class="text-[10px] font-mono text-slate-600 border-t border-slate-900 pt-4">
                SECURE_CONNECTION // SHA-256 ENCRYPTED
              </div>
            </div>

            <form
              @submit.prevent="handleSubmit"
              class="p-8 flex flex-col justify-center gap-5 font-mono"
            >
              <div class="flex flex-col gap-1.5 relative group">
                <label
                  for="name"
                  class="text-[10px] text-slate-500 tracking-wider uppercase group-focus-within:text-cyan-400 transition-colors"
                >
                  [01] Nombre del jugador:
                </label>
                <input
                  type="text"
                  name="name"
                  id="name"
                  required
                  placeholder="Ingresa tu identidad o alias"
                  class="w-full bg-slate-950/80 border border-slate-800 focus:border-cyan-500/80 focus:ring-1 focus:ring-cyan-500/30 text-white placeholder:text-slate-600 text-sm px-4 py-3.5 outline-none rounded-lg transition-all"
                />
              </div>

              <div class="flex flex-col gap-1.5 relative group">
                <label
                  for="email"
                  class="text-[10px] text-slate-500 tracking-wider uppercase group-focus-within:text-cyan-400 transition-colors"
                >
                  [02] Contacto del jugador (correo electrónico):
                </label>
                <input
                  type="email"
                  name="email"
                  id="email"
                  required
                  placeholder="tu-correo@servidor.com"
                  class="w-full bg-slate-950/80 border border-slate-800 focus:border-cyan-500/80 focus:ring-1 focus:ring-cyan-500/30 text-white placeholder:text-slate-600 text-sm px-4 py-3.5 outline-none rounded-lg transition-all"
                />
              </div>

              <div class="flex flex-col gap-1.5 relative group">
                <label
                  for="message"
                  class="text-[10px] text-slate-500 tracking-wider uppercase group-focus-within:text-cyan-400 transition-colors"
                >
                  [03] Mensaje del jugador:
                </label>
                <textarea
                  name="message"
                  id="message"
                  rows="4"
                  required
                  placeholder="Escribe tu propuesta, dudas o líneas de transmisión aquí..."
                  class="w-full bg-slate-950/80 border border-slate-800 focus:border-cyan-500/80 focus:ring-1 focus:ring-cyan-500/30 text-white placeholder:text-slate-600 text-sm px-4 py-3.5 outline-none rounded-lg resize-none transition-all"
                ></textarea>
              </div>

              <div class="flex justify-end mt-2">
                <button
                  type="submit"
                  class="nav-gamer-submit-btn group relative px-6 py-3 bg-cyan-500 text-slate-950 font-bold text-xs tracking-widest uppercase cursor-pointer transition-all hover:bg-cyan-400 hover:shadow-[0_0_20px_rgba(34,211,238,0.4)]"
                >
                  <div class="flex items-center gap-2 relative z-10">
                    <span>Transmitir Datos</span>
                    <svg
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2.5"
                      viewBox="0 0 24 24"
                      class="w-4 h-4 transform group-hover:translate-x-1 transition-transform"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5"
                      />
                    </svg>
                  </div>
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';

const handleSubmit = () => {
  // Aquí puedes integrar EmailJS, Formspree o tu propio backend
  console.log('Transmisión inicializada...');
};
</script>

<style scoped>
/* Estilo recortado poligonal personalizado para el botón de envío */
.nav-gamer-submit-btn {
  clip-path: polygon(0 0, 88% 0, 100% 30%, 100% 100%, 12% 100%, 0 70%);
}
</style>
