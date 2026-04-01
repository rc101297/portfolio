<template>
  <nav
    class="fixed top-0 left-0 right-0 bg-white/95 backdrop-blur-md shadow-lg z-50 border-b border-gray-100"
  >
    <div class="max-w-6xl mx-auto px-4 py-4">
      <div class="flex justify-between items-center">
        <a
          href="#"
          class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent hover:scale-105 transition-transform duration-300"
        >
          RC
        </a>
        <div class="hidden md:flex space-x-8">
          <a
            href="#about"
            :class="[
              'relative font-medium transition-all duration-300 hover:text-blue-600',
              activeSection === 'about' ? 'text-blue-600' : 'text-gray-700',
            ]"
            @click="setActiveSection('about')"
          >
            About
            <span
              v-if="activeSection === 'about'"
              class="absolute -bottom-1 left-0 w-full h-0.5 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full"
            ></span>
          </a>
          <a
            href="#tech-stack"
            :class="[
              'relative font-medium transition-all duration-300 hover:text-blue-600',
              activeSection === 'tech-stack' ? 'text-blue-600' : 'text-gray-700',
            ]"
            @click="setActiveSection('tech-stack')"
          >
            Tech Stack
            <span
              v-if="activeSection === 'tech-stack'"
              class="absolute -bottom-1 left-0 w-full h-0.5 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full"
            ></span>
          </a>
          <a
            href="#projects"
            :class="[
              'relative font-medium transition-all duration-300 hover:text-blue-600',
              activeSection === 'projects' ? 'text-blue-600' : 'text-gray-700',
            ]"
            @click="setActiveSection('projects')"
          >
            Projects
            <span
              v-if="activeSection === 'projects'"
              class="absolute -bottom-1 left-0 w-full h-0.5 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full"
            ></span>
          </a>
          <a
            href="#contact"
            :class="[
              'relative font-medium transition-all duration-300 hover:text-blue-600',
              activeSection === 'contact' ? 'text-blue-600' : 'text-gray-700',
            ]"
            @click="setActiveSection('contact')"
          >
            Contact
            <span
              v-if="activeSection === 'contact'"
              class="absolute -bottom-1 left-0 w-full h-0.5 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full"
            ></span>
          </a>
        </div>
        <div class="md:hidden">
          <button
            @click="toggleMenu"
            class="text-gray-700 hover:text-blue-600 p-2 rounded-lg hover:bg-gray-100 transition-all duration-300"
          >
            <svg
              class="w-6 h-6 transform transition-transform duration-300"
              :class="{ 'rotate-90': isMenuOpen }"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                v-if="!isMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              ></path>
            </svg>
          </button>
        </div>
      </div>
      <div
        v-if="isMenuOpen"
        class="md:hidden mt-4 pb-4 border-t border-gray-200 bg-white/95 backdrop-blur-md rounded-lg shadow-lg"
      >
        <div class="flex flex-col space-y-4 pt-4 px-4">
          <a
            href="#about"
            @click="
              closeMenu();
              setActiveSection('about');
            "
            :class="[
              'block py-2 px-3 rounded-lg transition-all duration-300',
              activeSection === 'about'
                ? 'bg-blue-50 text-blue-600 border-l-4 border-blue-600'
                : 'text-gray-700 hover:bg-gray-50 hover:text-blue-600',
            ]"
          >
            About
          </a>
          <a
            href="#tech-stack"
            @click="
              closeMenu();
              setActiveSection('tech-stack');
            "
            :class="[
              'block py-2 px-3 rounded-lg transition-all duration-300',
              activeSection === 'tech-stack'
                ? 'bg-blue-50 text-blue-600 border-l-4 border-blue-600'
                : 'text-gray-700 hover:bg-gray-50 hover:text-blue-600',
            ]"
          >
            Tech Stack
          </a>
          <a
            href="#projects"
            @click="
              closeMenu();
              setActiveSection('projects');
            "
            :class="[
              'block py-2 px-3 rounded-lg transition-all duration-300',
              activeSection === 'projects'
                ? 'bg-blue-50 text-blue-600 border-l-4 border-blue-600'
                : 'text-gray-700 hover:bg-gray-50 hover:text-blue-600',
            ]"
          >
            Projects
          </a>
          <a
            href="#contact"
            @click="
              closeMenu();
              setActiveSection('contact');
            "
            :class="[
              'block py-2 px-3 rounded-lg transition-all duration-300',
              activeSection === 'contact'
                ? 'bg-blue-50 text-blue-600 border-l-4 border-blue-600'
                : 'text-gray-700 hover:bg-gray-50 hover:text-blue-600',
            ]"
          >
            Contact
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isMenuOpen = ref(false);
const activeSection = ref('');

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
  isMenuOpen.value = false;
};

const setActiveSection = (section) => {
  activeSection.value = section;
};

const updateActiveSection = () => {
  const sections = ['about', 'tech-stack', 'projects', 'contact'];
  const scrollPosition = window.scrollY + 100;

  for (const section of sections) {
    const element = document.getElementById(section);
    if (element) {
      const { offsetTop, offsetHeight } = element;
      if (scrollPosition >= offsetTop && scrollPosition < offsetTop + offsetHeight) {
        activeSection.value = section;
        break;
      }
    }
  }

  // If at top, no active section
  if (window.scrollY < 100) {
    activeSection.value = '';
  }
};

onMounted(() => {
  window.addEventListener('scroll', updateActiveSection);
  updateActiveSection(); // Initial check
});

onUnmounted(() => {
  window.removeEventListener('scroll', updateActiveSection);
});
</script>

<style scoped>
nav {
  backdrop-filter: blur(10px);
}
</style>