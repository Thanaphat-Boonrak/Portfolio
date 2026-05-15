<script setup>
import { ref, onMounted } from 'vue'

const menuOpen = ref(false)
const isDark = ref(true)

const links = [
  { label: 'About', href: '#about' },
  { label: 'Contact', href: '#contact' },
]

const toggleDark = () => {
  isDark.value = !isDark.value
  document.documentElement.classList.toggle('dark', isDark.value)
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light')
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme) {
    isDark.value = savedTheme === 'dark'
  }
  document.documentElement.classList.toggle('dark', isDark.value)
})
</script>

<template>
  <nav
    class="fixed top-0 w-full z-50 border-b transition-colors duration-300 bg-white border-gray-200 dark:bg-gray-950 dark:border-gray-800"
  >
    <div class="max-w-5xl mx-auto px-6 py-4 flex items-center justify-between">
      <span class="font-mono font-semibold text-gray-900 dark:text-white">
        Thanaphat<span class="text-blue-500">.</span>
      </span>

      <div class="flex items-center gap-6">
        <ul class="hidden md:flex gap-6 text-sm">
          <li v-for="link in links" :key="link.href">
            <a
              :href="link.href"
              class="transition-colors duration-200 text-gray-500 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white"
            >
              {{ link.label }}
            </a>
          </li>
        </ul>

        <button
          @click="toggleDark"
          class="w-8 h-8 flex items-center justify-center rounded-md border transition-colors duration-200 border-gray-200 text-gray-500 hover:text-gray-900 hover:border-gray-400 dark:border-gray-700 dark:text-gray-400 dark:hover:text-white dark:hover:border-gray-500"
        >
          <svg v-if="isDark" class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <circle cx="12" cy="12" r="5" stroke-width="2" />
            <path
              stroke-linecap="round"
              stroke-width="2"
              d="M12 2v2M12 20v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M2 12h2M20 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"
            />
          </svg>
          <svg v-else class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M21 12.79A9 9 0 1111.21 3 7 7 0 0021 12.79z"
            />
          </svg>
        </button>

        <button
          class="md:hidden transition-colors text-gray-500 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white"
          @click="menuOpen = !menuOpen"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              v-if="!menuOpen"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path
              v-else
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
    </div>

    <div
      v-if="menuOpen"
      class="md:hidden border-t px-6 py-4 border-gray-100 bg-white dark:border-gray-800 dark:bg-gray-950"
    >
      <ul class="flex flex-col gap-3 text-sm">
        <li v-for="link in links" :key="link.href">
          <a
            :href="link.href"
            class="transition-colors text-gray-500 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white"
            @click="menuOpen = false"
            >{{ link.label }}</a
          >
        </li>
      </ul>
    </div>
  </nav>
</template>
