<template>
  <div class="bg-gray-900 antialiased p-4 flex items-center justify-center">
    <div class="relative max-w-4xl mx-auto flex flex-col gap-8 items-center">
      <!-- Card with project info -->
      <div
        class="z-10 p-6 max-w-md w-full cursor-default select-none rounded-lg bg-gray-200 dark:bg-gray-800 shadow-lg order-2 md:order-1"
      >
        <div class="font-semibold text-2xl mb-4 text-gray-800 dark:text-white">Project Name</div>

        <div class="flex gap-3 mb-4">
          <button
            class="transition-all bg-gray-800 text-sm text-white py-2 px-4 font-semibold rounded-md hover:bg-gray-700 dark:hover:bg-gray-600 active:scale-95 focus:outline-none focus:ring-2 focus:ring-gray-500"
          >
            Live Demo
          </button>
          <button
            class="transition-all bg-gray-800 text-sm text-white py-2 px-4 font-semibold rounded-md hover:bg-gray-700 dark:hover:bg-gray-600 active:scale-95 focus:outline-none focus:ring-2 focus:ring-gray-500"
          >
            View Code
          </button>
        </div>

        <div class="mb-5">
          <p class="text-gray-700 dark:text-gray-300 text-base">
            A brief description of what the project is and what it does and technologies used.
          </p>
        </div>

        <div>
          <div class="font-semibold text-lg text-gray-800 dark:text-gray-200 mb-3">Tech Stack:</div>
          <div class="flex flex-wrap gap-2">
            <span
              class="transition-all inline-block bg-blue-400 bg-opacity-75 rounded-md px-3 py-1.5 text-xs font-medium text-blue-900 hover:shadow-md active:scale-95"
            >
              ReactJS
            </span>
            <span
              class="transition-all inline-block bg-pink-400 bg-opacity-75 rounded-md px-3 py-1.5 text-xs font-medium text-pink-900 hover:shadow-md active:scale-95"
            >
              TailwindCSS
            </span>
            <span
              class="transition-all inline-block bg-yellow-400 bg-opacity-75 rounded-md px-3 py-1.5 text-xs font-medium text-yellow-900 hover:shadow-md active:scale-95"
            >
              JavaScript
            </span>
          </div>
        </div>
      </div>

      <!-- Project image -->
      <div class="order-1 md:order-2 w-full max-w-md md:max-w-lg">
        <img
          class="w-full h-auto object-cover rounded-xl border-2 border-gray-500 border-opacity-30 shadow-xl transition-all duration-300 hover:scale-105 hover:shadow-2xl"
          src="@/assets/images/project-1.jpg"
          alt="Project screenshot"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>
