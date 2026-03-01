<template>
  <section class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-gray-950 via-gray-900 to-emerald-950 px-4 py-20">
    <!-- Background decoration -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute -top-40 -right-40 w-96 h-96 bg-emerald-500/10 rounded-full blur-3xl"></div>
      <div class="absolute -bottom-40 -left-40 w-96 h-96 bg-teal-500/10 rounded-full blur-3xl"></div>
    </div>

    <div class="relative z-10 max-w-4xl mx-auto text-center">
      <!-- Avatar -->
      <div class="mb-8 flex justify-center">
        <div class="w-32 h-32 md:w-40 md:h-40 rounded-full bg-gradient-to-br from-emerald-400 to-teal-600 flex items-center justify-center text-5xl md:text-6xl font-bold text-white shadow-2xl ring-4 ring-emerald-500/30">
          JM
        </div>
      </div>

      <!-- Name -->
      <h1 class="text-4xl md:text-6xl lg:text-7xl font-bold text-white mb-4 tracking-tight">
        Jesús
        <span class="bg-gradient-to-r from-emerald-400 to-teal-400 bg-clip-text text-transparent">
          Montoya
        </span>
      </h1>

      <!-- Role -->
      <p class="text-lg md:text-2xl text-emerald-400 font-medium mb-6 tracking-wide">
        Desarrollador Web Full Stack
      </p>

      <!-- Description -->
      <p class="text-gray-400 text-base md:text-lg max-w-2xl mx-auto leading-relaxed mb-10">
        Apasionado por crear experiencias web modernas y escalables. Especializado en el ecosistema Vue/Nuxt con enfoque en código limpio, rendimiento y diseño accesible.
      </p>

      <!-- CTAs -->
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#contact"
          class="px-8 py-3 bg-emerald-500 hover:bg-emerald-400 text-white font-semibold rounded-lg transition-colors duration-200 shadow-lg shadow-emerald-500/25"
        >
          Contáctame
        </a>
        <a
          href="#skills"
          class="px-8 py-3 border border-gray-600 hover:border-emerald-500 text-gray-300 hover:text-emerald-400 font-semibold rounded-lg transition-colors duration-200"
        >
          Ver habilidades
        </a>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 text-gray-500 animate-bounce">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
      </svg>
    </div>
  </section>
</template>
