<template>
  <section id="contact" class="py-20 px-4 bg-gradient-to-br from-gray-950 via-gray-900 to-emerald-950">
    <div class="max-w-4xl mx-auto">
      <!-- Section header -->
      <div class="text-center mb-14">
        <span class="text-emerald-400 text-sm font-semibold tracking-widest uppercase">Contacto</span>
        <h2 class="text-3xl md:text-4xl font-bold text-white mt-2">Hablemos</h2>
        <div class="mt-4 w-16 h-1 bg-emerald-500 mx-auto rounded-full"></div>
        <p class="mt-6 text-gray-400 max-w-lg mx-auto">
          ¿Tienes un proyecto en mente o quieres colaborar? Estoy disponible para nuevas oportunidades.
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-10">
        <!-- Social links -->
        <div class="flex flex-col justify-center gap-5">
          <h3 class="text-white font-semibold text-lg mb-2">Encuéntrame en</h3>
          <a
            v-for="link in socialLinks"
            :key="link.label"
            :href="link.href"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-4 p-4 bg-gray-800/60 hover:bg-gray-800 border border-gray-700 hover:border-emerald-500/50 rounded-xl transition-all duration-200 group"
          >
            <span class="text-2xl">{{ link.icon }}</span>
            <div>
              <p class="text-white font-medium group-hover:text-emerald-400 transition-colors">{{ link.label }}</p>
              <p class="text-gray-400 text-sm">{{ link.handle }}</p>
            </div>
          </a>
        </div>

        <!-- Contact form -->
        <form class="flex flex-col gap-4" @submit.prevent>
          <div>
            <label for="name" class="block text-sm font-medium text-gray-300 mb-1.5">Nombre</label>
            <input
              id="name"
              v-model="form.name"
              type="text"
              placeholder="Tu nombre"
              class="w-full px-4 py-3 bg-gray-800 border border-gray-700 focus:border-emerald-500 text-white placeholder-gray-500 rounded-lg outline-none transition-colors duration-200"
            />
          </div>
          <div>
            <label for="email" class="block text-sm font-medium text-gray-300 mb-1.5">Email</label>
            <input
              id="email"
              v-model="form.email"
              type="email"
              placeholder="tu@email.com"
              class="w-full px-4 py-3 bg-gray-800 border border-gray-700 focus:border-emerald-500 text-white placeholder-gray-500 rounded-lg outline-none transition-colors duration-200"
            />
          </div>
          <div>
            <label for="message" class="block text-sm font-medium text-gray-300 mb-1.5">Mensaje</label>
            <textarea
              id="message"
              v-model="form.message"
              rows="5"
              placeholder="Cuéntame sobre tu proyecto..."
              class="w-full px-4 py-3 bg-gray-800 border border-gray-700 focus:border-emerald-500 text-white placeholder-gray-500 rounded-lg outline-none transition-colors duration-200 resize-none"
            ></textarea>
          </div>
          <button
            type="submit"
            class="w-full py-3 bg-emerald-500 hover:bg-emerald-400 text-white font-semibold rounded-lg transition-colors duration-200 shadow-lg shadow-emerald-500/25"
          >
            Enviar mensaje
          </button>
        </form>
      </div>
    </div>

    <!-- Footer -->
    <div class="mt-16 text-center text-gray-600 text-sm border-t border-gray-800 pt-8">
      <p>© {{ new Date().getFullYear() }} Jesús Montoya · Hecho con Nuxt & Tailwind CSS</p>
    </div>
  </section>
</template>

<script setup>
const form = reactive({
  name: '',
  email: '',
  message: ''
})

const socialLinks = [
  {
    label: 'GitHub',
    handle: 'github.com/jesmontoya',
    href: 'https://github.com',
    icon: '🐙'
  },
  {
    label: 'LinkedIn',
    handle: 'linkedin.com/in/jesmontoya',
    href: 'https://linkedin.com',
    icon: '💼'
  },
  {
    label: 'Email',
    handle: 'jesus@example.com',
    href: 'mailto:jesus@example.com',
    icon: '✉️'
  }
]
</script>
