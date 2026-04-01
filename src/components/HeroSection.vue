<template>
  <section
    class="min-h-screen flex flex-col justify-center items-center text-center p-6 bg-gradient-to-br from-blue-50 to-indigo-100 pt-20"
  >
    <div class="animate-fade-in">
      <h1
        class="text-5xl md:text-6xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent p-4 mb-4"
      >
        Rowena Cornejo
      </h1>
      <h2 class="text-xl md:text-2xl text-gray-700 mb-6">Junior Full-Stack Developer</h2>
      <p class="max-w-2xl text-lg text-gray-600 mb-8 leading-relaxed">
        I build responsive web applications with clean UI and reliable backend systems. <br />With
        5+ years of experience in data handling, documentation, and process optimization, I bring
        accuracy, structure, and real-world problem-solving into development.
      </p>
      <div class="flex flex-col sm:flex-row gap-4 justify-center p-4">
        <a
          href="#projects"
          class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-3 rounded-full font-medium hover:shadow-lg transform hover:scale-105 transition-all duration-300"
        >
          View Projects
        </a>
        <a
          href="#contact"
          class="border-2 border-blue-600 text-blue-600 px-8 py-3 rounded-full font-medium hover:bg-blue-600 hover:text-white transition-all duration-300"
        >
          Get In Touch
        </a>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out;
}
</style>
