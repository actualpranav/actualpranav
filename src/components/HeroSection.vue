<script setup lang="ts">
// SVG path for a subtle noise overlay
const noiseUrl = "data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E"
</script>

<template>
  <section class="hero-section">
    <!-- Grain Overlay -->
    <div class="grain-overlay" :style="{ backgroundImage: `url(${noiseUrl})` }"></div>
    
    <div class="container hero-content">
      <div class="label-wrapper">
        <span class="mono-label hero-label">Software Developer</span>
      </div>
      
      <h1 class="hero-name">Pranav Jadhav.</h1>
      
      <p class="hero-tagline">
        I build the systems that power what people see.
      </p>
      
      <div class="hero-actions">
        <a href="#working" class="btn btn-primary">See my work &rarr;</a>
        <a href="#contact" class="btn btn-ghost">Get in touch</a>
      </div>
    </div>
    
    <!-- Animated Scroll Indicator -->
    <div class="scroll-indicator">
      <div class="chevron"></div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  min-height: 100vh;
  width: 100%;
  background-color: #140e0a; /* Very deep espresso background specifically for hero */
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  padding-top: 80px; /* offset for fixed header */
}

.grain-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.05;
  pointer-events: none;
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.label-wrapper {
  margin-bottom: var(--spacing-md);
}

.hero-label {
  color: var(--color-eau-trouble);
}

.hero-name {
  color: var(--color-nuage-de-lait);
  font-size: var(--text-hero);
  line-height: 1.1;
  letter-spacing: -0.02em;
  margin-bottom: var(--spacing-sm);
}

.hero-tagline {
  color: var(--color-camel);
  font-size: var(--text-h2);
  max-width: 60ch;
  margin-bottom: var(--spacing-xl);
  line-height: 1.5;
}

.hero-actions {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
  width: 100%;
  max-width: 300px;
}

@media (min-width: 768px) {
  .hero-actions {
    flex-direction: row;
    justify-content: center;
    max-width: none;
  }
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 14px 28px;
  border-radius: 8px;
  font-family: var(--font-body);
  font-weight: 500;
  font-size: var(--text-base-size);
  transition: transform 0.2s ease, background-color 0.2s ease, border-color 0.2s ease, color 0.2s ease;
}

.btn:active {
  transform: scale(0.98);
}

.btn-primary {
  background-color: var(--color-terre-cuite);
  color: var(--color-nuage-de-lait);
  border: 1.5px solid var(--color-terre-cuite);
}

.btn-primary:hover,
.btn-primary:focus-visible {
  transform: scale(1.03);
  background-color: #8c3219; /* Slightly darker terre cuite */
}

.btn-ghost {
  background-color: transparent;
  color: var(--color-camel);
  border: 1.5px solid var(--color-camel);
}

.btn-ghost:hover,
.btn-ghost:focus-visible {
  border-color: var(--color-terre-cuite);
  color: var(--color-terre-cuite);
}

.scroll-indicator {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
  opacity: 0.7;
}

.chevron {
  width: 16px;
  height: 16px;
  border-right: 2px solid var(--color-camel);
  border-bottom: 2px solid var(--color-camel);
  transform: rotate(45deg);
  animation: bounce 2s infinite ease-in-out;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0) rotate(45deg);
  }
  40% {
    transform: translateY(-8px) rotate(45deg);
  }
  60% {
    transform: translateY(-4px) rotate(45deg);
  }
}
</style>
