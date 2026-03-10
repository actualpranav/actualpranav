<script setup lang="ts">
// No complex logic needed here for now
</script>

<template>
  <section class="about-stack-section">
    <div class="container about-stack-grid">
      
      <!-- Left Column: About -->
      <div class="about-content">
        <h2 class="about-title">A bit about me</h2>
        <div class="about-body">
          <p>
            I'm a backend engineer currently working as an SDE 1 at Swiggy. I specialize in designing horizontally scalable systems, optimizing costs, and building reliable microservices. 
          </p>
          <p>
            Previously, I interned at Fibe and State Street where I built fraud detection dashboards and migrated legacy systems ensuring 100% data accuracy.
          </p>
        </div>
      </div>
      
      <!-- Right Column: Stack -->
      <div class="stack-content">
        <div class="terminal-card">
          <div class="terminal-header">
            <span class="terminal-dot red"></span>
            <span class="terminal-dot yellow"></span>
            <span class="terminal-dot green"></span>
          </div>
          <div class="terminal-body">
            <h3 class="stack-title">// Tech I Reach For</h3>
            
            <div class="stack-line">
              <span class="stack-key">&gt; languages</span>
              <span class="stack-value">go, java, python, javascript, sql, springboot, dropwizard, reactjs, grpc</span>
            </div>
            
            <div class="stack-line">
              <span class="stack-key">&gt; infra & db</span>
              <span class="stack-value">mysql, dynamodb, redis, mongodb, firebase, aws, kafka, haproxy, kql</span>
            </div>
            
            <div class="stack-line">
              <span class="stack-key">&gt; tools</span>
              <span class="stack-value">github, jetbrains, llms, databricks, fcm</span>
            </div>
          </div>
        </div>
      </div>
      
    </div>
  </section>
</template>

<style scoped>
.about-stack-section {
  background-color: var(--color-espresso);
  padding: var(--spacing-xxl) 0;
  width: 100%;
}

.about-stack-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-xl);
}

@media (min-width: 1024px) {
  .about-stack-grid {
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: var(--spacing-xxl);
  }
}

/* About Column */
.about-title {
  color: var(--color-nuage-de-lait);
  font-size: var(--text-h1);
  margin-bottom: var(--spacing-md);
  letter-spacing: -0.01em;
}

.about-body p {
  color: var(--color-camel);
  font-size: var(--text-base-size);
  margin-bottom: var(--spacing-md);
  max-width: 480px;
}

.about-body p:last-child {
  margin-bottom: 0;
  font-size: var(--text-small);
  opacity: 0.8;
}

/* Stack Column (Terminal) */
.stack-content {
  background-color: var(--color-matcha);
  border-radius: 12px;
  padding: clamp(16px, 2vw, 24px);
}

.terminal-card {
  background-color: #0f0e0c; /* Near black insect */
  border-radius: 8px;
  overflow: hidden;
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.05);
}

.terminal-header {
  background-color: rgba(255, 255, 255, 0.03);
  padding: 12px 16px;
  display: flex;
  gap: 8px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.terminal-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.red { background-color: #ff5f56; }
.yellow { background-color: #ffbd2e; }
.green { background-color: #27c93f; }

.terminal-body {
  padding: 24px 20px;
  font-family: var(--font-mono);
  font-size: 13px; /* Slightly smaller than base for terminal aesthetic */
  line-height: 1.6;
}

.stack-title {
  color: var(--color-miel-dore);
  margin-bottom: 24px;
  font-family: var(--font-mono);
  font-size: 14px;
}

.stack-line {
  display: flex;
  flex-direction: column;
  margin-bottom: 16px;
}

@media (min-width: 640px) {
  .stack-line {
    flex-direction: row;
  }
}

.stack-line:last-child {
  margin-bottom: 0;
}

.stack-key {
  color: var(--color-nuage-de-lait);
  width: 140px; /* Fixed width for alignment like a table */
  flex-shrink: 0;
}

.stack-value {
  color: var(--color-bleu-porcelaine);
}
</style>
