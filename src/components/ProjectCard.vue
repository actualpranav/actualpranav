<script setup lang="ts">
defineProps<{
  title: string
  description: string
  tags: string[]
  githubUrl?: string
  liveUrl?: string
}>()
</script>

<template>
  <article class="project-card">
    <div class="card-content">
      <h3 class="project-title">
        <a v-if="liveUrl" :href="liveUrl" target="_blank" rel="noopener noreferrer" class="title-link">
          {{ title }}
        </a>
        <span v-else>{{ title }}</span>
      </h3>
      <p class="project-desc">{{ description }}</p>
      
      <div class="project-tags">
        <span v-for="tag in tags" :key="tag" class="tag">{{ tag }}</span>
      </div>
    </div>
    
    <footer class="card-footer">
      <a v-if="githubUrl" :href="githubUrl" target="_blank" rel="noopener noreferrer" class="card-link" aria-label="GitHub Repository">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
        </svg>
      </a>
      
      <a v-if="liveUrl" :href="liveUrl" target="_blank" rel="noopener noreferrer" class="card-link" aria-label="Live Demo">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
          <polyline points="15 3 21 3 21 9"></polyline>
          <line x1="10" y1="14" x2="21" y2="3"></line>
        </svg>
      </a>
    </footer>
  </article>
</template>

<style scoped>
.project-card {
  background-color: var(--color-surface-card);
  border: 1px solid var(--color-border);
  border-radius: 12px;
  padding: clamp(20px, 2.5vw, 28px);
  display: flex;
  flex-direction: column;
  height: 100%;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
}

@media (min-width: 1024px) {
  .project-card:hover,
  .project-card:focus-within {
    transform: translateY(-6px);
    box-shadow: 0 12px 24px -10px rgba(125, 106, 68, 0.15); /* Cocoa shadow */
    border-color: var(--color-caramel);
  }
}

.card-content {
  flex: 1;
}

.project-title {
  color: var(--color-text-dark);
  font-family: var(--font-heading);
  font-weight: 600;
  font-size: var(--text-h2);
  margin-bottom: var(--spacing-sm);
  line-height: 1.3;
}

.title-link {
  color: inherit;
  text-decoration: none;
  transition: color 0.2s ease, text-decoration 0.2s ease;
}

.title-link:hover {
  color: var(--color-terre-cuite);
  text-decoration: underline;
  text-decoration-thickness: 2px;
  text-underline-offset: 4px;
}

.project-desc {
  color: var(--color-text-muted);
  font-size: var(--text-base-size);
  margin-bottom: var(--spacing-lg);
  white-space: pre-line; /* Respects \n in the text data */
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: var(--spacing-lg);
}

.tag {
  background-color: var(--color-espresso);
  color: var(--color-nuage-de-lait);
  font-family: var(--font-mono);
  font-size: 13px;
  padding: 4px 10px;
  border-radius: 6px;
  line-height: 1.4;
}

.card-footer {
  display: flex;
  gap: 16px;
  margin-top: auto;
  padding-top: var(--spacing-md);
  border-top: 1px solid rgba(215, 201, 184, 0.5); /* Khaki subtle divider */
}

.card-link {
  color: var(--color-camel);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: color 0.2s ease, transform 0.2s ease;
}

.card-link:hover,
.card-link:focus-visible {
  color: var(--color-terre-cuite);
  transform: translateY(-2px);
}
</style>
