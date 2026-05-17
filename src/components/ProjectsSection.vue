<script setup>
const projects = [
  {
    title: 'Learn Space',
    description: 'A Frontend vue.js',
    tech: ['Vue.js'],
    role: 'Frontend-Developer',
    link: 'https://github.com/Thanaphat-Boonrak/Learn_Space',
  },
]
</script>

<template>
  <section
    id="projects"
    class="py-24 px-6 border-t transition-colors duration-300 scroll-mt-20 border-gray-100 dark:border-gray-800"
  >
    <div class="max-w-2xl w-full mx-auto md:mx-0 md:ml-[calc((100%-40rem)/2)]">
      <h2 class="text-lg font-semibold mb-8 transition-colors text-gray-900 dark:text-white">
        Projects
      </h2>

      <div class="space-y-6">
        <div
          v-for="project in projects"
          :key="project.title"
          class="p-5 rounded-lg border transition-colors border-gray-100 dark:border-gray-800 hover:border-gray-200 dark:hover:border-gray-700"
        >
          <div class="flex items-start justify-between gap-4 mb-3">
            <h3 class="text-sm font-semibold transition-colors text-gray-900 dark:text-white">
              {{ project.title }}
            </h3>
            <a
              v-if="project.link"
              :href="project.link"
              target="_blank"
              class="shrink-0 transition-colors text-gray-400 hover:text-gray-900 dark:hover:text-white"
              aria-label="View on GitHub"
            >
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                <path
                  d="M12 0C5.37 0 0 5.373 0 12c0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"
                />
              </svg>
            </a>
          </div>

          <p class="text-xs leading-6 mb-4 transition-colors text-gray-500 dark:text-gray-400">
            {{ project.description }}
          </p>

          <p
            class="text-xs leading-6 mb-4 transition-colors text-gray-400 dark:text-gray-500 italic"
          >
            {{ project.role }}
          </p>

          <!-- Tech stack -->
          <div class="flex flex-wrap gap-1.5">
            <span
              v-for="tech in project.tech"
              :key="tech"
              class="px-2 py-0.5 rounded text-xs font-mono border transition-colors border-gray-200 text-gray-500 bg-gray-50 dark:border-gray-700 dark:text-gray-500 dark:bg-gray-900"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
