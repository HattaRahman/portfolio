<template>
  <div class="min-h-screen font-sans text-white transition-colors duration-300 bg-black">
    <!-- HEADER -->
    <header class="fixed top-0 w-full z-50 bg-black/20 backdrop-blur-xl border-b border-white/10">
      <div class="flex justify-between items-center px-6 py-4 max-w-7xl mx-auto">
        <!-- Logo/Brand -->
        <div class="text-xl font-bold text-white">
          HATTA
        </div>

        <!-- Right Side Container -->
        <div class="flex items-center gap-8">
          <!-- Desktop Nav -->
          <nav class="hidden md:flex gap-8 font-medium">
            <a
              @click="handleNavClick('about', $event)"
              href="#about"
              :class="activeSection === 'about' ? 'text-purple-400 border-b-2 border-purple-400' : 'text-gray-300 hover:text-white'"
              class="transition-all duration-300 pb-1"
            >
              About
            </a>
            <a
              @click="handleNavClick('experience', $event)"
              href="#experience"
              :class="activeSection === 'experience' ? 'text-purple-400 border-b-2 border-purple-400' : 'text-gray-300 hover:text-white'"
              class="transition-all duration-300 pb-1"
            >
              Experience
            </a>
            <a
              @click="handleNavClick('projects', $event)"
              href="#projects"
              :class="activeSection === 'projects' ? 'text-purple-400 border-b-2 border-purple-400' : 'text-gray-300 hover:text-white'"
              class="transition-all duration-300 pb-1"
            >
              Projects
            </a>
            <a
              @click="handleNavClick('contact', $event)"
              href="#contact"
              :class="activeSection === 'contact' ? 'text-purple-400 border-b-2 border-purple-400' : 'text-gray-300 hover:text-white'"
              class="transition-all duration-300 pb-1"
            >
              Contact
            </a>
          </nav>

          <!-- Theme Toggle & Menu -->
          <div class="flex items-center gap-3">
          <!-- Hamburger Menu -->
          <button
            @click="open = !open"
            class="md:hidden text-white hover:text-purple-400 transition-colors duration-300"
          >
            <svg v-if="!open" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Nav -->
      <transition
        enter-active-class="transition-all duration-300 ease-out"
        enter-from-class="opacity-0 -translate-y-2"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition-all duration-200 ease-in"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 -translate-y-2"
      >
        <div v-if="open" class="md:hidden bg-black/90 backdrop-blur-xl px-6 pt-4 pb-6 text-center border-t border-white/10">
          <a
            @click="handleNavClick('about', $event)"
            href="#about"
            :class="activeSection === 'about' ? 'text-purple-400' : 'text-gray-300 hover:text-white'"
            class="block py-3 text-lg transition-colors duration-300"
          >
            About
          </a>
          <a
            @click="handleNavClick('experience', $event)"
            href="#experience"
            :class="activeSection === 'experience' ? 'text-purple-400' : 'text-gray-300 hover:text-white'"
            class="block py-3 text-lg transition-colors duration-300"
          >
            Experience
          </a>
          <a
            @click="handleNavClick('projects', $event)"
            href="#projects"
            :class="activeSection === 'projects' ? 'text-purple-400' : 'text-gray-300 hover:text-white'"
            class="block py-3 text-lg transition-colors duration-300"
          >
            Projects
          </a>
          <a
            @click="handleNavClick('contact', $event)"
            href="#contact"
            :class="activeSection === 'contact' ? 'text-purple-400' : 'text-gray-300 hover:text-white'"
            class="block py-3 text-lg transition-colors duration-300"
          >
            Contact
          </a>
        </div>
      </transition>
      </div>
    </header>

    <!-- MAIN CONTENT -->
    <main class="pt-20 px-6 max-w-7xl mx-auto relative">
      <!-- Background overlay for better text readability over video -->
      <div class="fixed inset-0 bg-black/40 pointer-events-none z-10"></div>

      <!-- Content wrapper with higher z-index -->
      <div class="relative z-20">
        <slot />
      </div>
    </main>

    <!-- FOOTER -->
    <footer class="relative z-20 mt-20 p-6 text-center border-t border-white/10 bg-black/20 backdrop-blur-sm">
      <div class="text-sm text-gray-400 mb-2">
        &copy; {{ currentYear }} Hatta's Portfolio. All rights reserved.
      </div>
      <div class="flex justify-center gap-6 text-gray-400">
        <a href="#" class="hover:text-purple-400 transition-colors duration-300">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
          </svg>
        </a>
        <a href="#" class="hover:text-purple-400 transition-colors duration-300">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </a>
        <a href="#" class="hover:text-purple-400 transition-colors duration-300">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
        </a>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue'

