<template>
  <div>
    <Overlay />
    <div class="space-y-24">
      <!-- About -->
      <section id="about" class="pt-40 pb-24 px-6 bg-black text-white">
        <h2 class="text-4xl font-bold text-purple-400">👋 About Me</h2>
        <p class="mt-4 text-lg max-w-3xl">
          I’m Hatta, a passionate developer from Malaysia...
        </p>
      </section>

      <!-- Experience -->
      <section id="experience" class="pt-20 pb-24 px-6 bg-gray-900 text-white">
        <h2 class="text-4xl font-bold text-purple-400">💼 Experience</h2>
        <ul class="mt-4 space-y-2 text-lg">
          <li>- Internship at Salihin IT Curation</li>
          <li>- Full-stack development with Laravel, Vue.js</li>
        </ul>
      </section>

      <!-- Projects -->
      <section id="projects" class="pt-20 pb-24 px-6 bg-black text-white">
        <h2 class="text-4xl font-bold text-purple-400">🛠 Projects</h2>
        <p class="mt-4 text-lg">Here are some things I’ve built:</p>
      </section>

      <!-- Contact -->
      <section id="contact" class="pt-20 pb-24 px-6 bg-gray-900 text-white">
        <h2 class="text-4xl font-bold text-purple-400">📬 Contact</h2>
        <p class="mt-4 text-lg">Email: hatta@example.com</p>
        <a
            href="/resume.pdf"
            download
            class="mt-4 inline-block text-sm px-4 py-2 rounded bg-pink-500 hover:bg-pink-600 font-bold text-white"
            >
            📄 Download Resume
        </a>
      </section>
    </div>
  </div>
</template>


<script setup>
import Overlay from '@/Components/Overlay.vue'
import PortfolioLayout from '@/Layouts/AppLayout.vue'
import gsap from 'gsap'
import { onMounted } from 'vue'

defineOptions({ layout: PortfolioLayout })

onMounted(() => {
  gsap.from('#about', { opacity: 0, y: 50, duration: 1, delay: 1.6 })
  gsap.from('#experience', { opacity: 0, y: 50, duration: 1, delay: 2 })
  gsap.from('#projects', { opacity: 0, y: 50, duration: 1, delay: 2.6 })
  gsap.from('#contact', { opacity: 0, y: 50, duration: 1, delay: 3 })
})
</script>

