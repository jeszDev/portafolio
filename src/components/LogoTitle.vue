<template>
  <div class="logo-wrapper">
    <div class="logo-container">
      <h1 class="logo-text">
        <span class="syntax">;</span>esz<span class="syntax">&lt;/</span>Dev<span class="syntax">&gt;</span>
      </h1>
    </div>
  </div>
</template>

<script setup lang="ts">
// Aquí puedes agregar props en el futuro si quieres cambiar el tamaño dinámicamente
</script>

<style scoped>
/* 1. Variables de entorno aplicadas al contenedor del componente */
.logo-wrapper {
  --bg-color: #0d1117;       /* Fondo oscuro tipo GitHub */
  --text-color: #e6edf3;     /* Blanco suave para las letras */
  --syntax-color: #58a6ff;   /* Azul brillante para los símbolos de código */
  --cursor-color: #f0883e;   /* Naranja/Amarillo para el cursor parpadeante */
  --font-size: 1.5rem;         /* Tamaño del logo */

  background-color: var(--bg-color);
  display: flex;
  justify-content: center;
  align-items: center;

  margin: 0;
  font-family: 'Fira Code', 'Courier New', Courier, monospace;
}

/* 2. Estilo del Logo y Animación Typewriter */
.logo-container {
  display: inline-flex;
  align-items: center;
  position: relative;
}

.logo-text {
  font-size: var(--font-size);
  font-weight: 700;
  color: var(--text-color);
  white-space: nowrap;
  overflow: hidden;
  border-right: 4px solid var(--cursor-color);

  /*
    - typewriter: 2.5 segundos de duración.
    - blink: 0.5s por ciclo, se repite exactamente 5 veces (5 * 0.5s = 2.5s).
    'forwards' hace que el cursor mantenga su estado final (transparente).
  */
  animation:
    typewriter 2.5s steps(10, end) forwards,
    blink 0.5s step-end 5 forwards;
}

/* 3. Colores de resaltado de sintaxis */
.syntax {
  color: var(--syntax-color);
}

/* 4. Keyframes de las animaciones */
@keyframes typewriter {
  from { width: 0; }
  to { width: 100%; }
}

@keyframes blink {
  from, to { border-color: var(--cursor-color); }
  50% { border-color: transparent; }
}
</style>
