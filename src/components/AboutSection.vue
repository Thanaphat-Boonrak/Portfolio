<script setup>
const interests = ['Backend Development']
</script>

<template>
  <section
    id="about"
    class="py-24 px-6 border-t transition-colors duration-300 scroll-mt-20 border-gray-100 dark:border-gray-800"
  >
    <div class="max-w-2xl w-full mx-auto md:mx-0 md:ml-[calc((100%-40rem)/2)]">
      <h2 class="text-lg font-semibold mb-8 transition-colors text-gray-900 dark:text-white">
        About Me
      </h2>

      <div class="space-y-8">
        <div>
          <h3 class="text-xs font-mono uppercase tracking-widest mb-3 text-blue-500">Biography</h3>
          <p class="text-sm leading-7 transition-colors text-gray-500 dark:text-gray-400">
            I'm Thanaphat Boonruck, a 2rd-year Information Technology student at KMUTT University.
          </p>
        </div>

        <div>
          <h3 class="text-xs font-mono uppercase tracking-widest mb-3 text-blue-500">Interests</h3>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="interest in interests"
              :key="interest"
              class="px-3 py-1 rounded-md text-xs font-mono border transition-colors border-gray-200 text-gray-600 bg-gray-50 dark:border-gray-700 dark:text-gray-400 dark:bg-gray-900"
            >
              {{ interest }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
