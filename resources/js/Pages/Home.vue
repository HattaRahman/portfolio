<template>
  <div class="relative min-h-screen overflow-hidden">
    <!-- Video Background -->
    <video
      autoplay
      muted
      loop
      playsinline
      class="fixed inset-0 w-full h-full object-cover z-0"
      style="filter: brightness(0.3) contrast(1.1);"
    >
      <source src="/videos/MotionBg.mp4" type="video/mp4" />
      <!-- Fallback for browsers that don't support video -->
      <div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900"></div>
    </video>

    <!-- Overlay for better text readability -->
    <div class="fixed inset-0 bg-gradient-to-br from-black/40 via-purple-900/30 to-black/40 z-10"></div>

    <!-- Animated Background Elements (on top of video) -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-20">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-purple-500/20 rounded-full blur-3xl animate-pulse"></div>
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-pink-500/20 rounded-full blur-3xl animate-pulse delay-1000"></div>
      <div class="absolute top-1/2 right-1/3 w-64 h-64 bg-blue-500/20 rounded-full blur-3xl animate-pulse delay-2000"></div>
    </div>

    <Overlay />

    <div class="relative z-30">
      <!-- Hero Section -->
      <section class="min-h-screen flex items-center justify-center px-6 relative">
        <div class="text-center space-y-8 max-w-4xl">
          <div class="space-y-4">
            <h1 class="text-6xl md:text-8xl font-black bg-gradient-to-r from-purple-400 via-pink-400 to-purple-400 bg-clip-text text-transparent animate-pulse">
              HATTA
            </h1>
            <p class="text-2xl md:text-3xl text-gray-100 font-light drop-shadow-lg">
              Mohamad Hatta Rahman Bin Borhanuddin
            </p>
          </div>

          <div class="flex flex-wrap justify-center gap-4 text-sm">
            <span class="px-4 py-2 rounded-full bg-purple-500/30 text-purple-200 border border-purple-500/50 backdrop-blur-sm">
              Frontend Developer
            </span>
            <span class="px-4 py-2 rounded-full bg-pink-500/30 text-pink-200 border border-pink-500/50 backdrop-blur-sm">
              UI/UX Designer
            </span>
            <span class="px-4 py-2 rounded-full bg-blue-500/30 text-blue-200 border border-blue-500/50 backdrop-blur-sm">
              Data Analyst
            </span>
            <span class="px-4 py-2 rounded-full bg-green-500/30 text-green-200 border border-green-500/50 backdrop-blur-sm">
              Software Analyst
            </span>
          </div>

          <div class="flex justify-center space-x-6">
            <a href="#about" class="group relative px-8 py-3 rounded-full bg-gradient-to-r from-purple-500 to-pink-500 text-white font-semibold hover:scale-105 transition-transform duration-300 shadow-lg">
              <span class="relative z-10">Explore My Work</span>
              <div class="absolute inset-0 rounded-full bg-gradient-to-r from-purple-600 to-pink-600 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
            </a>
            <a href="#contact" class="px-8 py-3 rounded-full border border-purple-500/50 text-purple-200 hover:bg-purple-500/20 transition-all duration-300 backdrop-blur-sm">
              Get In Touch
            </a>
          </div>
        </div>

        <!-- Scroll indicator -->
        <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 text-gray-300 animate-bounce">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
          </svg>
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-32 px-6 relative">
        <div class="absolute inset-0 bg-black/60 backdrop-blur-sm"></div>
        <div class="max-w-6xl mx-auto relative z-10">
          <div class="grid md:grid-cols-2 gap-16 items-center">
            <div class="space-y-8">
              <div class="space-y-4">
                <h2 class="text-5xl font-bold text-white">
                  About <span class="text-purple-400">Me</span>
                </h2>
                <div class="w-20 h-1 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full"></div>
              </div>

              <p class="text-xl text-gray-200 leading-relaxed">
                Fresh graduate in Computer Science (Software Engineering) from UMPSA with hands-on experience in full-stack development, UI/UX design, data Analyst, and software Analyst. Also experienced in developing end-to-end systems, integrating complex technologies, and delivering impactful digital solutions grounded in real-world use cases.
              </p>

              <div class="grid grid-cols-2 gap-6">
                <div class="space-y-2">
                  <h3 class="text-purple-400 font-semibold">Location</h3>
                  <p class="text-gray-200">Malaysia</p>
                </div>
                <div class="space-y-2">
                  <h3 class="text-purple-400 font-semibold">Focus</h3>
                  <p class="text-gray-200">Frontend Development</p>
                </div>
              </div>
            </div>

            <div class="relative">
                <div class="w-80 h-80 mx-auto rounded-3xl bg-gradient-to-br from-purple-500/30 to-pink-500/30 backdrop-blur-sm border border-purple-500/50 flex items-center justify-center overflow-hidden">
                    <!-- Replace this emoji with your image -->
                    <img src="/images/gambo.jpg" alt="Your Name" class="w-full h-full object-cover rounded-3xl" />
                </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Experience Section -->
      <section id="experience" class="py-32 px-6 relative">
        <div class="absolute inset-0 bg-black/70 backdrop-blur-sm"></div>
        <div class="max-w-6xl mx-auto relative z-10">
          <div class="text-center space-y-4 mb-16">
            <h2 class="text-5xl font-bold text-white">
              My <span class="text-purple-400">Experience</span>
            </h2>
            <div class="w-20 h-1 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full mx-auto"></div>
          </div>

          <div class="space-y-12">
            <div class="group relative">
              <div class="flex items-start space-x-6">
                <div class="flex-shrink-0 w-16 h-16 rounded-full bg-gradient-to-br from-purple-500 to-pink-500 flex items-center justify-center">
                  <span class="text-2xl">💼</span>
                </div>
                <div class="flex-1 space-y-4">
                  <div class="bg-gray-800/70 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 group-hover:border-purple-500/50 transition-all duration-300">
                    <h3 class="text-2xl font-bold text-white mb-2">Internship at Salihin IT Curation</h3>
                    <p class="text-purple-400 mb-4">Full-Stack Developer Intern</p>
                    <p class="text-gray-200 leading-relaxed">
                      Gained hands-on experience in full-stack development using Laravel, CodeIgniter3 and Vue.js. Worked on real-world projects, collaborating with experienced developers and contributing to production applications. Assisted in developing and optimizing web applications. Helped resolve technical issues with databases, APIs, and UI components.
                    </p>
                    <div class="mt-6 flex flex-wrap gap-2">
                      <span class="px-3 py-1 rounded-full bg-purple-500/30 text-purple-200 text-sm">Laravel</span>
                      <span class="px-3 py-1 rounded-full bg-pink-500/30 text-pink-200 text-sm">Vue.js</span>
                      <span class="px-3 py-1 rounded-full bg-blue-500/30 text-blue-200 text-sm">Full-Stack</span>
                    </div>
                    <ProjectCards />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

