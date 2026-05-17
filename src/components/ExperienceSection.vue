<script setup>
const experiences = [
  {
    title: 'Real-time Matching System (Starterpack IT31)',
    period: '2025',
    description:
      'Built a real-time matching system using Node.js, Socket.io, Prisma, and MySQL with JWT authentication and geolocation matching.',
  },
]
</script>

<template>
  <section
    id="experience"
    class="py-24 px-6 border-t border-gray-100 dark:border-gray-800 scroll-mt-20"
  >
    <div class="max-w-2xl mx-auto">
      <h2 class="text-lg font-semibold mb-10 text-gray-900 dark:text-white">Experience</h2>

      <div class="space-y-6">
        <div
          v-for="item in experiences"
          :key="item.title"
          class="pb-6 border-b border-gray-100 dark:border-gray-800"
        >
          <div class="flex justify-between items-start mb-2">
            <h3 class="text-sm font-medium text-gray-900 dark:text-white">
              {{ item.title }}
            </h3>

            <span class="text-xs text-gray-400">
              {{ item.period }}
            </span>
          </div>

          <p class="text-sm leading-6 text-gray-500 dark:text-gray-400">
            {{ item.description }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
