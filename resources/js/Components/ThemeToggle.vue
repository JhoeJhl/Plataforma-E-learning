<template>
  <button 
    @click="toggleTheme" 
    class="theme-toggle"
    :aria-label="isDark ? 'Cambiar a modo claro' : 'Cambiar a modo oscuro'"
    title="Alternar tema"
  >
    <svg v-if="!isDark" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
    </svg>
    
    <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="5"></circle>
      <line x1="12" y1="1" x2="12" y2="3"></line>
      <line x1="12" y1="21" x2="12" y2="23"></line>
      <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
      <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
      <line x1="1" y1="12" x2="3" y2="12"></line>
      <line x1="21" y1="12" x2="23" y2="12"></line>
      <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
      <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
    </svg>
  </button>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

// Función para aplicar o quitar la clase 'dark' en el documento HTML
const applyTheme = (dark) => {
  if (dark) {
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
}

// Función que se ejecuta al hacer clic en el botón
const toggleTheme = () => {
  isDark.value = !isDark.value
  applyTheme(isDark.value)
  // Guardar la preferencia en el navegador
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light')
}

// Comprobar la preferencia inicial cuando el componente se monta
onMounted(() => {
  // Comprobar si hay un tema guardado en localStorage
  const savedTheme = localStorage.getItem('theme')
  
  if (savedTheme) {
    isDark.value = savedTheme === 'dark'
  } else {
    // Si no hay nada guardado, usar la preferencia del sistema operativo
    isDark.value = window.matchMedia('(prefers-color-scheme: dark)').matches
  }
  
  applyTheme(isDark.value)
})
</script>

<style scoped>
.theme-toggle {
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 8px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #333;
  transition: all 0.3s ease;
}

.theme-toggle:hover {
  background-color: rgba(0, 0, 0, 0.1);
}

/* Estilos para cuando el modo oscuro está activo (suponiendo que usas la clase .dark en el :root/html) */
:global(.dark) .theme-toggle {
  color: #f1f1f1;
}

:global(.dark) .theme-toggle:hover {
  background-color: rgba(255, 255, 255, 0.1);
}
</style>