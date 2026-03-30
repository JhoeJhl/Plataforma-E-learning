<script setup>
import { Head, Link } from '@inertiajs/vue3';
// Asumiendo que guardaste el botón de cambio de tema aquí:
import ThemeToggle from '@/Components/ThemeToggle.vue'; 

const categories = [
  { name: 'Desarrollo Web', icon: '💻', desc: 'Frontend, Backend y Full Stack' },
  { name: 'Bases de Datos', icon: '🗄️', desc: 'Diseño, optimización y SQL' },
  { name: 'Electrónica & Hardware', icon: '🔌', desc: 'Circuitos, microcontroladores y IoT' },
  { name: 'Habilidades IT', icon: '🚀', desc: 'Inglés técnico, Git y entornos' },
];

const featuredCourses = [
  {
    id: 1,
    title: 'Bootcamp Full Stack: Laravel 12 y Vue.js',
    category: 'Desarrollo Web',
    level: 'Intermedio - Avanzado',
    hours: '40h',
    price: '$49.99',
    image: 'bg-blue-500', // Clases de utilidad para simular imágenes
  },
  {
    id: 2,
    title: 'Maestría en Bases de Datos: PostgreSQL y Oracle',
    category: 'Bases de Datos',
    level: 'Todos los niveles',
    hours: '25h',
    price: '$34.99',
    image: 'bg-emerald-500',
  },
  {
    id: 3,
    title: 'Inglés B2 para Desarrolladores de Software',
    category: 'Habilidades IT',
    level: 'Intermedio',
    hours: '15h',
    price: '$29.99',
    image: 'bg-indigo-500',
  },
  {
    id: 4,
    title: 'Fundamentos de Electrónica y Circuitos',
    category: 'Electrónica & Hardware',
    level: 'Básico',
    hours: '12h',
    price: '$19.99',
    image: 'bg-orange-500',
  },
  {
    id: 5,
    title: 'Productividad Dev: WSL, Ubuntu y Git en Windows',
    category: 'Habilidades IT',
    level: 'Básico',
    hours: '8h',
    price: 'Gratis',
    image: 'bg-slate-700',
  },
  {
    id: 6,
    title: 'Fundamentos de Informática y Telecomunicaciones',
    category: 'Redes',
    level: 'Universitario',
    hours: '30h',
    price: '$39.99',
    image: 'bg-cyan-600',
  }
];
</script>

