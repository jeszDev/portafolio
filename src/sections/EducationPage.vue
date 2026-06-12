<template>
  <section class="w-full py-12 gamer-education relative overflow-hidden">
    <!-- Section Title -->
    <div class="flex justify-center mb-16">
      <TitleSection title="EDUCACIÓN Y LOGROS" data-aos="fade-up" />
    </div>

    <div class="max-w-6xl mx-auto px-4 grid md:grid-cols-3 gap-8">
      <!-- MAIN QUESTS: ACADEMIC RECORD (Left Column, spans 2 cols on wide screens) -->
      <div class="md:col-span-2 space-y-8" data-aos="fade-right">
        <div class="flex items-center gap-2 mb-6">
          <span class="w-2.5 h-2.5 bg-cyan-400 animate-pulse"></span>
          <h2 class="text-sm font-mono tracking-[0.2em] text-cyan-400 uppercase font-bold">
            // MAIN_QUESTS: ACADEMIC_RECORD
          </h2>
        </div>

        <!-- Master Degree Card -->
        <div class="quest-card p-6 bg-slate-950/40 border border-slate-800 rounded-xl backdrop-blur-md relative group">
          <div class="absolute top-0 left-0 w-4 h-4 border-t-2 border-l-2 border-cyan-400"></div>
          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 mb-4">
            <div>
              <h3 class="text-xl font-black text-white uppercase tracking-wider group-hover:text-cyan-300 transition-colors">
                Maestría en Seguridad Informática
              </h3>
              <p class="text-sm text-cyan-400/80 font-mono">
                Universidad Internacional de La Rioja (UNIR)
              </p>
            </div>
            <span class="font-mono text-xs px-3 py-1 bg-cyan-500/10 border border-cyan-500/30 text-cyan-400 self-start sm:self-center uppercase tracking-wider">
              2023 – 2024
            </span>
          </div>
          <ul class="space-y-2 font-mono text-xs text-slate-400">
            <li class="flex items-start gap-2">
              <span class="text-cyan-400 font-bold">&gt;</span> Formación especializada en seguridad de la información, protección de datos y gestión de riesgos.
            </li>
            <li class="flex items-start gap-2">
              <span class="text-cyan-400 font-bold">&gt;</span> Enfoque en seguridad aplicada a sistemas informáticos y plataformas digitales.
            </li>
          </ul>
        </div>

        <!-- Bachelor Degree Card -->
        <div class="quest-card p-6 bg-slate-950/40 border border-slate-800 rounded-xl backdrop-blur-md relative group">
          <div class="absolute top-0 left-0 w-4 h-4 border-t-2 border-l-2 border-cyan-400"></div>
          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 mb-4">
            <div>
              <h3 class="text-xl font-black text-white uppercase tracking-wider group-hover:text-cyan-300 transition-colors">
                Ingeniería en Computación
              </h3>
              <p class="text-sm text-cyan-400/80 font-mono">
                Universidad Michoacana de San Nicolás de Hidalgo (UMSNH)
              </p>
            </div>
            <span class="font-mono text-xs px-3 py-1 bg-slate-800 border border-slate-700 text-slate-400 self-start sm:self-center uppercase tracking-wider">
              Egreso: 2015
            </span>
          </div>
          <ul class="space-y-2 font-mono text-xs text-slate-400">
            <li class="flex items-start gap-2">
              <span class="text-cyan-400 font-bold">&gt;</span> Formación en programación, estructuras de datos, bases de datos, sistemas computacionales y análisis de sistemas.
            </li>
            <li class="flex items-start gap-2">
              <span class="text-cyan-400 font-bold">&gt;</span> Base técnica sólida para el desarrollo de aplicaciones y soluciones tecnológicas.
            </li>
          </ul>
        </div>
      </div>

      <!-- SIDE QUESTS: CERTIFICATIONS (Right Column, spans 1 col) -->
      <div class="space-y-8" data-aos="fade-left">
        <div class="flex items-center gap-2 mb-6">
          <span class="w-2.5 h-2.5 bg-fuchsia-500 animate-pulse"></span>
          <h2 class="text-sm font-mono tracking-[0.2em] text-fuchsia-500 uppercase font-bold">
            // UPGRADES: CERTIFICATIONS
          </h2>
        </div>

        <div class="grid gap-4">
          <div
            v-for="(cert, index) in certificates"
            :key="index"
            class="cert-card p-4 bg-slate-950/60 border border-slate-900 hover:border-fuchsia-500/40 rounded-xl transition-all relative flex items-center justify-between group"
          >
            <div class="flex items-center gap-3">
              <!-- Cert Mini Tech Badge Icon -->
              <div class="w-10 h-10 rounded border border-slate-800 flex items-center justify-center bg-slate-900 group-hover:border-fuchsia-500/30 group-hover:bg-fuchsia-950/10 transition-colors">
                <!-- Tech Icon Custom SVGs -->
                <svg v-if="cert.tech === 'vscode'" class="w-5 h-5 text-sky-400" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M23.984 6.742a.526.526 0 00-.236-.368L18.45 2.5a.519.519 0 00-.638.077L13.1 7.228 3.824.975a.522.522 0 00-.7-.008L.226 3.421A.521.521 0 00.2 4.195l5.068 4.39-5.068 4.39a.52.52 0 00.026.774l2.898 2.454a.52.52 0 00.7-.008L13.1 9.957l4.713 4.651a.519.519 0 00.638.077l5.297-3.874a.52.52 0 00.236-.368V6.742zm-12.01 4.79l-4.577-3.66 4.577-3.66v7.32z"/>
                </svg>
                <svg v-else-if="cert.tech === 'vue'" class="w-5 h-5 text-emerald-400" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M24,1.61H17.75L12,11.56,6.25,1.61H0L12,22.39ZM17.75,1.61H13.62L12,4.42,10.38,1.61H6.25L12,11.56Z"/>
                </svg>
                <svg v-else-if="cert.tech === 'docker'" class="w-5 h-5 text-cyan-400" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M13.983 11.078h2.119c.102 0 .186-.083.186-.185V9.006a.185.185 0 00-.186-.186h-2.119a.185.185 0 00-.185.185v1.888c0 .102.083.185.185.185m-2.954-5.43h2.118c.102 0 .185-.083.185-.186V3.575a.186.186 0 00-.185-.185h-2.118a.185.185 0 00-.186.185v1.887c0 .102.084.186.186.186m-2.957 5.43h2.119c.102 0 .185-.083.185-.185V9.006a.185.185 0 00-.185-.186H8.072a.186.186 0 00-.186.185v1.888c0 .102.084.185.186.185m0-2.72h2.119c.102 0 .185-.083.185-.186V6.29a.185.185 0 00-.185-.185H8.072a.185.185 0 00-.186.185v1.887c0 .102.084.186.186.186m-2.955 2.72h2.118c.102 0 .186-.083.186-.185V9.006a.185.185 0 00-.186-.186H5.117a.185.185 0 00-.186.185v1.888c0 .102.084.185.186.185m0-2.72h2.118c.102 0 .186-.083.186-.186V6.29a.185.185 0 00-.186-.185H5.117a.185.185 0 00-.186.185v1.887c0 .102.084.186.186.186m-2.956 2.72h2.118c.103 0 .186-.083.186-.185V9.006a.185.185 0 00-.186-.186H2.16a.185.185 0 00-.186.185v1.888c0 .102.083.185.186.185m0-2.72h2.118c.103 0 .186-.083.186-.186V6.29a.185.185 0 00-.186-.185H2.162a.185.185 0 00-.186.185v1.887c0 .102.083.186.186.186M2.161 5.451h2.118c.103 0 .186-.083.186-.186V3.378a.185.185 0 00-.186-.185H2.161a.185.185 0 00-.186.185v1.887c0 .102.083.186.186.186M23.99 9.886c-.19-.7-1.111-2.428-2.909-3.259-.88-.41-1.675-.422-2.299-.37l-.023.012c-.387.082-.677.24-.86.343a.217.217 0 00-.117.186V16.2c0 .2.084.38.22.5a6.57 6.57 0 005.437.38c1.247-.458 1.512-1.888 1.516-1.936.02-.1.018-.31-.065-.53-.557-.515-1.286-.89-1.902-1.12l-.082-.03c-.45-.17-.89-.34-1.29-.63-.26-.18-.46-.43-.59-.75-.15-.35-.19-.77-.12-1.21.07-.43.25-.82.52-1.11.27-.29.61-.47.99-.51l.137-.01c.41-.03.84.06 1.27.24.5.21 1.08.54 1.58.94.1.07.23.09.34.05a.28.28 0 00.162-.242V9.97a.2.2 0 00-.014-.084m-4.63 7.633h-.006a12.013 12.013 0 01-6.002 1.58 12.216 12.216 0 01-6.006-1.579.244.244 0 00-.215-.01 2.228 2.228 0 00-1.357 2.023v.006c0 .125.1.227.229.228 3.733.033 7.045 1.068 7.212 1.117a.23.23 0 00.147 0c.18-.05 3.49-1.084 7.227-1.117a.23.23 0 00.228-.228v-.004a2.228 2.228 0 00-1.35-2.025.244.244 0 00-.11-.007"/>
                </svg>
                <svg v-else-if="cert.tech === 'flutter'" class="w-5 h-5 text-blue-400" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M14.314 0L2.3 12 6 15.7 21.684.013h-7.37zM2.3 12l8 8 3.7-3.7-8-8zm11.72 4.25L10.3 20l3.7 3.7 7.7-7.7h-7.686z"/>
                </svg>
                <svg v-else-if="cert.tech === 'typescript'" class="w-5 h-5 text-blue-500" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M1.125 0C.502 0 0 .502 0 1.125V22.88C0 23.498.502 24 1.125 24h21.75c.623 0 1.125-.502 1.125-1.125V1.125C24 .502 23.498 0 22.875 0H1.125zm16.965 14.18c.983 0 1.812.44 2.45 1.272.637.828.955 1.986.955 3.473 0 1.442-.327 2.585-.98 3.432-.653.847-1.575 1.27-2.766 1.27-1.1 0-1.964-.344-2.59-1.03-.63-.687-.944-1.72-.944-3.097H16.8c0 .736.14 1.282.417 1.636.278.354.708.53 1.288.53.536 0 .942-.18 1.218-.54.276-.36.413-.997.413-1.91 0-.9-.133-1.527-.4-1.88-.266-.353-.692-.53-1.278-.53-.34 0-.67.076-.988.228l-.348-.17 1.056-4.992h4.5v1.656h-2.916l-.42 2.016c.366-.144.757-.216 1.173-.216zm-8.877-2.28h3.336v1.656H12.55v7.2c0 .72.115 1.212.348 1.476.23.264.606.396 1.128.396.348 0 .685-.06 1.008-.18v1.728c-.468.168-1.002.252-1.608.252-1.056 0-1.85-.306-2.382-.918-.53-.612-.798-1.554-.798-2.826V13.56H9.213v-1.656z"/>
                </svg>
              </div>
              
              <div>
                <h4 class="text-sm font-bold text-white uppercase font-mono tracking-wide group-hover:text-fuchsia-400 transition-colors">
                  {{ cert.name }}
                </h4>
                <p class="text-[10px] text-slate-500 font-mono">
                  // STATUS: CERTIFIED
                </p>
              </div>
            </div>

            <!-- Download PDF Button -->
            <a
              :href="cert.pdfPath"
              target="_blank"
              :download="'Certificado_' + cert.name.replace(/\s+/g, '_') + '.pdf'"
              class="btn-cert-download cursor-pointer"
            >
              <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import TitleSection from '../components/TitleSection.vue';

