<template>
  <header class="header">
    <div class="container">
      <nav class="nav">
        <div class="nav-brand">
          <a href="/" class="brand-link">
            <img src="/logo_gs.svg" alt="GS Online Services" class="logo" />
          </a>
        </div>
        
        <div class="nav-menu" :class="{ 'nav-menu-open': isMenuOpen }">
          <a href="#services" class="nav-link" @click="closeMenu">Services</a>
          <a href="#about" class="nav-link" @click="closeMenu">About</a>
          <a href="#contact" class="nav-link" @click="closeMenu">Contact</a>
          <a href="#contact" class="btn btn-primary" @click="closeMenu">Get Started</a>
        </div>
        
        <button 
          class="nav-toggle"
          @click="toggleMenu"
          :class="{ active: isMenuOpen }"
          aria-label="Toggle menu"
        >
          <span></span>
          <span></span>
          <span></span>
        </button>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

// Close menu when clicking outside
const handleClickOutside = (event) => {
  if (!event.target.closest('.nav-menu') && !event.target.closest('.nav-toggle')) {
    isMenuOpen.value = false
  }
}

if (typeof window !== 'undefined') {
  document.addEventListener('click', handleClickOutside)
}
</script>

<style scoped>
.header {
  background: var(--white);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 0;
}

.nav-brand {
  flex-shrink: 0;
}

.brand-link {
  display: flex;
  align-items: center;
}

.logo {
  height: 45px;
  width: auto;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  font-weight: 500;
  color: var(--gray-800);
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: var(--primary);
}

.nav-toggle {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  padding: 0.5rem;
  cursor: pointer;
  gap: 3px;
}

.nav-toggle span {
  width: 25px;
  height: 3px;
  background: var(--primary);
  transition: all 0.3s ease;
  transform-origin: center;
}

.nav-toggle.active span:first-child {
  transform: rotate(45deg) translate(6px, 6px);
}

.nav-toggle.active span:nth-child(2) {
  opacity: 0;
}

.nav-toggle.active span:last-child {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* Mobile Styles */
@media (max-width: 768px) {
  .nav-toggle {
    display: flex;
  }
  
  .nav-menu {
    position: fixed;
    top: 100%;
    left: 0;
    right: 0;
    background: var(--white);
    flex-direction: column;
    padding: 2rem;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }
  
  .nav-menu-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }
  
  .nav-link {
    padding: 0.5rem 0;
    width: 100%;
    text-align: center;
  }
}
</style>