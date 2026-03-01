<template>
  <section id="skills" class="py-20 px-4 bg-gray-900">
    <div class="max-w-5xl mx-auto">
      <!-- Section header -->
      <div class="text-center mb-14">
        <span class="text-emerald-400 text-sm font-semibold tracking-widest uppercase">Tecnologías</span>
        <h2 class="text-3xl md:text-4xl font-bold text-white mt-2">Mis Habilidades</h2>
        <div class="mt-4 w-16 h-1 bg-emerald-500 mx-auto rounded-full"></div>
      </div>

      <!-- Skills grid -->
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
        <div
          v-for="skill in skills"
          :key="skill.name"
          class="group flex flex-col items-center gap-3 p-5 bg-gray-800 hover:bg-gray-750 border border-gray-700 hover:border-emerald-500/50 rounded-xl transition-all duration-200 hover:-translate-y-1 hover:shadow-lg hover:shadow-emerald-500/10"
        >
          <span class="text-3xl">{{ skill.icon }}</span>
          <span class="text-sm font-medium text-gray-300 group-hover:text-white transition-colors">
            {{ skill.name }}
          </span>
          <span class="text-xs text-emerald-400/70 font-medium">{{ skill.level }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  { name: 'Vue.js', icon: '💚', level: 'Avanzado' },
  { name: 'Nuxt', icon: '🟢', level: 'Avanzado' },
  { name: 'JavaScript', icon: '🟡', level: 'Avanzado' },
  { name: 'TypeScript', icon: '🔵', level: 'Intermedio' },
  { name: 'HTML5', icon: '🟠', level: 'Avanzado' },
  { name: 'CSS3', icon: '🔷', level: 'Avanzado' },
  { name: 'Tailwind CSS', icon: '🌊', level: 'Avanzado' },
  { name: 'Node.js', icon: '🟩', level: 'Intermedio' },
  { name: 'Git', icon: '🔧', level: 'Avanzado' },
  { name: 'REST APIs', icon: '⚡', level: 'Intermedio' },
  { name: 'PostgreSQL', icon: '🐘', level: 'Básico' },
  { name: 'Docker', icon: '🐳', level: 'Básico' },
]
</script>
