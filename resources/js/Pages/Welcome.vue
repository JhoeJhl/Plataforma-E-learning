<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import { Head } from '@inertiajs/vue3';

// Definimos que esta página usa el AppLayout
defineOptions({ layout: AppLayout });
</script>

<template>
  <Head title="Bienvenido a mis Cursos" />
  
  <div class="py-20 px-6 max-w-5xl mx-auto text-center">
    <span class="inline-block px-4 py-1.5 mb-6 text-sm font-semibold tracking-wide text-indigo-600 uppercase bg-indigo-100 dark:bg-indigo-900/30 dark:text-indigo-400 rounded-full">
      ¡Lanzamiento 2026!
    </span>
    <h1 class="text-5xl md:text-7xl font-extrabold mb-8 bg-gradient-to-r from-slate-900 to-slate-700 dark:from-white dark:to-slate-400 bg-clip-text text-transparent">
      Aprende Programación de forma Real.
    </h1>
    <p class="text-xl text-slate-600 dark:text-slate-400 mb-10 max-w-2xl mx-auto">
      Accede a rutas de aprendizaje estructuradas con Laravel 12 y Vue.js. Proyectos prácticos que el mercado laboral exige.
    </p>
    <div class="flex flex-col sm:flex-row justify-center gap-4">
      <button class="bg-indigo-600 hover:bg-indigo-700 text-white px-8 py-4 rounded-2xl text-lg font-bold shadow-xl shadow-indigo-500/20">
        Empezar Ahora
      </button>
      <button class="bg-slate-200 dark:bg-slate-800 px-8 py-4 rounded-2xl text-lg font-bold">
        Ver Plan de Estudios
      </button>
    </div>
  </div>
</template>