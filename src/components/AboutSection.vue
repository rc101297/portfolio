<template>
  <section class="py-16 px-8 max-w-4xl mx-auto">
    <div class="text-center mb-12">
      <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">About Me</h2>
      <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto"></div>
    </div>
    <div class="grid md:grid-cols-2 gap-8 items-center">
      <div>
        <p class="text-lg text-gray-600 leading-relaxed mb-6">
          Full-Stack Developer skilled in Vue, Node.js, Express, and MongoDB. Experienced in
          handling large datasets with high accuracy and efficiency.
        </p>
        <p class="text-lg text-gray-600 leading-relaxed">
          Passionate about creating user-friendly applications and continuously learning new
          technologies to deliver high-quality solutions.
        </p>
      </div>
      <div class="flex justify-center">
        <div
          class="w-64 h-64 bg-gradient-to-br from-blue-100 to-purple-100 rounded-full flex items-center justify-center"
        >
          <div class="text-6xl">
            <img
              :src="Profile"
              class="img-fluid col-lg-3 rounded-circle"
              id="profile"
              alt="Profile Picture"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import Profile from '/images/profile.jpg';
</script>

<style>
</style>