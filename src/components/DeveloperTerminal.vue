<template>
<div class="flex items-center justify-center"> <!-- Contenedor padre (centrado vertical/horizontal) -->
  <div class="code-container font-mono flex flex-col w-full max-w-3xl"> <!-- Elimina justify-center/items-center aquí -->
    <div class="filename-bar bg-gray-700 px-4 py-2 rounded-t-lg w-full flex items-center justify-between">
      <div class="text-gray-300 text-sm flex items-center gap-2">
        <svg xmlns="http://www.w3.org/2000/svg" height="18" width="17.5" viewBox="0 0 448 512"><path fill="#FFD43B" d="M448 96c0-35.3-28.7-64-64-64H64C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H384c35.3 0 64-28.7 64-64V96zM180.9 444.9c-33.7 0-53.2-17.4-63.2-38.5L152 385.7c6.6 11.7 12.6 21.6 27.1 21.6c13.8 0 22.6-5.4 22.6-26.5V237.7h42.1V381.4c0 43.6-25.6 63.5-62.9 63.5zm85.8-43L301 382.1c9 14.7 20.8 25.6 41.5 25.6c17.4 0 28.6-8.7 28.6-20.8c0-14.4-11.4-19.5-30.7-28l-10.5-4.5c-30.4-12.9-50.5-29.2-50.5-63.5c0-31.6 24.1-55.6 61.6-55.6c26.8 0 46 9.3 59.8 33.7L368 290c-7.2-12.9-15-18-27.1-18c-12.3 0-20.1 7.8-20.1 18c0 12.6 7.8 17.7 25.9 25.6l10.5 4.5c35.8 15.3 55.9 31 55.9 66.2c0 37.8-29.8 58.6-69.7 58.6c-39.1 0-64.4-18.6-76.7-43z"/></svg>
        developer-profile.js
      </div>
      <div class="flex gap-1">
          <span class="w-3 h-3 rounded-full bg-red-500"></span>
          <span class="w-3 h-3 rounded-full bg-yellow-500"></span>
          <span class="w-3 h-3 rounded-full bg-green-500"></span>
      </div>
    </div>

    <div class="code-content p-4 rounded-b-lg w-full">
      <div class="code-line" v-for="(line, index) in displayedLines" :key="index">
        <span class="line-number text-gray-500 mr-4 select-none pe-2">{{ index + 1 }}</span>
        <span class="code-text text-white" v-html="highlightSyntax(line)"></span>
        <span
          class="cursor-blink text-white"
          v-if="currentLine === index && cursorVisible"
        >|</span>
      </div>
    </div>
  </div>
</div>
</template>

<script lang="ts" setup>
import { ref, computed, onMounted, onUnmounted } from 'vue';

interface Developer {
  name: string;
  role: string;
  skills: string[];
  passion: string;
  available: boolean;
}

const fullCode = `const developer = {
  name: 'Jessie Josue Canchola Romero',
  nickname: 'JeszDev',
  role: 'Full stack developer',
  skills: [
    'Alpine Js',
    'CSS/Tailwind',
    'HTML5',
    'JavaScript',
    'Laravel',
    'Livweire',
    'TypeScript',
    'Vue 3',
  ],
  learning: ['Dart'],
  passion: 'Building intuitive web experiences', 'futbol',
};`;

// Dividir el código en líneas
const codeLines = fullCode.split('\n');
const displayedLines = ref<string[]>([]);
const currentLine = ref<number>(0);
const currentChar = ref<number>(0);
const cursorVisible = ref<boolean>(true);
let animationInterval: number;
let cursorInterval: number;

// Resaltado de sintaxis
const highlightSyntax = (line: string): string => {
  return line
    // Comentarios primero (son muy específicos)
    .replace(/\/\/.*$/g, '<span class="text-green-500">$&</span>')
    // Strings entre comillas (también muy específicos)
    .replace(/(['"].*?['"])/g, '<span class="text-yellow-300">$1</span>')
    // Palabras clave
    .replace(/(const|let|var|true|false)/g, '<span class="text-purple-400">$1</span>')
    // Símbolos especiales
    .replace(/([{}[\],:;])/g, '<span class="text-blue-400">$1</span>');
};

// Efecto de escritura línea por línea
const typeNextLine = (): void => {
  if (currentLine.value < codeLines.length) {
    const line = codeLines[currentLine.value];

    if (currentChar.value < line.length) {
      if (displayedLines.value.length <= currentLine.value) {
        displayedLines.value.push('');
      }

      displayedLines.value[currentLine.value] = line.substring(0, currentChar.value + 1);
      currentChar.value++;
    } else {
      currentLine.value++;
      currentChar.value = 0;
    }
  } else {
    clearInterval(animationInterval);
  }
};

onMounted(() => {
  // Efecto de cursor intermitente
  cursorInterval = setInterval(() => {
    cursorVisible.value = !cursorVisible.value;
  }, 500) as unknown as number;

  // Iniciar animación de escritura
  animationInterval = setInterval(typeNextLine, 25) as unknown as number;
});

onUnmounted(() => {
  clearInterval(animationInterval);
  clearInterval(cursorInterval);
});
</script>

<style scoped>
.code-container {
  background: rgba(2, 6, 23, 0.8);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 16px;
  box-shadow:
    0 0 60px rgba(16,185,129,0.15),
    0 10px 40px rgba(0,0,0,0.6);
}

.code-content {
  font-family: 'Fira Code', 'Courier New', monospace;
  counter-reset: line;
}

.code-line {
  min-height: 1.5em;
  display: flex;
  align-items: center;
  white-space: pre;
}

.line-number {
  display: inline-block;
  width: 2.5em;
  text-align: right;
}

.cursor-blink {
  animation: blink 1s step-end infinite;
  background-color: #4fd1c5;
  width: 2px;
  height: 1.2em;
  display: inline-block;
  margin-left: 2px;
}

@keyframes blink {
  from, to { opacity: 1; }
  50% { opacity: 0; }
}
</style>
