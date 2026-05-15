<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const roles = ['Backend Developer', 'Java & Spring Boot']
const typedText = ref('')
let roleIndex = 0,
  charIndex = 0,
  deleting = false,
  timer = null

function typingEffect() {
  const current = roles[roleIndex]
  typedText.value = deleting ? current.slice(0, charIndex--) : current.slice(0, charIndex++)
  if (!deleting && charIndex > current.length) {
    deleting = true
    timer = setTimeout(typingEffect, 1400)
    return
  }
  if (deleting && charIndex < 0) {
    deleting = false
    roleIndex = (roleIndex + 1) % roles.length
  }
  timer = setTimeout(typingEffect, deleting ? 45 : 85)
}

const skills = ['Java', 'Spring Boot']

onMounted(typingEffect)
onUnmounted(() => clearTimeout(timer))
</script>

<template>
  <section class="min-h-screen flex items-center justify-center px-6 pt-20">
    <div class="max-w-2xl w-full flex flex-col md:flex-row-reverse items-center gap-10">
      <!-- Profile image -->
      <img
        src="/image.png"
        alt="Thanaphat Boonruck"
        class="w-36 h-36 md:w-44 md:h-44 rounded-full object-cover shrink-0 border-2 border-gray-200 dark:border-gray-700"
      />

      <!-- Text content -->
      <div class="flex-1">
        <p class="text-blue-500 text-sm font-mono mb-3">Hi, I'm</p>

        <h1
          class="text-5xl md:text-6xl font-bold mb-4 transition-colors text-gray-900 dark:text-white"
        >
          Thanaphat Boonruck
        </h1>

        <div class="flex items-center gap-1 mb-6 h-9">
          <span class="text-xl font-mono transition-colors text-gray-500 dark:text-gray-400">
            {{ typedText }}
          </span>
          <span class="text-blue-500 font-mono text-xl animate-pulse">|</span>
        </div>

        <p
          class="text-sm leading-7 max-w-md mb-8 transition-colors text-gray-500 dark:text-gray-400"
        >
          Passionate developer focused on backend
        </p>

        <div class="flex gap-3 mb-6">
          <a
            href="#contact"
            class="px-5 py-2.5 rounded-lg text-sm font-medium bg-blue-600 hover:bg-blue-500 text-white transition-colors duration-200"
          >
            Contact me
          </a>
          <a
            href="#about"
            class="px-5 py-2.5 rounded-lg text-sm font-medium border transition-colors duration-200 border-gray-300 text-gray-600 hover:border-gray-400 hover:text-gray-900 dark:border-gray-700 dark:text-gray-300 dark:hover:border-gray-500 dark:hover:text-white"
          >
            About me
          </a>
        </div>

        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in skills"
            :key="skill"
            class="px-3 py-1 rounded-md text-xs font-mono border transition-colors border-gray-200 text-gray-600 bg-gray-50 dark:border-gray-700 dark:text-gray-400 dark:bg-gray-900"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>