const lightMode = ref(false)
const open = ref(false)
const currentYear = new Date().getFullYear()
const activeSection = ref('about')

let observer = null

function toggleTheme() {
  lightMode.value = !lightMode.value
  document.documentElement.classList.toggle('light', lightMode.value)
}

function closeMenu() {
  open.value = false
}

function handleNavClick(sectionId, event) {
  event.preventDefault()

  // Immediately update active section
  activeSection.value = sectionId

  // Close mobile menu
  closeMenu()

  // Find and scroll to target
  const target = document.getElementById(sectionId)
  if (target) {
    target.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    })
  }

  // Debug log
  console.log('Active section set to:', sectionId)
}

function updateActiveSection() {
  const sections = document.querySelectorAll('section[id]')
  if (sections.length === 0) return

  const scrollY = window.scrollY
  const windowHeight = window.innerHeight

  let currentSection = 'about' // default

  sections.forEach((section) => {
    const rect = section.getBoundingClientRect()
    const sectionTop = rect.top + scrollY
    const sectionHeight = rect.height

    // A section is active if the top of the section is above the middle of the viewport
    // and the bottom is below the middle
    if (scrollY + windowHeight / 2 >= sectionTop &&
        scrollY + windowHeight / 2 < sectionTop + sectionHeight) {
      currentSection = section.id
    }
  })

  if (activeSection.value !== currentSection) {
    activeSection.value = currentSection
    console.log('Active section updated to:', currentSection)
  }
}

function handleScroll() {
  updateActiveSection()
}

onMounted(async () => {
  // Wait for DOM to be ready
  await nextTick()

  // Set initial dark theme
  document.documentElement.classList.add('dark')

  // Add scroll event listener
  window.addEventListener('scroll', handleScroll, { passive: true })

  // Setup intersection observer after a short delay to ensure sections exist
  setTimeout(() => {
    const sections = document.querySelectorAll('section[id]')
    console.log('Found sections:', sections.length)

    if (sections.length > 0) {
      observer = new IntersectionObserver(
        (entries) => {
          // Find the entry with the highest intersection ratio
          let maxRatio = 0
          let activeEntry = null

          entries.forEach((entry) => {
            if (entry.isIntersecting && entry.intersectionRatio > maxRatio) {
              maxRatio = entry.intersectionRatio
              activeEntry = entry
            }
          })

          if (activeEntry && maxRatio > 0.3) {
            activeSection.value = activeEntry.target.id
            console.log('Intersection observer updated active section to:', activeEntry.target.id)
          }
        },
        {
          threshold: [0.1, 0.3, 0.5, 0.7, 0.9],
          rootMargin: '-100px 0px -100px 0px'
        }
      )

      sections.forEach((section) => observer.observe(section))

      // Set initial active section
      updateActiveSection()
    } else {
      console.log('No sections found, using scroll-based detection only')
    }
  }, 500) // Increased delay to ensure sections are loaded
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  if (observer) {
    observer.disconnect()
  }
})
</script>

<style scoped>
/* Additional dark theme enhancements */
.bg-gradient-to-r {
  background: linear-gradient(135deg, #a855f7 0%, #ec4899 100%);
}

/* Smooth transitions for all interactive elements */
* {
  transition: all 0.3s ease;
}

/* Enhanced backdrop blur for better video background compatibility */
.backdrop-blur-xl {
  backdrop-filter: blur(24px);
}

/* Custom scrollbar for dark theme */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
}

::-webkit-scrollbar-thumb {
  background: rgba(168, 85, 247, 0.5);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(168, 85, 247, 0.7);
}
</style>
