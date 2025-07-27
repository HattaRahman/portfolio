<template>
    <div class="mt-6 grid grid-cols-1 lg:grid-cols-2 gap-6">
        <div
            v-for="(project, index) in projects"
            :key="project.id"
            class="bg-white/10 backdrop-blur-lg border border-white/20 p-6 rounded-xl shadow-xl transform transition-all duration-500 hover:scale-105 opacity-0 translate-y-10"
            :ref="(el) => (projectRefs[index] = el)"
        >
            <!-- Image Carousel -->
            <div class="relative w-full h-70 mb-4 overflow-hidden rounded-lg">
                <!-- Images Container -->
                <div
                    class="flex transition-transform duration-300 ease-in-out h-full"
                    :style="{
                        transform: `translateX(-${
                            currentImageIndex[project.id] * 100
                        }%)`,
                    }"
                >
                    <img
                        v-for="(image, imgIndex) in project.images"
                        :key="imgIndex"
                        :src="image"
                        :alt="`${project.title} - Image ${imgIndex + 1}`"
                        class="w-full h-full object-cover flex-shrink-0"
                    />
                </div>

                <!-- Navigation Buttons -->
                <template v-if="project.images.length > 1">
                    <!-- Previous Button -->
                    <button
                        @click="
                            handlePreviousImage(
                                project.id,
                                project.images.length
                            )
                        "
                        class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-black/50 hover:bg-black/70 text-white p-2 rounded-full transition-all duration-200 opacity-80 hover:opacity-100"
                    >
                        <svg
                            class="w-5 h-5"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M15 19l-7-7 7-7"
                            ></path>
                        </svg>
                    </button>

                    <!-- Next Button -->
                    <button
                        @click="
                            handleNextImage(project.id, project.images.length)
                        "
                        class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-black/50 hover:bg-black/70 text-white p-2 rounded-full transition-all duration-200 opacity-80 hover:opacity-100"
                    >
                        <svg
                            class="w-5 h-5"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path>
                        </svg>
                    </button>

                    <!-- Image Indicators -->
                    <div
                        class="absolute bottom-2 left-1/2 transform -translate-x-1/2 flex space-x-2"
                    >
                        <button
                            v-for="(image, imgIndex) in project.images"
                            :key="imgIndex"
                            @click="setCurrentImage(project.id, imgIndex)"
                            class="w-2 h-2 rounded-full transition-all duration-200"
                            :class="
                                currentImageIndex[project.id] === imgIndex
                                    ? 'bg-white'
                                    : 'bg-white/50 hover:bg-white/75'
                            "
                        ></button>
                    </div>

                    <!-- Image Counter -->
                    <div
                        class="absolute top-2 right-2 bg-black/50 text-white text-sm px-2 py-1 rounded"
                    >
                        {{ currentImageIndex[project.id] + 1 }} /
                        {{ project.images.length }}
                    </div>
                </template>
            </div>

            <h3 class="text-xl font-semibold text-purple-300">
                {{ project.title }}
            </h3>
            <p class="mt-2 text-gray-200">{{ project.description }}</p>
            <div class="mt-4 flex flex-wrap gap-2">
<!-- Project Links -->
      <div class="mt-4 mb-4 flex flex-wrap gap-3" v-if="project.figmaLink || project.prototypeLink">
        <!-- Figma Link -->
        <a
          v-if="project.figmaLink"
          :href="project.figmaLink"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 text-purple-300 hover:text-purple-100 transition-colors duration-200 group"
        >
          <!-- Figma Logo SVG -->
          <svg
            class="w-5 h-5 group-hover:scale-110 transition-transform duration-200"
            viewBox="0 0 24 24"
            fill="currentColor"
          >
            <path d="M8 24c2.208 0 4-1.792 4-4v-4H8c-2.208 0-4 1.792-4 4s1.792 4 4 4z"/>
            <path d="M4 12c0-2.208 1.792-4 4-4h4v8H8c-2.208 0-4-1.792-4-4z"/>
            <path d="M4 4c0-2.208 1.792-4 4-4h4v8H8C5.792 8 4 6.208 4 4z"/>
            <path d="M12 0h4c2.208 0 4 1.792 4 4s-1.792 4-4 4h-4V0z"/>
            <path d="M20 12c0 2.208-1.792 4-4 4s-4-1.792-4-4 1.792-4 4-4 4 1.792 4 4z"/>
          </svg>
          <span class="text-sm font-medium">View Design</span>
        </a>

        <!-- Prototype Link -->
        <a
          v-if="project.prototypeLink"
          :href="project.prototypeLink"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 text-green-300 hover:text-green-100 transition-colors duration-200 group"
        >
          <!-- Play/Prototype Icon SVG -->
          <svg
            class="w-5 h-5 group-hover:scale-110 transition-transform duration-200"
            viewBox="0 0 24 24"
            fill="currentColor"
          >
            <path d="M8 5v14l11-7z"/>
          </svg>
          <span class="text-sm font-medium">Live Demo</span>
        </a>
      </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { onMounted, ref, reactive, onUnmounted } from "vue";

