<script setup lang="ts">
import { ref } from 'vue'

const currentYear = new Date().getFullYear();
const email = 'pranavpjadhav154@gmail.com';
const isCopied = ref(false);

const copyEmail = async () => {
  try {
    await navigator.clipboard.writeText(email);
    isCopied.value = true;
    setTimeout(() => {
      isCopied.value = false;
    }, 2000);
  } catch (err) {
    console.error('Failed to copy: ', err);
  }
};
</script>

<template>
  <section class="contact-section">
    <div class="container contact-content">
      <span class="mono-label contact-label">— Let's Talk —</span>
      
      <h2 class="contact-title">Work together?</h2>
      
      <p class="contact-subline">
        Open to full-time roles, contracts, and interesting problems.
      </p>
      
      <div class="email-wrapper">
        <a :href="`mailto:${email}`" class="email-link">
          {{ email }}
        </a>
        <button class="copy-btn" @click="copyEmail" :aria-label="isCopied ? 'Copied' : 'Copy email'">
          <svg v-if="!isCopied" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="9" y="9" width="13" height="13" rx="2" ry="2"></rect>
            <path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"></path>
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="check-icon">
            <polyline points="20 6 9 17 4 12"></polyline>
          </svg>
          <span class="copy-tooltip" v-if="isCopied">Copied!</span>
        </button>
      </div>
      
      <div class="social-links">
        <a href="https://www.linkedin.com/in/actualpranav/" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="LinkedIn">
          <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
            <rect x="2" y="9" width="4" height="12"></rect>
            <circle cx="4" cy="4" r="2"></circle>
          </svg>
        </a>
        <a href="https://github.com/actualpranav" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="GitHub">
          <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
          </svg>
        </a>
        <a href="https://www.instagram.com/actualpranav/" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="Instagram">
          <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
            <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
            <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
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
  padding-bottom: var(--spacing-lg);
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

.email-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: var(--spacing-xl);
  max-width: 100%;
}

.email-link {
  color: var(--color-nuage-de-lait);
  font-family: var(--font-heading);
  font-size: clamp(18px, 6vw, 36px);
  font-weight: 700;
  position: relative;
  display: inline-block;
  padding-bottom: 4px;
  overflow-wrap: break-word;
  word-break: break-word;
}

.copy-btn {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(215, 201, 184, 0.2);
  color: var(--color-camel);
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  transition: all 0.2s ease;
  margin-top: -4px;
}

.copy-btn:hover {
  background: rgba(255, 255, 255, 0.1);
  color: var(--color-nuage-de-lait);
  border-color: var(--color-camel);
}

.check-icon {
  color: #27c93f;
  animation: pop 0.3s ease-out;
}

.copy-tooltip {
  position: absolute;
  top: -30px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--color-espresso);
  color: var(--color-nuage-de-lait);
  font-family: var(--font-mono);
  font-size: 10px;
  padding: 4px 8px;
  border-radius: 4px;
  border: 1px solid var(--color-camel);
  white-space: nowrap;
  pointer-events: none;
}

@keyframes pop {
  0% { transform: scale(0.5); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
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
  margin-bottom: var(--spacing-lg);
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
