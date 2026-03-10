<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
  if (isMobileMenuOpen.value) {
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = ''
  }
}

const closeMobileMenu = () => {
  if (isMobileMenuOpen.value) toggleMobileMenu()
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header :class="{ 'is-scrolled': isScrolled }">
    <div class="container nav-container">
      <div class="logo">
        <a href="#home" @click="closeMobileMenu">Pranav.</a>
      </div>

      <!-- Desktop Nav -->
      <nav class="desktop-nav">
        <a href="#work">Work</a>
        <a href="#about">About</a>
        <a href="#stack">Stack</a>
        <a href="#contact">Contact</a>
      </nav>

      <!-- Mobile Hamburger -->
      <button 
        class="hamburger" 
        :class="{ 'is-active': isMobileMenuOpen }"
        @click="toggleMobileMenu"
        aria-label="Toggle Navigation"
      >
        <div class="hamburger-box">
          <div class="hamburger-inner"></div>
        </div>
      </button>
    </div>
  </header>

  <!-- Mobile Menu Overlay -->
  <div class="mobile-overlay" :class="{ 'is-open': isMobileMenuOpen }">
    <nav class="mobile-nav">
      <a href="#work" @click="closeMobileMenu">Work</a>
      <a href="#about" @click="closeMobileMenu">About</a>
      <a href="#stack" @click="closeMobileMenu">Stack</a>
      <a href="#contact" @click="closeMobileMenu">Contact</a>
    </nav>
  </div>

  <main>
    <RouterView />
  </main>
</template>

<style scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 80px;
  z-index: 100;
  display: flex;
  align-items: center;
  background-color: transparent;
  transition: all 0.3s ease;
}

header.is-scrolled {
  background-color: rgba(74, 52, 42, 0.9); /* Espresso with opacity */
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-bottom: 1px solid rgba(215, 201, 184, 0.1); /* Khaki subtle */
  height: 64px;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo a {
  font-family: var(--font-heading);
  font-weight: 700;
  font-size: 24px;
  color: var(--color-nuage-de-lait);
  letter-spacing: -0.02em;
}

/* Desktop Nav */
.desktop-nav {
  display: none;
}

@media (min-width: 768px) {
  .desktop-nav {
    display: flex;
    gap: var(--spacing-lg);
  }

  .desktop-nav a {
    font-size: 15px;
    font-weight: 500;
    color: var(--color-camel);
    position: relative;
    padding-bottom: 4px;
  }

  /* Sweep underline effect */
  .desktop-nav a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: var(--color-terre-cuite);
    transition: width 0.2s ease;
  }

  .desktop-nav a:hover,
  .desktop-nav a:focus-visible {
    color: var(--color-terre-cuite);
  }

  .desktop-nav a:hover::after,
  .desktop-nav a:focus-visible::after {
    width: 100%;
  }
}

/* Hamburger Button */
.hamburger {
  display: inline-block;
  cursor: pointer;
  background-color: transparent;
  border: 0;
  margin: 0;
  padding: 10px;
  z-index: 200; /* Above overlay */
  position: relative;
}

@media (min-width: 768px) {
  .hamburger {
    display: none;
  }
}

.hamburger-box {
  width: 24px;
  height: 18px;
  display: inline-block;
  position: relative;
}

.hamburger-inner {
  display: block;
  top: 50%;
  margin-top: -1px;
}

.hamburger-inner,
.hamburger-inner::before,
.hamburger-inner::after {
  width: 24px;
  height: 2px;
  background-color: var(--color-camel);
  border-radius: 2px;
  position: absolute;
  transition: transform 0.2s ease, background-color 0.2s ease;
}

.hamburger-inner::before,
.hamburger-inner::after {
  content: "";
  display: block;
}

.hamburger-inner::before {
  top: -8px;
}
.hamburger-inner::after {
  bottom: -8px;
}

/* Hamburger active state */
.hamburger.is-active .hamburger-inner {
  transform: rotate(45deg);
}

.hamburger.is-active .hamburger-inner::before {
  top: 0;
  opacity: 0;
}

.hamburger.is-active .hamburger-inner::after {
  bottom: 0;
  transform: rotate(-90deg);
}

/* Mobile Overlay */
.mobile-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: var(--color-espresso);
  z-index: 90;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s ease;
}

.mobile-overlay.is-open {
  opacity: 1;
  pointer-events: auto;
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-lg);
  transform: translateY(20px);
  transition: transform 0.3s ease;
}

.mobile-overlay.is-open .mobile-nav {
  transform: translateY(0);
}

.mobile-nav a {
  font-family: var(--font-heading);
  font-size: 32px;
  font-weight: 700;
  color: var(--color-camel);
}

.mobile-nav a:hover,
.mobile-nav a:focus-visible {
  color: var(--color-terre-cuite);
}

main {
  width: 100%;
}
</style>
