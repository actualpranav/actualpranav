<script setup lang="ts">
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    id: 1,
    title: 'Amazon Clone',
    description: 'Full-stack e-commerce replica with Stripe payments, real-time Firestore synchronization, and Firebase serverless logic.',
    tags: ['reactjs', 'node.js', 'firebase', 'stripe'],
    githubUrl: 'https://github.com/actualpranav/amazon-clone',
    liveUrl: 'https://challenge-629de.web.app/',
  },
  {
    id: 2,
    title: 'Tic-Tac-Toe Engine',
    description: 'Core Java customizable game supporting 26x26 boards and bots using MVC architecture, SOLID principles, and OOP concepts.',
    tags: ['java', 'oop', 'mvc'],
  },
  {
    id: 3,
    title: 'PraNow',
    description: 'An interactive personal platform featuring a custom UI engine and dynamic state management',
    tags: ['vuejs', 'vite', 'frontend'],
    liveUrl: 'https://pranow.vercel.app/',
  },
  {
    id: 4,
    title: 'ClipKboard',
    description: 'A cloud-synced clipboard tool for effortless text sharing across devices, powered by real-time database lookups based on usernames.',
    tags: ['reactjs', 'firebase', 'firestore'],
    liveUrl: 'https://clipkboard.web.app/',
  }
]
</script>

<template>
  <section class="projects-section">
    <div class="container">
      <div class="section-header">
        <span class="mono-label section-label">// Selected Work</span>
        <h2 class="section-title">Projects</h2>
      </div>
      
      <div class="projects-grid">
        <ProjectCard 
          v-for="project in projects" 
          :key="project.id"
          :title="project.title"
          :description="project.description"
          :tags="project.tags"
          :githubUrl="project.githubUrl"
          :liveUrl="project.liveUrl"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-section {
  background-color: var(--color-surface-light); /* Linen background */
  padding: var(--spacing-xxl) 0;
  width: 100%;
}

.section-header {
  margin-bottom: var(--spacing-xl);
}

.section-label {
  color: var(--color-eau-trouble);
  display: block;
  margin-bottom: var(--spacing-xs);
}

.section-title {
  color: var(--color-espresso);
  font-size: var(--text-h1);
  letter-spacing: -0.01em;
}

.projects-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-lg);
}

@media (min-width: 768px) {
  .projects-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1280px) {
  .projects-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
