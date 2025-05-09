<template>
  <div class="terminal-container w-full max-w-3xl">
    <div class="terminal-header bg-gray-800 rounded-t-lg p-3 flex items-center">
      <div class="flex space-x-2 mr-4">
        <span class="w-3 h-3 rounded-full bg-red-500"></span>
        <span class="w-3 h-3 rounded-full bg-yellow-500"></span>
        <span class="w-3 h-3 rounded-full bg-green-500"></span>
      </div>
      <div class="text-sm text-gray-400">developer-profile.js</div>
    </div>
    <div class="terminal-body bg-gray-800 rounded-b-lg p-6 font-mono">
      <div class="typing-container">
        <div class="command-line flex items-start mb-4">
          <span class="text-green-400 mr-2">$</span>
          <span class="typing-text">{{ displayedText }}</span>
          <span class="cursor-blink" :class="{ 'opacity-0': !cursorVisible }">|</span>
        </div>
        <div class="code-output" v-if="showCodeOutput" v-html="highlightedCode"></div>
        <div v-if="showExecutionOutput" class="mt-4 text-green-400">
          // Output:
          <div class="ml-4 mt-2">
            <div><span class="text-blue-400">name:</span> {{ developer.name }}</div>
            <div><span class="text-blue-400">role:</span> {{ developer.role }}</div>
            <div><span class="text-blue-400">skills:</span> {{ developer.skills.join(', ') }}</div>
            <div>
              <span class="text-blue-400">available:</span> {{ developer.available ? 'Yes' : 'No' }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

interface Developer {
  name: string
  role: string
  skills: string[]
  passion: string
  available: boolean
}

const fullCode: string = `const developer = {
  name: 'Luis Alberto Chavero Chavez',
  role: 'Front-end Developer',
  skills: [
    'React',
    'JavaScript',
    'CSS/Tailwind',
    'HTML5',
    'UI/UX Design'
  ],
  passion: 'Building intuitive web experiences',
  available: true
};`

const developer: Developer = {
  name: 'Luis Alberto Chavero Chavez',
  role: 'Front-end Developer',
  skills: ['React', 'JavaScript', 'CSS/Tailwind', 'HTML5', 'UI/UX Design'],
  passion: 'Building intuitive web experiences',
  available: true,
}

// Refs reactivas
const displayedText = ref<string>('')
const cursorVisible = ref<boolean>(true)
const showCodeOutput = ref<boolean>(false)
const showExecutionOutput = ref<boolean>(false)
const typingComplete = ref<boolean>(false)
let cursorInterval: number | undefined
let typingTimeout: number | undefined

// Computed property para código resaltado
const highlightedCode = computed<string>(() => {
  return fullCode
    .replace(/(const|let|var|true|false)/g, '<span class="text-purple-400">$1</span>')
    .replace(/(['"].*?['"])/g, '<span class="text-yellow-300">$1</span>')
    .replace(/([{}[\],:;])/g, '<span class="text-gray-400">$1</span>')
})

// Función para el efecto de escritura
const typeWriter = (text: string, index: number = 0): void => {
  if (index < text.length) {
    displayedText.value += text.charAt(index)
    typingTimeout = setTimeout(
      () => typeWriter(text, index + 1),
      Math.random() * 50 + 30,
    ) as unknown as number
  } else {
    typingComplete.value = true
    showCodeOutput.value = true
    displayedText.value = ''

    // Simular ejecución después de mostrar el código
    setTimeout(() => {
      displayedText.value = 'node developer-profile.js'
      setTimeout(() => {
        displayedText.value = ''
        showExecutionOutput.value = true
      }, 1000)
    }, 1000)
  }
}

// Iniciar efectos al montar el componente
onMounted(() => {
  cursorInterval = setInterval(() => {
    cursorVisible.value = !cursorVisible.value
  }, 500) as unknown as number

  // Iniciar animación de escritura después de 1 segundo
  setTimeout(() => typeWriter(fullCode), 1000)
})

// Limpiar intervalos al desmontar
onUnmounted(() => {
  if (cursorInterval) clearInterval(cursorInterval)
  if (typingTimeout) clearTimeout(typingTimeout)
})
</script>

<style scoped>
.terminal-container {
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.cursor-blink {
  transition: opacity 0.3s ease;
}
</style>