const projects = [
    {
        id: 1,
        title: "Kitty’s Cupid",
        description:
            "Kitty’s Cupid: Cat Dating App, is a mobile application I designed using Figma and developed with FlutterFlow as my final year project at UMP. It connects cat owners looking for suitable partners for their cats, either for breeding or companionship, while also fostering a friendly community of cat enthusiasts. The project showcases my end-to-end UI/UX process, from wireframing and prototyping to interface design and real app development, blending user-friendly design with a playful and caring concept.",
        images: [
            "/images/Kitty/Kitty4.png",
            "/images/Kitty/Kitty5.png",
            "/images/Kitty/Kitty6.png",
            "/images/Kitty/Kitty1.png",
            "/images/Kitty/Kitty2.png",
            "/images/Kitty/Kitty3.png",
        ],
        figmaLink:
            "https://www.figma.com/design/ELIlt5PMj0W3vQD4FnL1k7/Kitty-s-Cupid?node-id=0-1&t=xe3e1QxqtXhA2KWX-1",
        prototypeLink:
            'https://www.figma.com/proto/d1hglv9W7BYGTCKhtb8dAq/Prototype-FYP-Kitty-s-Cupid?node-id=26-14&starting-point-node-id=26%3A14&t=qsA3cUYXhrcJCknO-1'
    },
    {
        id: 2,
        title: "MeowDate",
        description:
            "MeowDate is a refreshed version of my earlier project, Kitty’s Cupid, redesigned purely out of personal interest to explore a more modern and polished UI. Still in progress, this project reflects my growth in UI design, aiming to reimagine the original concept with a cleaner, more realistic app feel while keeping the charm and purpose of connecting cat lovers intact.",
        tags: ["CodeIgniter 3", "MySQL", "Full-Stack Development"],
        images: [
            "/images/Meowdate/Meowdate1.png",
            "/images/Meowdate/Meowdate2.png",
            "/images/Meowdate/Meowdate3.png",
        ],
        figmaLink:
            "https://www.figma.com/design/WhcUgNRs8Utm94I2yQHyIk/MeowDate-new?t=eFCxFZdnSqGWdPL6-1",
    },
    {
        id: 3,
        title: "E-Munakahat",
        description:
            "E-Munakahat System is a group project developed for Software Requirement and Software Design Workshops at UMP. Designed using Figma, I created the UI template used by my team to build a cohesive interface. The system serves as an online platform for managing Islamic marriage, divorce, and reconciliation matters in Malaysia—specifically for marriage registration in Pahang, streamlining the entire process through digital record-keeping and user-friendly workflows.",
        tags: ["Laravel", "Vue.js", "HeidiSQL"],
        images: [
            "/images/Munakahat/Emunakahat.png",
            "/images/Munakahat/Emunakahat1.png",
            "/images/Munakahat/Emunakahat2.png",
            "/images/Munakahat/Emunakahat3.png",
            "/images/Munakahat/Emunakahat4.png",
            "/images/Munakahat/Emunakahat5.png",
        ],
        figmaLink:
            "https://www.figma.com/design/wp4gLk74nIz7S6P8oE7mcM/E-munakahat?t=eFCxFZdnSqGWdPL6-1",
    },
    {
        id: 4,
        title: "Can.Teen",
        description:
            "Can.Teen is a meal planner web system designed as a team project for our Web Engineering course. Created using Figma, the system helps users plan their meals by calculating calorie intake, tracking nutritional values, and providing personalized dietary recommendations. It aims to promote healthier eating habits through an intuitive interface and practical features that support users in managing their daily nutrition effectively.",
        tags: ["CodeIgniter 3", "HeidiSQL"],
        images: [
            "/images/Canteen/Canteen1.png",
            "/images/Canteen/Canteen2.png",
            "/images/Canteen/Canteen3.png",
        ],
        figmaLink:
            "https://www.figma.com/design/GGt3GUknHBZXJk136JJv3F/CanTeen?t=eFCxFZdnSqGWdPL6-1",
        prototypeLink:
            'https://www.figma.com/proto/GGt3GUknHBZXJk136JJv3F/CanTeen?t=VbN9By47jXw0EcO1-1&scaling=contain&content-scaling=fixed&page-id=0%3A1&node-id=1-181'
    },
    {
        id: 5,
        title: "Eduwallet",
        description:
            "Eduwallet is a financial management app designed specifically for UMP students, created as a freelance design project for a friend’s final year system. While he focused on development, I was responsible for the full UI/UX design process which is crafting the interface and building an interactive prototype in Figma based on his system requirements. The app helps students manage their expenses, track spending, and develop better financial habits through a clean and user-friendly experience tailored to student life.",
        tags: ["Laravel", "Vue.js", "HeidiSQL"],
        images: [
            "/images/Eduwallet/Eduwallet1.png",
            "/images/Eduwallet/Eduwallet2.png",
            "/images/Eduwallet/Eduwallet3.png",
            "/images/Eduwallet/Eduwallet4.png",
            "/images/Eduwallet/Eduwallet5.png",
        ],
        figmaLink:
            "https://www.figma.com/design/tD8fvqInr9eXQNPc06LcCw/Eduwallet?t=eFCxFZdnSqGWdPL6-1",
        prototypeLink:
            'https://www.figma.com/proto/tD8fvqInr9eXQNPc06LcCw/Eduwallet?t=5yvById214dLqKCS-1&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&node-id=1-20&starting-point-node-id=1%3A2'
    },
    {
        id: 6,
        title: "E-Bookoo",
        description:
            "E-Bookoo System is an e-commerce platform I’m currently designing and developing independently using Laravel, aimed at selling self-made educational e-books for children. Inspired by my side job creating creative learning materials, such as coloring books, alphabet guides, and dotted tracing sheets using Canva. I built this system to turn my designs into digital products for parents. It combines both my UI design and web development skills to support my goal of generating side income while promoting fun, educational content for kids.",
        tags: ["Laravel", "Vue.js", "HeidiSQL"],
        images: ["/images/Bookoo.png"],
    },
    {
        id: 7,
        title: "Doctor App",
        description:
            "Doctor App is a medical management interface I independently designed using Figma as part of an internship application assessment. The system was intended to help doctors manage patient records, view appointment schedules, and create new appointments efficiently. I created a clean and functional prototype to showcase my UI/UX skills, but the project was discontinued after I received and accepted an internship offer from another company.",
        tags: ["CodeIgniter 3", "MySQL", "Documenting"],
        images: [
            "/images/Abata/Abata1.jpg",
            "/images/Abata/Abata5.png",
            "/images/Abata/Abata2.jpg",
            "/images/Abata/Abata3.jpg",
            "/images/Abata/Abata4.jpg",
        ],
        figmaLink:
            "https://www.figma.com/design/5OyIqzp3P3dtcmg03WpcrU/Abata?t=eFCxFZdnSqGWdPL6-1",
        prototypeLink:
            'https://www.figma.com/proto/5OyIqzp3P3dtcmg03WpcrU/Abata?t=gaCqh7c1gv7UZnLZ-1&scaling=contain&content-scaling=fixed&page-id=0%3A1&node-id=1-3504'
    },
];

