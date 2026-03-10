<script setup lang="ts">
// Experience data adopting 'Senior Principal Architect' impact and scale framing
const experiences = [
  {
    id: 1,
    role: 'Software Development Engineer 1',
    company: 'Swiggy',
    period: 'Aug 2024 - Present',
    description: 'I worked on consolidating Swiggy’s communication platforms—handling SMS, WhatsApp, and Push Notifications—which helped reduce monthly infrastructure costs by ~$2,500. I also built the real-time catalog sync for Instamart (13M items) with Meta Ads and worked on the Brandverse project. Most of this involves managing high-throughput event pipelines at 575K events per minute using Kafka and HAProxy. Throughout these projects, I gained hands-on exposure to a broad AWS stack including SQS, SES, DynamoDB, ElastiCache, and more.',
    tech: ['Go', 'Java', 'AWS', 'Kafka', 'HAProxy', 'Spring Boot']
  },
  {
    id: 2,
    role: 'Backend Developer Intern',
    company: 'Fibe (EarlySalary)',
    period: 'Jan 2024 - Jun 2024',
    description: 'I built a Fraud Syndicate Dashboard and worked on automating KYC workflows. I also helped design systems to extract location data from video KYC, which made identity verification more accurate and reduced onboarding costs.',
    tech: ['Java', 'SQL', 'AWS', 'Springboot']
  },
  {
    id: 3,
    role: 'Intern',
    company: 'State Street',
    period: 'May 2023 - Jul 2023',
    description: 'I was part of the platform migration from Axiom V9 to V10, ensuring everything stayed accurate during the move. I also developed automated testing workflows to help the QA team release more reliably.',
    tech: ['Java', 'SQL', 'Axiom', 'QA Automation']
  }
]
</script>

<template>
  <section class="experience-section" id="working">
    <div class="container">
      <div class="section-header">
        <span class="mono-label section-label">// Architecture & Impact</span>
        <h2 class="section-title">Where I've Worked</h2>
      </div>

      <div class="timeline-container">
        <div class="timeline-line"></div>
        
        <div class="timeline-item" v-for="exp in experiences" :key="exp.id">
          <!-- The timeline dot -->
          <div class="timeline-dot"></div>
          
          <!-- The content card -->
          <div class="timeline-content">
            <div class="timeline-header">
              <h3 class="role-title">{{ exp.role }}</h3>
              <span class="company-name">@ {{ exp.company }}</span>
            </div>
            
            <div class="period-label mono-label">{{ exp.period }}</div>
            
            <p class="role-description">
              {{ exp.description }}
            </p>
            
            <ul class="tech-stack-list">
              <li v-for="tag in exp.tech" :key="tag" class="tech-tag">{{ tag }}</li>
            </ul>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  background-color: var(--color-espresso); /* Continue the dark theme */
  padding: var(--spacing-xxl) 0;
  width: 100%;
}

.section-header {
  margin-bottom: var(--spacing-xl);
  text-align: left;
}

.section-label {
  color: var(--color-eau-trouble);
  display: block;
  margin-bottom: var(--spacing-xs);
}

.section-title {
  color: var(--color-nuage-de-lait);
  font-size: var(--text-h1);
  letter-spacing: -0.01em;
}

/* Timeline specific layout */
.timeline-container {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  padding-left: 20px; /* Space for the line on mobile */
}

@media (min-width: 768px) {
  .timeline-container {
    padding-left: 40px;
  }
}

/* The vertical dashed/solid line */
.timeline-line {
  position: absolute;
  top: 8px; /* Slightly offset so it starts below the first dot */
  bottom: 0;
  left: 20px; /* matches .timeline-container padding-left */
  width: 2px;
  background-color: rgba(215, 201, 184, 0.1); /* Subtle khaki */
  z-index: 1;
}

@media (min-width: 768px) {
  .timeline-line {
    left: 40px;
  }
}

.timeline-item {
  position: relative;
  padding-left: 32px; /* Space between dot and card */
  margin-bottom: var(--spacing-xl);
  opacity: 0.95;
  transition: opacity 0.3s ease;
}

@media (min-width: 768px) {
  .timeline-item {
    padding-left: 48px;
  }
}

.timeline-item:hover {
  opacity: 1;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

/* The dot that sits on the line */
.timeline-dot {
  position: absolute;
  left: -5px; /* Centers the 12px dot on the 2px line based on padding */
  top: 6px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: var(--color-terre-cuite);
  border: 2px solid var(--color-espresso);
  z-index: 2;
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.timeline-item:hover .timeline-dot {
  transform: scale(1.3);
  background-color: var(--color-camel);
}

/* The card framing the experience */
.timeline-content {
  background-color: rgba(255, 255, 255, 0.02);
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  padding: clamp(20px, 4vw, 32px);
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.timeline-item:hover .timeline-content {
  transform: translateX(4px);
  background-color: rgba(255, 255, 255, 0.04);
}

.timeline-header {
  display: flex;
  flex-direction: column;
  margin-bottom: 8px;
}

@media (min-width: 640px) {
  .timeline-header {
    flex-direction: row;
    align-items: baseline;
    gap: 8px;
  }
}

.role-title {
  color: var(--color-nuage-de-lait);
  font-size: var(--text-h3);
  font-weight: 600;
  letter-spacing: -0.01em;
}

.company-name {
  color: var(--color-camel);
  font-size: var(--text-base-size);
  font-weight: 500;
}

.period-label {
  color: var(--color-eau-trouble);
  font-size: var(--text-small);
  margin-bottom: var(--spacing-md);
  opacity: 0.8;
}

.role-description {
  color: var(--color-camel); /* Using camel for body text on espresso is legible */
  line-height: 1.6;
  margin-bottom: var(--spacing-md);
  font-size: var(--text-base-size);
}

.tech-stack-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  list-style: none;
  padding: 0;
  margin: 0;
}

.tech-tag {
  background-color: rgba(255, 255, 255, 0.05);
  color: var(--color-eau-trouble);
  font-family: var(--font-mono);
  font-size: 12px;
  padding: 4px 10px;
  border-radius: 4px;
  transition: color 0.2s ease, background-color 0.2s ease;
}

.timeline-item:hover .tech-tag {
  background-color: rgba(215, 201, 184, 0.1);
  color: var(--color-nuage-de-lait);
}
</style>
