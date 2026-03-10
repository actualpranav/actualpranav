<script setup lang="ts">
import HeroSection from '@/components/HeroSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
import AboutStackSection from '@/components/AboutStackSection.vue'
import ExperienceSection from '@/components/ExperienceSection.vue'
import ContactSection from '@/components/ContactSection.vue'
</script>

<template>
  <div class="home-wrapper">
    <div id="home">
      <HeroSection />
    </div>
    
    <div id="about">
      <AboutStackSection />
    </div>

    <!-- Stack is part of AboutStackSection, but we keep an anchor point for navigation -->
    <div id="stack" class="sr-only"></div>

    <div id="experience">
      <ExperienceSection />
    </div>
    
    <div id="work">
      <ProjectsSection />
    </div>
    
    <div id="contact">
      <ContactSection />
    </div>
  </div>
</template>

<style scoped>
.home-wrapper {
  display: flex;
  flex-direction: column;
  width: 100%;
}
</style>
