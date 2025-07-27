<template>
  <div
    class="mt-6 grid grid-cols-1 lg:grid-cols-2 gap-6"
  >
    <div
      v-for="(project, index) in projects"
      :key="project.id"
      class="bg-white/10 backdrop-blur-lg border border-white/20 p-6 rounded-xl shadow-xl transform transition-all duration-500 hover:scale-105 opacity-0 translate-y-10"
      :ref="el => projectRefs[index] = el"
    >
      <!-- Project Image -->
      <img
        :src="project.image"
        :alt="project.title"
        class="w-full h-48 object-cover rounded-lg mb-4"
      />

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
    title: 'E-Invoice System',
    description: 'I contributed to the E-Invoice System, developed for Salihin’s clients to manage their e-invoicing processes efficiently. My role focused on the front-end, where I was responsible for refining and cleaning up UI layouts to ensure a more organized and user-friendly experience. This involved enhancing visual consistency, fixing layout issues, and improving the overall interface to better align with professional standards and user expectations.',
    tags: ['CodeIgniter 3', 'MySQL', 'Documenting'],
    image: '/images/Einvoice.png'
  },
  {
    id: 2,
    title: 'Suruhanjaya Koperasi Malaysia System',
    description: 'I also worked on the SKM Tender System, an application platform for cooperative membership registration. For this project, I was involved in both front-end and back-end development, with full ownership of the front-end design. I designed the UI from scratch to ensure a clean, accessible, and functional interface, while also supporting the backend integration, demonstrating my ability to blend design thinking with technical implementation.',
    tags: ['CodeIgniter 3', 'MySQL', 'Full-Stack Development'],
    image:'/images/SPK.png'
  },
  {
    id: 3,
    title: 'E-Recruitment System',
    description: 'The E-Recruitment System was developed for Salihin’s internal use to manage job vacancies and streamline the recruitment process. It allows admins to post job openings and manage applications from potential candidates. I was involved in both front-end and back-end development, and took the lead in designing the UI based on the project requirements. My focus was on creating a clear and efficient user interface that simplified the admin workflow while ensuring a smooth experience for job seekers.',
    tags: ['Laravel', 'Vue.js', 'HeidiSQL'],
    image: '/images/ERS.png'
  },
  {
    id: 4,
    title: 'Talenthub',
    description: 'The Talenthub System is a job application platform designed for public use, allowing citizens to explore and apply for job opportunities. During my internship, I focused on enhancing the front-end to create a more polished and user-friendly experience, inspired by the clean and structured layout of platforms like JobStreet. I also contributed to fixing backend bugs to support smoother functionality and ensure a seamless connection between the interface and system processes.',
    tags: ['CodeIgniter 3', 'HeidiSQL'],
    image: '/images/Talenthub.png'
  },
]

const projectRefs = ref([])

onMounted(() => {
  projectRefs.value.forEach((el, i) => {
    const delay = i * 0.6
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
