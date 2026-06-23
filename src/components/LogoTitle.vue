<template>
  <div class="logo-wrapper">
    <div class="logo-container">
      <h1 class="logo-text">
        <span class="custom-syntax">;</span>esz<span class="terminal-prompt"
          ><svg class="terminal-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
            <path
              d="M73.4 182.6C60.9 170.1 60.9 149.8 73.4 137.3C85.9 124.8 106.2 124.8 118.7 137.3L278.7 297.3C291.2 309.8 291.2 330.1 278.7 342.6L118.7 502.6C106.2 515.1 85.9 515.1 73.4 502.6C60.9 490.1 60.9 469.8 73.4 457.3L210.7 320L73.4 182.6zM288 448L544 448C561.7 448 576 462.3 576 480C576 497.7 561.7 512 544 512L288 512C270.3 512 256 497.7 256 480C256 462.3 270.3 448 288 448z"
            /></svg></span
        ><span class="animated-text">ev</span>
      </h1>
    </div>
  </div>
</template>

<script setup lang="ts">
// Listo para props en el futuro (ej. tamaño o colores)
</script>

<style scoped>
/* 1. Variables de entorno - CONFIGURA AQUÍ TUS COLORES */
.logo-wrapper {
  --bg-color: #0d1117; /* Fondo oscuro tipo GitHub */
  --text-color: #e6edf3; /* Blanco suave para las letras "esz" */
  --syntax-color: #39ff14; /* Color personalizado para el ';' */
  --terminal-color: #39ff14; /* Verde brillante para el icono SVG */
  --cursor-color: #39ff14; /* Naranja para el cursor parpadeante */
  --font-size: 2.5rem; /* Un tamaño de logo impactante */

  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Fira Code', 'Courier New', Courier, monospace;
  padding: 1rem; /* Pequeño padding para que no toque los bordes si se escala */
}

/* 2. Estilo del Logo y Contenedor */
.logo-container {
  display: inline-flex;
  align-items: center;
}

.logo-text {
  font-size: var(--font-size);
  font-weight: 700;
  color: var(--text-color);
  margin: 0;
  display: flex;
  align-items: center; /* Alinea verticalmente texto e icono */
  white-space: nowrap;
}

/* 3. Estilo personalizado para el punto y coma ';' */
.custom-syntax {
  color: var(--syntax-color);
  margin-right: -0.1em; /* Ajusta el espaciado si es necesario */
}

/* 4. Estilo del Prompt SVG (Icono Grande) */
.terminal-prompt {
  display: flex;
  align-items: center;
  margin: 0 0.1em; /* Un poco de espaciado a los lados */
}

.terminal-icon {
  /* ¡Aquí está el truco! Hacemos el SVG más grande que el texto */
  height: 1.4em; /* 1.4 veces el tamaño del texto */
  width: auto; /* Mantiene la proporción */
  fill: var(--terminal-color); /* Aplica el color del terminal al SVG */

  /* Ajuste vertical sutil para que se vea balanceado con el texto más pequeño */
  transform: translateY(0.1em);
}

/* 5. Texto 'ev' con Animación de Bucle y Cursor */
.animated-text {
  display: inline-block;
  overflow: hidden; /* Esconde el texto mientras se escribe */
  white-space: nowrap;
  vertical-align: bottom; /* Alineación base */
  border-right: 3px solid var(--cursor-color); /* El cursor parpadeante */
  width: 0; /* Ancho inicial para el efecto de escritura */

  /* Mismo color que las letras 'esz', para que parezca una palabra */
  color: var(--text-color);

  /* Animaciones:
    - typewriter-loop: simula escritura/borrado, 5s de ciclo, 2 pasos (letras 'e' y 'v')
    - blink: parpadeo del cursor, ciclo rápido
  */
  animation:
    typewriter-loop 5s steps(2, end) infinite,
    blink 0.6s step-end infinite;
}

/* 6. Keyframes de las animaciones (Se mantienen de la propuesta anterior) */

@keyframes typewriter-loop {
  0%,
  10% {
    width: 0;
  } /* 0s - 0.5s: Vacío */
  25%,
  50% {
    width: 2ch;
  } /* 1.25s - 2.5s: Escribe 'ev' y lo muestra */
  65%,
  90% {
    width: 0;
  } /* 3.25s - 4.5s: Borra 'ev' */
  100% {
    width: 0;
  } /* Reinicia */
}

@keyframes blink {
  from,
  to {
    border-color: var(--cursor-color);
  }
  50% {
    border-color: transparent;
  }
}
</style>