interface Certificate {
  name: string;
  tech: string;
  pdfPath: string;
}

const certificates: Certificate[] = [
  { name: 'Visual Studio Code', tech: 'vscode', pdfPath: '/certificates/vscode.pdf' },
  { name: 'Vue.js', tech: 'vue', pdfPath: '/certificates/vue.pdf' },
  { name: 'Docker', tech: 'docker', pdfPath: '/certificates/docker.pdf' },
  { name: 'Flutter', tech: 'flutter', pdfPath: '/certificates/flutter.pdf' },
  { name: 'TypeScript', tech: 'typescript', pdfPath: '/certificates/typescript.pdf' }
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap');

.gamer-education {
  font-family: 'JetBrains Mono', monospace;
}

/* Quest Card Academic styling */
.quest-card {
  box-shadow: inset 0 0 20px rgba(34, 211, 238, 0.03), 0 10px 30px rgba(0, 0, 0, 0.5);
  clip-path: polygon(0 0, 97% 0, 100% 8%, 100% 100%, 0 100%);
  transition: all 0.25s ease;
}

.quest-card:hover {
  border-color: rgba(34, 211, 238, 0.3);
  transform: translateY(-2px);
  background: rgba(15, 23, 42, 0.3);
}

/* Certificate List Cards styling */
.cert-card {
  box-shadow: inset 0 0 10px rgba(240, 46, 170, 0.01), 0 4px 15px rgba(0, 0, 0, 0.3);
  clip-path: polygon(0 0, 100% 0, 100% 100%, 6% 100%, 0 75%);
  transition: all 0.2s ease;
}

.cert-card:hover {
  transform: translateX(4px);
  box-shadow: -3px 0 12px rgba(240, 46, 170, 0.15);
}

/* Cyber design for download button */
.btn-cert-download {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2rem;
  height: 2rem;
  background: rgba(51, 65, 85, 0.3);
  border: 1px solid #334155;
  color: #94a3b8;
  border-radius: 4px;
  transition: all 0.2s ease;
}

.cert-card:hover .btn-cert-download {
  border-color: #d946ef;
  color: #fff;
  background: rgba(217, 70, 239, 0.2);
  box-shadow: 0 0 10px rgba(217, 70, 239, 0.4);
}
</style>
