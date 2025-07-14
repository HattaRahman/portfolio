<template>
  <div class="min-h-screen font-sans text-gray-800 dark:text-white transition-colors duration-300 bg-white dark:bg-black">
    <!-- HEADER -->
    <header class="fixed top-0 w-full z-50 bg-white/30 dark:bg-black/30 backdrop-blur-md shadow-sm">
      <div class="flex justify-between items-center px-6 py-4 max-w-7xl mx-auto">

        <!-- Desktop Nav -->
        <nav class="hidden md:flex gap-6 font-medium">
          <a href="#about" :class="activeSection === 'about' ? 'text-indigo-500' : ''">About</a>
          <a href="#experience" :class="activeSection === 'experience' ? 'text-indigo-500' : ''">Experience</a>
          <a href="#projects" :class="activeSection === 'projects' ? 'text-indigo-500' : ''">Projects</a>
          <a href="#contact" :class="activeSection === 'contact' ? 'text-indigo-500' : ''">Contact</a>
        </nav>


        <!-- Theme + Toggle -->
        <div class="flex items-center gap-3 ml-auto">
          <!-- Dark Mode Button -->
          <button
            @click="dark = !dark"
            class="px-3 py-1 text-sm rounded bg-purple-500 hover:bg-purple-600 text-white transition"
          >
            {{ dark ? '🌞 Light' : '🌙 Dark' }}
          </button>

          <!-- Hamburger Menu -->
          <button @click="open = !open" class="md:hidden text-gray-800 dark:text-white">
            <svg v-if="!open" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none"
              viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none"
              viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Nav -->
      <transition name="fade">
        <div v-if="open" class="md:hidden bg-white/80 dark:bg-black/90 px-6 pt-4 pb-6 text-center shadow-md">
          <a @click="closeMenu" href="#about" :class="activeSection === 'about' ? 'text-purple-500' : ''" class="block py-2">About</a>
          <a @click="closeMenu" href="#experience" :class="activeSection === 'experience' ? 'text-purple-500' : ''" class="block py-2">Experience</a>
          <a @click="closeMenu" href="#projects" :class="activeSection === 'projects' ? 'text-purple-500' : ''" class="block py-2">Projects</a>
          <a @click="closeMenu" href="#contact" :class="activeSection === 'contact' ? 'text-purple-500' : ''" class="block py-2">Contact</a>
        </div>
      </transition>
    </header>

    <!-- MAIN -->
    <main class="pt-28 px-6 max-w-7xl mx-auto">
      <slot />
    </main>

    <!-- FOOTER -->
    <footer class="mt-20 p-4 text-center text-sm text-gray-500 dark:text-gray-400">
      &copy; {{ currentYear }} Hatta's Portfolio. All rights reserved.
    </footer>
  </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue'

const dark = ref(false)
const open = ref(false)
const currentYear = new Date().getFullYear()
const activeSection = ref('about')

watch(dark, (val) => {
  document.documentElement.classList.toggle('dark', val)
})

function closeMenu() {
  open.value = false
}

onMounted(() => {
  const sections = document.querySelectorAll('section[id]')
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    { threshold: 0.6 }
  )

  sections.forEach((section) => observer.observe(section))
})
</script>
