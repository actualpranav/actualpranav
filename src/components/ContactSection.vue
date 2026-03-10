<script setup lang="ts">
const currentYear = new Date().getFullYear();
</script>

<template>
  <section class="contact-section">
    <div class="container contact-content">
      <span class="mono-label contact-label">— Let's Talk —</span>
      
      <h2 class="contact-title">Work together?</h2>
      
      <p class="contact-subline">
        Open to full-time roles, contracts, and interesting problems.
      </p>
      
      <a href="mailto:pranavpjadhav154@gmail.com" class="email-link">
        pranavpjadhav154@gmail.com
      </a>
      
      <div class="social-links">
        <a href="https://www.linkedin.com/in/actualpranav/" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="LinkedIn">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
            <rect x="2" y="9" width="4" height="12"></rect>
            <circle cx="4" cy="4" r="2"></circle>
          </svg>
        </a>
      </div>
      
    </div>
    
    <footer class="site-footer">
      <p>Built with Vue.js · Vercel · &copy; {{ currentYear }}</p>
    </footer>
  </section>
</template>

<style scoped>
.contact-section {
  background-color: #140e0a; /* Same deep espresso as hero */
  padding-top: var(--spacing-xxl);
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.contact-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  max-width: 640px;
  padding-bottom: var(--spacing-xxl);
}

.contact-label {
  color: var(--color-eau-trouble);
  margin-bottom: var(--spacing-md);
}

.contact-title {
  color: var(--color-nuage-de-lait);
  font-size: var(--text-h1);
  letter-spacing: -0.01em;
  margin-bottom: var(--spacing-md);
}

.contact-subline {
  color: var(--color-camel);
  font-size: var(--text-base-size);
  margin-bottom: var(--spacing-xl);
}

.email-link {
  color: var(--color-nuage-de-lait);
  font-family: var(--font-heading);
  font-size: clamp(24px, 4vw, 36px);
  font-weight: 700;
  position: relative;
  display: inline-block;
  margin-bottom: var(--spacing-xl);
  padding-bottom: 4px;
}

.email-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 3px;
  background-color: var(--color-camel);
  transition: width 0.3s ease, background-color 0.3s ease;
  transform-origin: left;
}

.email-link:hover,
.email-link:focus-visible {
  color: var(--color-terre-cuite);
}

.email-link:hover::after,
.email-link:focus-visible::after {
  background-color: var(--color-terre-cuite);
}

.social-links {
  display: flex;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-xl);
}

.social-icon {
  color: var(--color-camel);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 12px;
  border-radius: 50%;
  border: 1.5px solid var(--color-camel);
  transition: all 0.2s ease;
}

.social-icon:hover,
.social-icon:focus-visible {
  color: var(--color-terre-cuite);
  border-color: var(--color-terre-cuite);
  transform: translateY(-4px);
}

.site-footer {
  width: 100%;
  text-align: center;
  padding: var(--spacing-md) 0;
  border-top: 1px solid rgba(215, 201, 184, 0.05); /* very subtle khaki line */
}

.site-footer p {
  color: var(--color-cocoa);
  font-family: var(--font-mono);
  font-size: 13px;
}
</style>