<template>
  <Head title="Plataforma de Cursos de Tecnología" />

  <div class="min-h-screen bg-slate-50 dark:bg-slate-950 text-slate-900 dark:text-slate-100 transition-colors duration-300 font-sans">
    
    <nav class="sticky top-0 z-50 w-full border-b border-slate-200 dark:border-slate-800 bg-white/80 dark:bg-slate-950/80 backdrop-blur-md">
      <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
        <div class="flex items-center gap-2">
          <div class="w-8 h-8 bg-indigo-600 rounded-lg flex items-center justify-center text-white font-bold">JP</div>
          <span class="text-2xl font-black tracking-tight">TechAcademy</span>
        </div>
        
        <div class="hidden md:flex items-center gap-8 font-medium">
          <Link href="/cursos" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition">Catálogo</Link>
          <Link href="/rutas" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition">Rutas de Aprendizaje</Link>
          <Link href="/comunidad" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition">Comunidad</Link>
        </div>

        <div class="flex items-center gap-4">
          <ThemeToggle />
          <Link href="/login" class="hidden sm:block font-medium hover:text-indigo-600 dark:hover:text-indigo-400 transition">Ingresar</Link>
          <Link href="/register" class="bg-indigo-600 hover:bg-indigo-700 text-white px-5 py-2.5 rounded-xl font-semibold transition shadow-lg shadow-indigo-500/30">
            Regístrate
          </Link>
        </div>
      </div>
    </nav>

    <header class="relative overflow-hidden pt-24 pb-32">
      <div class="max-w-7xl mx-auto px-6 relative z-10 text-center">
        <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-indigo-100 dark:bg-indigo-900/30 text-indigo-700 dark:text-indigo-300 font-semibold text-sm mb-8">
          <span class="relative flex h-3 w-3">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-indigo-400 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-3 w-3 bg-indigo-500"></span>
          </span>
          Nuevos cursos disponibles este mes
        </div>
        <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight mb-8 max-w-4xl mx-auto leading-tight">
          Eleva tus habilidades en <span class="text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 to-cyan-500">Tecnología y Desarrollo</span>
        </h1>
        <p class="text-lg md:text-xl text-slate-600 dark:text-slate-400 mb-10 max-w-2xl mx-auto leading-relaxed">
          Aprende programación, bases de datos, electrónica e inglés técnico con proyectos reales. Construye el perfil profesional que las empresas buscan.
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <Link href="/cursos" class="bg-slate-900 dark:bg-white text-white dark:text-slate-900 px-8 py-4 rounded-2xl text-lg font-bold hover:scale-105 transition-transform">
            Explorar Cursos
          </Link>
        </div>
      </div>
      
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[800px] h-[800px] bg-indigo-500/10 dark:bg-indigo-500/5 rounded-full blur-3xl -z-10"></div>
    </header>

    <section class="py-20 bg-white dark:bg-slate-900 border-y border-slate-200 dark:border-slate-800">
      <div class="max-w-7xl mx-auto px-6">
        <h2 class="text-3xl font-bold mb-12 text-center">Explora por Áreas de Conocimiento</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div v-for="cat in categories" :key="cat.name" class="p-6 rounded-3xl border border-slate-200 dark:border-slate-800 hover:border-indigo-500 dark:hover:border-indigo-500 transition-colors bg-slate-50 dark:bg-slate-800/50 cursor-pointer group">
            <div class="text-4xl mb-4 group-hover:scale-110 transition-transform origin-left">{{ cat.icon }}</div>
            <h3 class="text-xl font-bold mb-2">{{ cat.name }}</h3>
            <p class="text-slate-600 dark:text-slate-400 text-sm">{{ cat.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-24 max-w-7xl mx-auto px-6">
      <div class="flex justify-between items-end mb-12">
        <div>
          <h2 class="text-3xl font-bold mb-4">Cursos Destacados</h2>
          <p class="text-slate-600 dark:text-slate-400">Comienza tu aprendizaje con el contenido mejor valorado.</p>
        </div>
        <Link href="/cursos" class="hidden sm:block text-indigo-600 dark:text-indigo-400 font-semibold hover:underline">Ver todo el catálogo &rarr;</Link>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <article v-for="course in featuredCourses" :key="course.id" class="flex flex-col bg-white dark:bg-slate-900 rounded-3xl overflow-hidden border border-slate-200 dark:border-slate-800 hover:shadow-2xl hover:shadow-indigo-500/10 transition-all group">
          <div :class="[course.image, 'h-48 w-full relative overflow-hidden']">
            <div class="absolute inset-0 bg-black/20 group-hover:bg-transparent transition-colors"></div>
            <span class="absolute top-4 left-4 bg-white/90 dark:bg-slate-900/90 text-xs font-bold px-3 py-1 rounded-full backdrop-blur-sm">
              {{ course.category }}
            </span>
          </div>
          
          <div class="p-6 flex flex-col flex-grow">
            <div class="flex items-center gap-4 text-xs font-medium text-slate-500 dark:text-slate-400 mb-3">
              <span class="flex items-center gap-1"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg> {{ course.hours }}</span>
              <span class="flex items-center gap-1"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg> {{ course.level }}</span>
            </div>
            
            <h3 class="text-xl font-bold mb-4 leading-snug group-hover:text-indigo-600 dark:group-hover:text-indigo-400 transition-colors">
              {{ course.title }}
            </h3>
            
            <div class="mt-auto pt-6 border-t border-slate-100 dark:border-slate-800 flex items-center justify-between">
              <span class="text-2xl font-black">{{ course.price }}</span>
              <button class="text-indigo-600 dark:text-indigo-400 font-bold hover:underline">Ver temario</button>
            </div>
          </div>
        </article>
      </div>
      <div class="mt-8 text-center sm:hidden">
        <Link href="/cursos" class="text-indigo-600 dark:text-indigo-400 font-semibold hover:underline">Ver todo el catálogo &rarr;</Link>
      </div>
    </section>

    <section class="py-24 bg-indigo-600 dark:bg-indigo-900 text-white">
      <div class="max-w-7xl mx-auto px-6 md:flex items-center gap-16">
        <div class="md:w-1/2 mb-10 md:mb-0">
          <div class="aspect-square max-w-md mx-auto bg-indigo-500 dark:bg-indigo-800 rounded-full overflow-hidden border-8 border-indigo-400/50">
            <div class="w-full h-full flex items-center justify-center text-indigo-300 text-2xl font-bold italic">
              [Tu Foto Aquí]
            </div>
          </div>
        </div>
        <div class="md:w-1/2">
          <h2 class="text-4xl font-extrabold mb-6">Aprende con un Desarrollador Full Stack</h2>
          <p class="text-indigo-100 text-lg mb-6 leading-relaxed">
            Soy un profesional Técnico Medio en Sistemas Informáticos y desarrollador autodidacta apasionado por enseñar. Mi objetivo es transmitirte conocimientos reales, orientados a la práctica y al mercado laboral actual.
          </p>
          <ul class="space-y-4 text-indigo-100 mb-8 font-medium">
             <li class="flex items-center gap-3"><svg class="w-6 h-6 text-indigo-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg> Enfoque 100% práctico.</li>
             <li class="flex items-center gap-3"><svg class="w-6 h-6 text-indigo-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg> Proyectos orientados a resolver problemas reales.</li>
             <li class="flex items-center gap-3"><svg class="w-6 h-6 text-indigo-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg> Acompañamiento en tu ruta de aprendizaje.</li>
          </ul>
        </div>
      </div>
    </section>

    <footer class="bg-slate-900 dark:bg-slate-950 text-slate-400 py-12 border-t border-slate-800">
      <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-8">
        <div class="col-span-1 md:col-span-2">
          <span class="text-2xl font-black text-white tracking-tight mb-4 block">TechAcademy</span>
          <p class="max-w-sm">Plataforma educativa para desarrolladores y profesionales de IT. Domina el código, las bases de datos y la tecnología.</p>
        </div>
        <div>
          <h4 class="text-white font-bold mb-4">Enlaces</h4>
          <ul class="space-y-2">
            <li><Link href="/cursos" class="hover:text-white transition">Cursos</Link></li>
            <li><Link href="/nosotros" class="hover:text-white transition">Sobre el Instructor</Link></li>
            <li><Link href="/contacto" class="hover:text-white transition">Contacto</Link></li>
          </ul>
        </div>
        <div>
          <h4 class="text-white font-bold mb-4">Legal</h4>
          <ul class="space-y-2">
            <li><Link href="/terminos" class="hover:text-white transition">Términos de Servicio</Link></li>
            <li><Link href="/privacidad" class="hover:text-white transition">Privacidad</Link></li>
          </ul>
        </div>
      </div>
      <div class="max-w-7xl mx-auto px-6 mt-12 pt-8 border-t border-slate-800 text-center text-sm">
        &copy; 2026 TechAcademy. Desarrollado con Laravel 12 y Vue.js.
      </div>
    </footer>
  </div>
</template>