<Skills/>
      <!-- Projects Section -->
      <section id="projects" class="py-32 px-6 relative">
        <div class="absolute inset-0 bg-black/60 backdrop-blur-sm"></div>
        <div class="max-w-6xl mx-auto relative z-10">
          <div class="text-center space-y-4 mb-16">
            <h2 class="text-5xl font-bold text-white">
              My <span class="text-purple-400">Projects</span>
            </h2>
            <div class="w-20 h-1 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full mx-auto"></div>
            <p class="text-xl text-gray-200 max-w-2xl mx-auto">
              Here are some things I've built that showcase my skills and passion for development
            </p>
          </div>

          <ProjectCards />
        </div>
      </section>

      <!-- Contact Section -->
      <section id="contact" class="py-32 px-6 relative">
        <div class="absolute inset-0 bg-black/70 backdrop-blur-sm"></div>
        <div class="max-w-4xl mx-auto text-center relative z-10">
          <div class="space-y-8">
            <div class="space-y-4">
              <h2 class="text-5xl font-bold text-white">
                Let's <span class="text-purple-400">Connect</span>
              </h2>
              <div class="w-20 h-1 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full mx-auto"></div>
              <p class="text-xl text-gray-200 max-w-2xl mx-auto">
                Ready to bring your ideas to life? Let's discuss how we can work together to create something amazing.
              </p>
            </div>

            <div class="flex flex-col sm:flex-row items-center justify-center space-y-4 sm:space-y-0 sm:space-x-6">
              <!-- Email Button -->
              <a href="mailto:hattarahman1@gmail.com" class="group flex items-center space-x-3 px-6 py-3 rounded-full bg-gradient-to-r from-purple-500 to-pink-500 text-white font-semibold hover:scale-105 transition-transform duration-300">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"></path>
                  <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"></path>
                </svg>
                <span>Email</span>
              </a>

              <!-- LinkedIn Button -->
              <a href="https://www.linkedin.com/in/Hatta-Rahman" target="_blank" rel="noopener noreferrer" class="group flex items-center space-x-3 px-6 py-3 rounded-full border border-purple-500/50 text-purple-300 hover:bg-purple-500/10 transition-all duration-300 backdrop-blur-sm">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
                <span>LinkedIn</span>
              </a>

              <!-- Resume Button -->
              <a href="/resume.pdf" download class="group flex items-center space-x-3 px-6 py-3 rounded-full border border-purple-500/50 text-purple-300 hover:bg-purple-500/10 transition-all duration-300 backdrop-blur-sm">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd"/>
                </svg>
                <span>Download Resume</span>
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- Footer -->
      <footer class="py-12 px-6 border-t border-gray-800/50 relative">
        <div class="absolute inset-0 bg-black/60 backdrop-blur-sm"></div>
        <div class="max-w-6xl mx-auto text-center relative z-10">
          <p class="text-gray-300">
            © 2024 Hatta. Built with ❤️ using Vue.js
          </p>
        </div>
      </footer>
    </div>
  </div>
