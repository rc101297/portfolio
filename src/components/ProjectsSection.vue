<script setup>
const projects = [
  {
    title: '🗂 Task Management App (FULL-STACK)',
    description:
      'Built a full-stack task manager with CRUD operations and API integration. Features: Authentication, task tracking, Trello API integration. Shows: Full-stack architecture, API integration, database handling.',
    tech: 'Vue.js, Node.js, Express, MongoDB, Trello API',
    github: '#',
    live: '#',
    image: '📋',
  },
  {
    title: '🎬 Movie Catalog App',
    description:
      'Developed a responsive SPA with user authentication and admin controls. Features: Login system, commenting, admin CRUD functionality. Shows: State management, authentication, UI/UX design.',
    tech: 'Vue.js, Node.js, Axios, Pinia, JWT',
    github: '#',
    live: '#',
    image: '🎬',
  },
  {
    title: '🛒 E-Commerce Mockup',
    description:
      'Built a mock e-commerce system with cart and checkout flow. Features: Product listing, cart system, backend integration. Shows: Full-stack data flow, user interaction handling.',
    tech: 'Vue.js, Node.js, Express.js, MongoDB',
    github: '#',
    live: '#',
    image: '🛒',
  },
  {
    title: '🌐 Portfolio Website',
    description:
      'Designed and developed a responsive personal portfolio. Implemented mobile-friendly UI. Deployed using GitHub + Vercel.',
    tech: 'HTML, CSS, Bootstrap, Vercel',
    github: '#',
    live: '#',
    image: '🌐',
  },
];
</script>

<template>
  <section id="projects" class="py-16 px-8 max-w-6xl mx-auto">
    <div class="text-center mb-12">
      <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">Projects</h2>
      <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto"></div>
    </div>
    <div class="grid md:grid-cols-2 gap-8">
      <div
        v-for="project in projects"
        :key="project.title"
        class="bg-white rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 overflow-hidden group flex flex-col"
      >
        <div
          class="h-48 bg-gradient-to-br from-blue-100 to-purple-100 flex items-center justify-center text-6xl"
        >
          {{ project.image }}
        </div>
        <div class="p-6 flex-1 flex flex-col gap-2">
          <h3 class="text-xl font-bold text-gray-800 mb-2">{{ project.title }}</h3>
          <p class="text-gray-600 mb-4">{{ project.description }}</p>
          <p class="text-sm text-blue-600 font-medium mb-4">{{ project.tech }}</p>
          <div class="flex gap-4 mt-auto">
            <a
              :href="project.github"
              class="flex-1 bg-gray-800 text-white text-center py-2 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-300"
            >
              GitHub
            </a>
            <a
              :href="project.live"
              class="flex-1 bg-gradient-to-r from-blue-600 to-purple-600 text-white text-center py-2 px-4 rounded-lg hover:shadow-lg transform hover:scale-105 transition-all duration-300"
            >
              Live Demo
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>


<style></style>