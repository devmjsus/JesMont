<template>
    <section
        id="contact"
        ref="sectionRef"
        class="py-20 px-4 bg-gradient-to-br from-gray-950 via-gray-900 to-emerald-950"
    >
        <div class="max-w-4xl mx-auto">
            <!-- Section header -->
            <div
                class="text-center mb-14 transition-all duration-700 ease-out"
                :class="
                    isVisible
                        ? 'opacity-100 translate-y-0'
                        : 'opacity-0 translate-y-8'
                "
            >
                <span
                    class="text-emerald-400 text-sm font-semibold tracking-widest uppercase"
                    >Contacto</span
                >
                <h2 class="text-3xl md:text-4xl font-bold text-white mt-2">
                    Hablemos
                </h2>
                <div
                    class="mt-4 w-16 h-1 bg-emerald-500 mx-auto rounded-full"
                ></div>
                <p class="mt-6 text-gray-400 max-w-lg mx-auto">
                    ¿Tienes un proyecto en mente o quieres colaborar? Estoy
                    disponible para nuevas oportunidades.
                </p>
            </div>

            <div class="grid md:grid-cols-2 gap-10">
                <!-- Social links -->
                <div
                    class="flex flex-col justify-center gap-5 transition-all duration-700 ease-out"
                    :class="
                        isVisible
                            ? 'opacity-100 translate-x-0'
                            : 'opacity-0 -translate-x-10'
                    "
                    style="transition-delay: 200ms"
                >
                    <h3 class="text-white font-semibold text-lg mb-2">
                        Encuéntrame en
                    </h3>
                    <a
                        v-for="(link, index) in socialLinks"
                        :key="link.label"
                        :href="link.href"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="flex items-center gap-4 p-4 bg-gray-800/60 hover:bg-gray-800 border border-gray-700 hover:border-emerald-500/50 rounded-xl transition-all duration-200 group"
                        :class="
                            isVisible
                                ? 'opacity-100 translate-x-0'
                                : 'opacity-0 -translate-x-6'
                        "
                        :style="{
                            transitionDelay: isVisible && !entranceDone
                                ? `${300 + index * 80}ms`
                                : '0ms',
                        }"
                    >
                        <span
                            class="w-10 h-10 rounded-lg bg-gray-700/50 group-hover:bg-emerald-500/10 flex items-center justify-center flex-shrink-0 transition-colors duration-200 p-2 text-gray-400 group-hover:text-emerald-400"
                            v-html="link.icon"
                        ></span>
                        <div>
                            <p
                                class="text-white font-medium group-hover:text-emerald-400 transition-colors"
                            >
                                {{ link.label }}
                            </p>
                            <p class="text-gray-400 text-sm">
                                {{ link.handle }}
                            </p>
                        </div>
                    </a>
                </div>

                <!-- Contact form -->
                <form
                    class="flex flex-col gap-4 transition-all duration-700 ease-out"
                    :class="
                        isVisible
                            ? 'opacity-100 translate-x-0'
                            : 'opacity-0 translate-x-10'
                    "
                    style="transition-delay: 250ms"
                    @submit.prevent
                >
                    <div>
                        <label
                            for="name"
                            class="block text-sm font-medium text-gray-300 mb-1.5"
                            >Nombre</label
                        >
                        <input
                            id="name"
                            v-model="form.name"
                            type="text"
                            placeholder="Tu nombre"
                            class="w-full px-4 py-3 bg-gray-800 border border-gray-700 focus:border-emerald-500 text-white placeholder-gray-500 rounded-lg outline-none transition-colors duration-200"
                        />
                    </div>
                    <div>
                        <label
                            for="email"
                            class="block text-sm font-medium text-gray-300 mb-1.5"
                            >Email</label
                        >
                        <input
                            id="email"
                            v-model="form.email"
                            type="email"
                            placeholder="tu@email.com"
                            class="w-full px-4 py-3 bg-gray-800 border border-gray-700 focus:border-emerald-500 text-white placeholder-gray-500 rounded-lg outline-none transition-colors duration-200"
                        />
                    </div>
                    <div>
                        <label
                            for="message"
                            class="block text-sm font-medium text-gray-300 mb-1.5"
                            >Mensaje</label
                        >
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
        <div
            class="mt-16 text-center text-gray-600 text-sm border-t border-gray-800 pt-8"
        >
            <p>
                © {{ new Date().getFullYear() }} Jesús Montoya · Hecho con Nuxt
                & Tailwind CSS
            </p>
        </div>
    </section>
</template>

<script setup>
const sectionRef = ref(null);
const isVisible = ref(false);
const entranceDone = ref(false);

onMounted(() => {
    const observer = new IntersectionObserver(
        ([entry]) => {
            if (entry.isIntersecting) {
                isVisible.value = true;
                // 460ms (último delay) + 200ms (duración) + margen
                setTimeout(() => { entranceDone.value = true; }, 700);
                observer.disconnect();
            }
        },
        { threshold: 0.1 },
    );
    if (sectionRef.value) observer.observe(sectionRef.value);
});

const form = reactive({
    name: "",
    email: "",
    message: "",
});

const socialLinks = [
    {
        label: "GitHub",
        handle: "github.com/devmjsus",
        href: "https://github.com/devmjsus",
        icon: `<svg viewBox="0 0 24 24" fill="currentColor" class="w-full h-full"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>`,
    },
    {
        label: "LinkedIn",
        handle: "linkedin.com/in/jesmontoya",
        href: "https://www.linkedin.com/in/jesus-montoya-castro-324011219/",
        icon: `<svg viewBox="0 0 24 24" fill="currentColor" class="w-full h-full"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>`,
    },
    {
        label: "Email",
        handle: "jesdmont@outlook.com",
        href: "mailto:jesdmont@outlook.com",
        icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="w-full h-full"><path d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/></svg>`,
    },
];
</script>
