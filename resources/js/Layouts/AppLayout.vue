<script setup>
import { ref, onMounted } from 'vue';
import { Link, Head } from '@inertiajs/vue3';

const isDark = ref(false);

// Función para cambiar el modo
const toggleTheme = () => {
  isDark.value = !isDark.value;
  if (isDark.value) {
    document.documentElement.classList.add('dark');
    localStorage.setItem('theme', 'dark');
  } else {
    document.documentElement.classList.remove('dark');
    localStorage.setItem('theme', 'light');
  }
};

// Cargar preferencia al iniciar
onMounted(() => {
  if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDark.value = true;
    document.documentElement.classList.add('dark');
  } else {
    isDark.value = false;
    document.documentElement.classList.remove('dark');
  }
});
</script>

<template>
  <div class="min-h-screen bg-white dark:bg-slate-950 text-slate-900 dark:text-slate-100 transition-colors duration-300">
    <nav class="sticky top-0 z-50 w-full border-b border-slate-200 dark:border-slate-800 bg-white/80 dark:bg-slate-950/80 backdrop-blur-md">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16 items-center">
          <Link href="/" class="text-2xl font-black text-indigo-600 dark:text-indigo-400">UDE-CLONE</Link>
          
          <div class="flex items-center gap-6">
            <Link href="/cursos" class="font-medium hover:text-indigo-500">Explorar</Link>
            
            <button @click="toggleTheme" class="p-2 rounded-full bg-slate-100 dark:bg-slate-800 hover:ring-2 ring-indigo-500 transition-all">
              <span v-if="!isDark">🌙</span>
              <span v-else>☀️</span>
            </button>

            <Link href="/login" class="hidden sm:block">Entrar</Link>
            <Link href="/register" class="bg-indigo-600 text-white px-4 py-2 rounded-lg font-bold">Únete</Link>
          </div>
        </div>
      </div>
    </nav>

    <main>
      <slot />
    </main>

    <footer class="py-10 text-center border-t border-slate-200 dark:border-slate-800 opacity-60 text-sm">
      &copy; 2026 - Plataforma E-learning Profesional
    </footer>
  </div>
</template>