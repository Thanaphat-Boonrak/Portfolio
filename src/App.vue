<script setup>
import AboutSection from '@/components/AboutSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import ExperienceSection from '@/components/ExperienceSection.vue'
import FooterSecrtion from '@/components/FooterSecrtion.vue'
import HeroSection from '@/components/HeroSection.vue'
import Navbar from '@/components/Navbar.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
import SkillsSection from '@/components/SkillsSection.vue'
</script>

<template>
  <div
    class="min-h-screen transition-colors duration-300 bg-white text-gray-900 dark:bg-gray-950 dark:text-gray-100"
  >
    <Navbar />
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ProjectsSection />
    <ExperienceSection />
    <ContactSection />
    <FooterSecrtion />
  </div>
</template>