const projectRefs = ref([]);

// Track current image index for each project
const currentImageIndex = reactive({});

// Track auto-play intervals for each project
const autoPlayIntervals = reactive({});

// Initialize current image index for each project
projects.forEach((project) => {
    currentImageIndex[project.id] = 0;
});

// Navigation functions
const nextImage = (projectId, totalImages) => {
    currentImageIndex[projectId] =
        (currentImageIndex[projectId] + 1) % totalImages;
};

const previousImage = (projectId, totalImages) => {
    currentImageIndex[projectId] =
        currentImageIndex[projectId] === 0
            ? totalImages - 1
            : currentImageIndex[projectId] - 1;
};

const setCurrentImage = (projectId, index) => {
    currentImageIndex[projectId] = index;
    // Reset auto-play timer when user manually navigates
    resetAutoPlay(projectId);
};

// Auto-play functions
const startAutoPlay = (projectId, totalImages) => {
    // Only start auto-play if project has multiple images
    if (totalImages > 1) {
        autoPlayIntervals[projectId] = setInterval(() => {
            nextImage(projectId, totalImages);
        }, 5000); // 5 seconds
    }
};

const stopAutoPlay = (projectId) => {
    if (autoPlayIntervals[projectId]) {
        clearInterval(autoPlayIntervals[projectId]);
        delete autoPlayIntervals[projectId];
    }
};

const resetAutoPlay = (projectId) => {
    const project = projects.find((p) => p.id === projectId);
    if (project && project.images.length > 1) {
        stopAutoPlay(projectId);
        startAutoPlay(projectId, project.images.length);
    }
};

// Enhanced navigation functions that reset auto-play
const handleNextImage = (projectId, totalImages) => {
    nextImage(projectId, totalImages);
    resetAutoPlay(projectId);
};

const handlePreviousImage = (projectId, totalImages) => {
    previousImage(projectId, totalImages);
    resetAutoPlay(projectId);
};

onMounted(() => {
    // Initialize intersection observer for animations
    projectRefs.value.forEach((el, i) => {
        const delay = i * 0.6;
        const observer = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        el.classList.add("opacity-100", "translate-y-0");
                    }
                });
            },
            { threshold: 0.1 }
        );
        observer.observe(el);
    });

    // Start auto-play for all projects
    projects.forEach((project) => {
        startAutoPlay(project.id, project.images.length);
    });
});

// Clean up intervals when component unmounts
onUnmounted(() => {
    projects.forEach((project) => {
        stopAutoPlay(project.id);
    });
});
</script>

<style scoped>
.opacity-100 {
    opacity: 1 !important;
    transform: translateY(0) !important;
    transition: all 0.6s ease-out;
}
</style>
