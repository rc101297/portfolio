<template>
  <section id="contact" class="py-16 px-8 bg-gradient-to-br from-blue-50 to-indigo-100">
    <div class="max-w-4xl mx-auto text-center">
      <div class="mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">Get In Touch</h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto"></div>
      </div>
      <div class="grid md:grid-cols-3 gap-8 mb-12 p-8">
        <div class="bg-white p-6 rounded-xl shadow-lg">
          <div class="text-4xl mb-4">📧</div>
          <h3 class="text-xl font-semibold text-gray-800 mb-2">Email</h3>
          <p class="text-gray-600">rowenacornejo.work@gmail.com</p>
        </div>
        <div class="bg-white p-6 rounded-xl shadow-lg">
          <div class="text-4xl mb-4">📱</div>
          <h3 class="text-xl font-semibold text-gray-800 mb-2">Phone</h3>
          <p class="text-gray-600">+63 926 126 628</p>
        </div>
        <div class="bg-white p-6 rounded-xl shadow-lg mb-2">
          <div class="text-4xl mb-4">📍</div>
          <h3 class="text-xl font-semibold text-gray-800 mb-2">Location</h3>
          <p class="text-gray-600">Cavite, Philippines</p>
        </div>
      </div>
      <div class="bg-white p-8 rounded-xl shadow-lg max-w-2xl mx-auto">
        <h3 class="text-2xl font-bold text-gray-800 mb-6">Send a Message</h3>
        <form @submit.prevent="submitForm" class="space-y-4">
          <div class="grid md:grid-cols-2 gap-4">
            <input
              v-model="name"
              type="text"
              placeholder="Your Name"
              class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
            />
            <input
              v-model="email"
              type="email"
              placeholder="Your Email"
              class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
            />
          </div>
          <textarea
            v-model="message"
            placeholder="Your Message"
            rows="4"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
            required
          ></textarea>
          <div class="flex justify-center">
            <div ref="recaptchaContainer"></div>
          </div>
          <button
            type="submit"
            :disabled="isLoading"
            class="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-3 px-6 rounded-lg font-medium hover:shadow-lg transform hover:scale-105 transition-all duration-300 disabled:opacity-50 disabled:cursor-not-allowed"
          >
            <span v-if="isLoading" class="flex items-center justify-center">
              <svg
                class="animate-spin -ml-1 mr-3 h-5 w-5 text-white"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
              >
                <circle
                  class="opacity-25"
                  cx="12"
                  cy="12"
                  r="10"
                  stroke="currentColor"
                  stroke-width="4"
                ></circle>
                <path
                  class="opacity-75"
                  fill="currentColor"
                  d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
                ></path>
              </svg>
              Sending...
            </span>
            <span v-else>Send Message</span>
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onBeforeMount, onMounted, ref } from 'vue';

import { Notyf } from 'notyf';
import 'notyf/notyf.min.css';

const notyf = new Notyf();

const WEB3FORMS_ACCESS_KEY = 'f079cc3d-a4fc-431b-8e2a-371c1a8ba6c0';

const subject = 'New message from Portfolio Contact Form';

const name = ref('');
const email = ref('');
const message = ref('');

const isLoading = ref(false);

// function for submit form
const submitForm = async () => {
  if (!recaptchaToken.value) {
    notyf.error('Please verify that you are not a robot.');
    return;
  }
  isLoading.value = true;

  try {
    const response = await fetch('https://api.web3forms.com/submit', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        Accept: 'application/json',
      },
      body: JSON.stringify({
        access_key: WEB3FORMS_ACCESS_KEY,
        subject: subject,
        name: name.value,
        email: email.value,
        message: message.value,
      }),
    });
    const result = await response.json();

    if (result.data.subject) {
      console.log(result);

      isLoading.value = false;
      notyf.success('Message Sent!');
    }
  } catch (error) {
    console.log(error);

    isLoading.value = false;
    notyf.error('Failed to send message.');
  } finally {
    resetRecaptcha();
  }
};

const SITE_KEY = '6LcxmBYsAAAAAMJVKNJ9n0PLGVNVpG3-MQF0lyrJ';
const recaptchaContainer = ref(null);
const recaptchaWidgetId = ref(null);
const recaptchaToken = ref('');

function onRecaptchaSucess(token) {
  recaptchaToken.value = token;
}

function onRecaptchaExpired() {
  recaptchaToken.value = '';
}

function renderRecaptcha() {
  if (!window.grecaptcha) {
    console.error('reCAPTCHA not loaded');
    return;
  }
  recaptchaWidgetId.value = window.grecaptcha.render(recaptchaContainer.value, {
    sitekey: SITE_KEY,
    size: 'normal',
    callback: onRecaptchaSucess,
    'expired-callback': onRecaptchaExpired,
  });
}

function resetRecaptcha() {
  if (recaptchaWidgetId.value !== null) {
    window.grecaptcha.reset(recaptchaWidgetId.value);
    recaptchaToken.value = '';
  }
}

onMounted(() => {
  const interval = setInterval(() => {
    if (window.grecaptcha && window.grecaptcha.render) {
      renderRecaptcha();
      clearInterval(interval);
    }
  }, 100);
  onBeforeMount(() => {
    clearInterval(interval);
  });
});
</script>

<style></style>