</template>

<script setup>
import Overlay from '@/Components/Overlay.vue'
import ProjectCards from '@/Components/ProjectCards.vue'
import Skills from '@/Components/Skills.vue'
import PortfolioLayout from '@/Layouts/AppLayout.vue'
import gsap from 'gsap'
import { onMounted } from 'vue'

defineOptions({ layout: PortfolioLayout })

onMounted(() => {
  // Enhanced animations with staggered timing
  gsap.from('h1', {
    opacity: 0,
    y: 100,
    duration: 1.5,
    ease: 'power3.out',
    delay: 0.5
  })

  gsap.from('h1 + p', {
    opacity: 0,
    y: 50,
    duration: 1,
    ease: 'power2.out',
    delay: 1
  })

  gsap.from('.flex.flex-wrap', {
    opacity: 0,
    y: 30,
    duration: 0.8,
    ease: 'power2.out',
    delay: 1.3
  })

  gsap.from('.flex.justify-center.space-x-6', {
    opacity: 0,
    y: 30,
    duration: 0.8,
    ease: 'power2.out',
    delay: 1.6
  })

  // Scroll-triggered animations
  gsap.registerPlugin(ScrollTrigger)

  gsap.from('#about', {
    opacity: 0,
    y: 100,
    duration: 1.2,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: '#about',
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play none none reverse'
    }
  })

  gsap.from('#experience', {
    opacity: 0,
    y: 100,
    duration: 1.2,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: '#experience',
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play none none reverse'
    }
  })

  gsap.from('#projects', {
    opacity: 0,
    y: 100,
    duration: 1.2,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: '#projects',
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play none none reverse'
    }
  })

  gsap.from('#contact', {
    opacity: 0,
    y: 100,
    duration: 1.2,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: '#contact',
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play none none reverse'
    }
  })
})
</script>

<style scoped>
/* Add smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #1a1a1a;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(to bottom, #8b5cf6, #ec4899);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(to bottom, #7c3aed, #db2777);
}

/* Enhanced gradient text animation */
@keyframes gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.animate-gradient {
  background-size: 200% 200%;
  animation: gradient 3s ease infinite;
}

/* Floating animation for background elements */
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

/* Ensure video covers the entire background */
video {
  min-width: 100%;
  min-height: 100%;
}

        .expertise-bar {
            height: 4px;
            background: linear-gradient(90deg, #6b46c1, #ec4899);
            border-radius: 2px;
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .skill-card:hover .expertise-bar {
            transform: scaleX(1.1);
        }

        .skill-image {
            width: 40px;
            height: 40px;
            object-fit: cover;
            border-radius: 8px;
        }

        .skill-image-placeholder {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 12px;
            font-weight: bold;
        }
</style>
