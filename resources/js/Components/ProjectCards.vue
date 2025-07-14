<template>
  <div
    class="mt-6 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6"
  >
    <div
      v-for="(project, index) in projects"
      :key="project.id"
      class="bg-white/10 backdrop-blur-lg border border-white/20 p-6 rounded-xl shadow-xl transform transition-all duration-500 hover:scale-105 opacity-0 translate-y-10"
      :ref="el => projectRefs[index] = el"
    >
      <h3 class="text-xl font-semibold text-purple-300">{{ project.title }}</h3>
      <p class="mt-2 text-gray-200">{{ project.description }}</p>
      <div class="mt-4 flex flex-wrap gap-2">
        <span
          v-for="tag in project.tags"
          :key="tag"
          class="bg-purple-600/30 text-sm px-2 py-1 rounded-full text-purple-100"
        >
          #{{ tag }}
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const projects = [
  {
    id: 1,
    title: 'E-Invoicing System',
    description: 'A modern system to manage and send invoices efficiently.',
    tags: ['Laravel', 'Vue', 'MySQL'],
  },
  {
    id: 2,
    title: 'UI/UX Coop Prototype',
    description: 'Interactive UI design for cooperative systems.',
    tags: ['Figma', 'UX Design'],
  },
  {
    id: 3,
    title: 'Portfolio Website',
    description: 'One-page responsive site built with modern tools.',
    tags: ['Laravel', 'Inertia', 'Tailwind'],
  },
]

const projectRefs = ref([])

onMounted(() => {
  projectRefs.value.forEach((el, i) => {
    const delay = i * 0.3
    const observer = new IntersectionObserver(
      entries => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            el.classList.add('opacity-100', 'translate-y-0')
          }
        })
      },
      { threshold: 0.1 }
    )
    observer.observe(el)
  })
})
</script>

<style scoped>
.opacity-100 {
  opacity: 1 !important;
  transform: translateY(0) !important;
  transition: all 0.6s ease-out;
}
</style>
