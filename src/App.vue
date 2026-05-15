<script setup>
import ContactSection from '@/components/ContactSection.vue'
import FooterSecrtion from '@/components/FooterSecrtion.vue'
import HeroSection from '@/components/HeroSection.vue'
import Navbar from '@/components/Navbar.vue'
</script>

<template>
  <div
    class="min-h-screen transition-colors duration-300 bg-white text-gray-900 dark:bg-gray-950 dark:text-gray-100"
  >
    <Navbar />
    <HeroSection />
    <ContactSection />
    <FooterSecrtion />
  </div>
</template>
