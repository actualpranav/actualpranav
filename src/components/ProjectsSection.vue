<script setup lang="ts">
import ProjectCard from './ProjectCard.vue'

// Sample data - you can replace this with your actual projects later
const projects = [
  {
    id: 1,
    title: 'Distributed Message Queue',
    description: 'A high-throughput, horizontally scalable message broker built in Go using Raft consensus for high availability.',
    tags: ['golang', 'raft', 'tcp', 'grpc'],
    githubUrl: '#',
  },
  {
    id: 2,
    title: 'Payment Processing Service',
    description: 'Idempotent, PCI-compliant payment gateway integration handling Stripe and PayPal webhooks with zero data loss.',
    tags: ['python', 'fastapi', 'postgresql', 'redis'],
    githubUrl: '#',
    liveUrl: '#',
  },
  {
    id: 3,
    title: 'Real-time Analytics Engine',
    description: 'Stream processing pipeline ingesting 10k events/sec. Stores aggregated data for dashboard consumption.',
    tags: ['rust', 'kafka', 'clickhouse', 'docker'],
    githubUrl: '#',
  }
]
</script>

<template>
  <section class="projects-section">
    <div class="container">
      <div class="section-header">
        <span class="mono-label section-label">// Selected Work</span>
        <h2 class="section-title">Things I've Built</h2>
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
