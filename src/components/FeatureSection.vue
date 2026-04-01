<template>
  <section id="features" class="py-20 px-8 bg-gradient-to-br from-gray-50 to-blue-50">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">
          Discover My
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-purple-600"
            >Unique Edge</span
          >
        </h2>
        <div class="w-32 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto mb-6"></div>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Beyond the code: Real-world impact, proven results, and what sets me apart in the
          developer landscape
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-12">
        <!-- Case Study Card -->
        <div
          class="bg-white rounded-2xl shadow-xl hover:shadow-2xl transition-all duration-300 overflow-hidden group"
        >
          <div class="bg-gradient-to-r from-blue-600 to-purple-600 p-6">
            <div class="flex items-center">
              <div
                class="w-12 h-12 bg-white bg-opacity-20 rounded-full flex items-center justify-center mr-4"
              >
                <span class="text-2xl">🧠</span>
              </div>
              <h3 class="text-2xl font-bold text-white">Deep Dive: Task Management App</h3>
            </div>
          </div>

          <div class="p-8">
            <div class="mb-8">
              <div class="flex items-center mb-3">
                <div class="w-8 h-8 bg-red-100 rounded-full flex items-center justify-center mr-3">
                  <span class="text-red-600 font-bold text-sm">!</span>
                </div>
                <h4 class="text-xl font-semibold text-gray-800">The Challenge</h4>
              </div>
              <p class="text-gray-600 leading-relaxed pl-11">
                Design a system that allows users to manage tasks efficiently while integrating
                external workflow tools.
              </p>
            </div>

            <div class="mb-8">
              <div class="flex items-center mb-3">
                <div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center mr-3">
                  <span class="text-blue-600 font-bold text-sm">→</span>
                </div>
                <h4 class="text-xl font-semibold text-gray-800">My Approach</h4>
              </div>
              <ul class="text-gray-600 leading-relaxed pl-11 space-y-2">
                <li class="flex items-start">
                  <span class="w-2 h-2 bg-blue-600 rounded-full mt-2 mr-3 flex-shrink-0"></span>
                  Built REST APIs using Express
                </li>
                <li class="flex items-start">
                  <span class="w-2 h-2 bg-blue-600 rounded-full mt-2 mr-3 flex-shrink-0"></span>
                  Designed MongoDB schema for task storage
                </li>
                <li class="flex items-start">
                  <span class="w-2 h-2 bg-blue-600 rounded-full mt-2 mr-3 flex-shrink-0"></span>
                  Integrated Trello API for workflow visualization
                </li>
                <li class="flex items-start">
                  <span class="w-2 h-2 bg-blue-600 rounded-full mt-2 mr-3 flex-shrink-0"></span>
                  Implemented authentication for secure access
                </li>
              </ul>
            </div>

            <div>
              <div class="flex items-center mb-3">
                <div
                  class="w-8 h-8 bg-green-100 rounded-full flex items-center justify-center mr-3"
                >
                  <span class="text-green-600 font-bold text-sm">✓</span>
                </div>
                <h4 class="text-xl font-semibold text-gray-800">The Result</h4>
              </div>
              <p class="text-gray-600 leading-relaxed pl-11">
                A functional full-stack application demonstrating real-world architecture, API
                integration, and secure data handling.
              </p>
            </div>
          </div>
        </div>

        <!-- What Makes Me Different Card -->
        <div
          class="bg-white rounded-2xl shadow-xl hover:shadow-2xl transition-all duration-300 overflow-hidden group"
        >
          <div class="bg-gradient-to-r from-purple-600 to-pink-600 p-6">
            <div class="flex items-center">
              <div
                class="w-12 h-12 bg-white bg-opacity-20 rounded-full flex items-center justify-center mr-4"
              >
                <span class="text-2xl">💡</span>
              </div>
              <h3 class="text-2xl font-bold text-white">Why Choose Me</h3>
            </div>
          </div>

          <div class="p-8">
            <div class="space-y-6 mb-8">
              <div
                class="flex items-start p-4 bg-gradient-to-r from-blue-50 to-indigo-50 rounded-lg hover:from-blue-100 hover:to-indigo-100 transition-colors"
              >
                <div
                  class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center mr-4 flex-shrink-0"
                >
                  <span class="text-white text-lg">📊</span>
                </div>
                <div>
                  <h5 class="font-semibold text-gray-800 mb-1">Data Accuracy Champion</h5>
                  <p class="text-gray-600 text-sm">
                    Maintaining up to 99% data accuracy in high-volume systems
                  </p>
                </div>
              </div>

              <div
                class="flex items-start p-4 bg-gradient-to-r from-green-50 to-emerald-50 rounded-lg hover:from-green-100 hover:to-emerald-100 transition-colors"
              >
                <div
                  class="w-10 h-10 bg-green-500 rounded-full flex items-center justify-center mr-4 flex-shrink-0"
                >
                  <span class="text-white text-lg">⚙️</span>
                </div>
                <div>
                  <h5 class="font-semibold text-gray-800 mb-1">Workflow Optimizer</h5>
                  <p class="text-gray-600 text-sm">
                    20% efficiency improvement through real-world process optimization
                  </p>
                </div>
              </div>

              <div
                class="flex items-start p-4 bg-gradient-to-r from-purple-50 to-violet-50 rounded-lg hover:from-purple-100 hover:to-violet-100 transition-colors"
              >
                <div
                  class="w-10 h-10 bg-purple-500 rounded-full flex items-center justify-center mr-4 flex-shrink-0"
                >
                  <span class="text-white text-lg">🧠</span>
                </div>
                <div>
                  <h5 class="font-semibold text-gray-800 mb-1">Analytical Thinker</h5>
                  <p class="text-gray-600 text-sm">
                    Technical engineering background driving problem-solving excellence
                  </p>
                </div>
              </div>

              <div
                class="flex items-start p-4 bg-gradient-to-r from-orange-50 to-amber-50 rounded-lg hover:from-orange-100 hover:to-amber-100 transition-colors"
              >
                <div
                  class="w-10 h-10 bg-orange-500 rounded-full flex items-center justify-center mr-4 flex-shrink-0"
                >
                  <span class="text-white text-lg">📝</span>
                </div>
                <div>
                  <h5 class="font-semibold text-gray-800 mb-1">Documentation Expert</h5>
                  <p class="text-gray-600 text-sm">
                    Exceptional documentation and reporting skills for clear communication
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style></style>