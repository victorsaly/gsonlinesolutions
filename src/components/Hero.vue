<template>
  <section class="hero">
    <!-- Slider Container -->
    <div class="hero-slider">
      <div 
        class="slide" 
        v-for="(slide, index) in slides" 
        :key="index"
        :class="{ active: currentSlide === index }"
        :style="{ backgroundImage: `url(${slide.background})` }"
      >
        <div class="hero-background">
          <div class="parallax-layer parallax-back">
            <div class="parallax-element element-1"></div>
            <div class="parallax-element element-2"></div>
            <div class="parallax-element element-3"></div>
          </div>
          <div class="parallax-layer parallax-mid">
            <div class="parallax-grid"></div>
          </div>
          <div class="hero-gradient"></div>
          <div class="floating-shapes">
            <div class="shape shape-1"></div>
            <div class="shape shape-2"></div>
            <div class="shape shape-3"></div>
            <div class="shape shape-4"></div>
            <div class="shape shape-5"></div>
          </div>
        </div>
        
        <div class="container">
          <div class="hero-content">
            <div class="hero-text">
              <h1 class="hero-title slide-in-left">
                {{ slide.title }}
                <span class="highlight">{{ slide.highlight }}</span>
              </h1>
              
              <p class="hero-description slide-in-left" style="transition-delay: 0.2s">
                {{ slide.description }}
              </p>
              
              <div class="hero-actions slide-in-left" style="transition-delay: 0.4s">
                <a href="#services" class="btn btn-primary btn-large">
                  {{ slide.primaryAction }}
                </a>
                <a href="#contact" class="btn btn-secondary btn-large">
                  {{ slide.secondaryAction }}
                </a>
              </div>
              
              <div class="hero-features slide-in-left" style="transition-delay: 0.6s">
                <div class="feature-item" v-for="feature in slide.features" :key="feature">
                  <svg width="20" height="20" viewBox="0 0 20 20" fill="var(--primary)">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                  </svg>
                  <span>{{ feature }}</span>
                </div>
              </div>
            </div>
            
            <div class="hero-visual slide-in-right">
              <div class="hero-card">
                <div class="card-header">
                  <h3>{{ slide.cardTitle }}</h3>
                </div>
                <div class="card-content">
                  <div class="metric" v-for="metric in slide.metrics" :key="metric.label">
                    <div class="metric-value">{{ metric.value }}</div>
                    <div class="metric-label">{{ metric.label }}</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Slider Navigation -->
    <div class="slider-navigation">
      <!-- Previous/Next arrows -->
      <button class="nav-arrow nav-prev" @click="previousSlide" aria-label="Previous slide">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="white">
          <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"/>
        </svg>
      </button>
      
      <button class="nav-arrow nav-next" @click="nextSlide" aria-label="Next slide">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="white">
          <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"/>
        </svg>
      </button>
      
      <!-- Dots navigation -->
      <div class="slider-dots">
        <button 
          class="dot" 
          v-for="(slide, index) in slides" 
          :key="index"
          :class="{ active: currentSlide === index }"
          @click="goToSlide(index)"
          :aria-label="`Go to slide ${index + 1}`"
        ></button>
      </div>
    </div>
    
    <div class="hero-scroll-indicator">
      <div class="scroll-arrow"></div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

// Slider state
const currentSlide = ref(0)
let slideInterval = null
let ticking = false

// Slider data
const slides = ref([
  {
    background: '/hero-bg-1.svg',
    title: 'Transform Your Business Finances',
    highlight: 'with Expert Care',
    description: 'Founded by Gosia Saly, GS Online Solutions provides personalized accounting and financial solutions for growing businesses. With fresh expertise and dedicated attention, we help you build a solid financial foundation for success.',
    primaryAction: 'Explore Our Services',
    secondaryAction: 'Book a Consultation',
    features: ['Personal Attention', 'Modern Approach', 'Transparent Pricing'],
    cardTitle: 'Building Success Together',
    metrics: [
      { value: '1+', label: 'Year in Business' },
      { value: '50+', label: 'Happy Clients' },
      { value: '100%', label: 'Dedication' }
    ]
  },
  {
    background: '/hero-bg-2.svg',
    title: 'Modern Cloud Accounting',
    highlight: 'for Digital Businesses',
    description: 'Leverage cutting-edge technology with our Xero-certified expertise. We help modern businesses streamline their finances with cloud-based solutions that provide real-time insights and seamless collaboration.',
    primaryAction: 'Discover Technology',
    secondaryAction: 'Schedule Demo',
    features: ['Xero Certified', 'Cloud-Based', 'Real-Time Reports'],
    cardTitle: 'Digital Excellence',
    metrics: [
      { value: 'Xero', label: 'Certified Partner' },
      { value: '24/7', label: 'Cloud Access' },
      { value: '100%', label: 'Digital Workflow' }
    ]
  },
  {
    background: '/hero-bg-3.svg',
    title: 'Scale Your Business',
    highlight: 'with Confidence',
    description: 'As your business grows, we grow with you. Our scalable financial solutions and expert partnerships ensure you have the right support at every stage of your journey, from startup to enterprise.',
    primaryAction: 'Growth Solutions',
    secondaryAction: 'Start Planning',
    features: ['Scalable Solutions', 'Expert Partnerships', 'Growth Focused'],
    cardTitle: 'Your Growth Partner',
    metrics: [
      { value: '∞', label: 'Growth Potential' },
      { value: 'ICB', label: 'Professional Member' },
      { value: '360°', label: 'Full Support' }
    ]
  }
])

// Slider functionality
const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.value.length
  resetSlideInterval()
}

const previousSlide = () => {
  currentSlide.value = currentSlide.value === 0 ? slides.value.length - 1 : currentSlide.value - 1
  resetSlideInterval()
}

const goToSlide = (index) => {
  currentSlide.value = index
  resetSlideInterval()
}

const startSlideInterval = () => {
  slideInterval = setInterval(nextSlide, 6000) // 6 seconds per slide
}

const resetSlideInterval = () => {
  if (slideInterval) {
    clearInterval(slideInterval)
  }
  startSlideInterval()
}

// Parallax handling
const handleScroll = () => {
  if (!ticking) {
    requestAnimationFrame(() => {
      const scrolled = window.pageYOffset
      const rate = scrolled * -0.6
      const rateMid = scrolled * -0.4
      const rateFront = scrolled * -0.15

      // Parallax background layers
      const backLayer = document.querySelector('.parallax-back')
      const midLayer = document.querySelector('.parallax-mid')
      const shapes = document.querySelector('.floating-shapes')
      
      if (backLayer) {
        backLayer.style.transform = `translateY(${rate}px)`
      }
      
      if (midLayer) {
        midLayer.style.transform = `translateY(${rateMid}px)`
      }
      
      if (shapes) {
        shapes.style.transform = `translateY(${rateFront}px)`
      }

      // Individual element animations with enhanced movement
      const elements = document.querySelectorAll('.parallax-element')
      elements.forEach((element, index) => {
        const speed = 0.3 + (index * 0.15)
        const yPos = -(scrolled * speed)
        const rotation = scrolled * 0.08
        element.style.transform = `translateY(${yPos}px) rotate(${rotation}deg) scale(${1 + Math.sin(scrolled * 0.001) * 0.05})`
      })
      
      ticking = false
    })
    ticking = true
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
  handleScroll() // Initial call
  startSlideInterval() // Start auto-sliding
  
  // Initialize scroll animations
  setTimeout(() => {
    const options = {
      root: null,
      rootMargin: '0px 0px -100px 0px',
      threshold: 0.1
    }

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate-in')
        }
      })
    }, options)

    // Observe elements with animation classes
    const animationElements = document.querySelectorAll('.slide-in-left, .slide-in-right, .slide-in-up, .fade-in-up, .fade-in-up-delay, .fade-in-up-delay-2')
    animationElements.forEach(el => observer.observe(el))
  }, 100)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  if (slideInterval) {
    clearInterval(slideInterval)
  }
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
}

/* Slider Container */
.hero-slider {
  position: relative;
  width: 100%;
  height: 100%;
}

.slide {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 1s ease-in-out;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.slide.active {
  opacity: 1;
}

/* Slide content animations */
.slide:not(.active) .slide-in-left,
.slide:not(.active) .slide-in-right {
  opacity: 0;
  transform: translateX(-30px);
}

.slide.active .slide-in-left {
  opacity: 1;
  transform: translateX(0);
  transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.slide.active .slide-in-right {
  opacity: 1;
  transform: translateX(0);
  transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

/* Slider Navigation */
.slider-navigation {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
  gap: 2rem;
  z-index: 20;
}

.nav-arrow {
  background: rgba(82, 115, 108, 0.8);
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.nav-arrow:hover {
  background: rgba(82, 115, 108, 1);
  transform: scale(1.1);
}

.nav-prev {
  order: -1;
}

.nav-next {
  order: 1;
}

.slider-dots {
  display: flex;
  gap: 0.75rem;
  align-items: center;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.6);
  background: transparent;
  cursor: pointer;
  transition: all 0.3s ease;
}

.dot.active {
  background: white;
  border-color: white;
  transform: scale(1.2);
}

.dot:hover {
  border-color: white;
  background: rgba(255, 255, 255, 0.5);
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, var(--gray-50) 0%, var(--white) 100%);
}

.hero-gradient {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, 
    rgba(82, 115, 108, 0.025) 0%, 
    rgba(135, 115, 94, 0.025) 50%, 
    transparent 100%
  );
  z-index: 4;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 10;
  transform: translateZ(0); /* Hardware acceleration */
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 300;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  color: var(--primary);
}

.highlight {
  color: var(--secondary);
}

.hero-description {
  font-size: 1.25rem;
  line-height: 1.6;
  color: var(--gray-600);
  margin-bottom: 2rem;
  font-weight: 300;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  margin-bottom: 3rem;
}

.hero-features {
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--gray-600);
  font-weight: 500;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-card {
  background: var(--white);
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 
    0 20px 25px -5px rgba(0, 0, 0, 0.1),
    0 10px 10px -5px rgba(0, 0, 0, 0.04);
  border: 1px solid var(--gray-100);
  max-width: 400px;
  width: 100%;
}

.card-header {
  margin-bottom: 1.5rem;
  text-align: center;
}

.card-header h3 {
  color: var(--primary);
  font-size: 1.25rem;
  margin: 0;
}

.card-content {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.metric {
  text-align: center;
  padding: 1rem 0;
}

.metric-value {
  font-size: 2rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 0.25rem;
}

.metric-label {
  font-size: 0.875rem;
  color: var(--gray-600);
  font-weight: 500;
}

.hero-scroll-indicator {
  position: absolute;
  bottom: 6rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
}

.scroll-arrow {
  width: 24px;
  height: 24px;
  border: 2px solid var(--primary);
  border-left: 0;
  border-top: 0;
  transform: rotate(45deg);
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0) rotate(45deg);
  }
  40% {
    transform: translateY(-10px) rotate(45deg);
  }
  60% {
    transform: translateY(-5px) rotate(45deg);
  }
}

/* Mobile Styles */
@media (max-width: 768px) {
  .hero {
    min-height: 90vh;
    padding-top: 60px;
  }
  
  .hero-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-description {
    font-size: 1.125rem;
  }
  
  .hero-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-large {
    width: 100%;
    max-width: 300px;
  }
  
  .hero-features {
    justify-content: center;
    gap: 1rem;
  }
  
  .feature-item {
    flex-direction: column;
    text-align: center;
    gap: 0.25rem;
    font-size: 0.875rem;
  }
  
  .hero-card {
    padding: 1.5rem;
  }
  
  .card-content {
    gap: 0.5rem;
  }
  
  .metric-value {
    font-size: 1.5rem;
  }
  
  /* Mobile slider navigation */
  .slider-navigation {
    bottom: 1rem;
    gap: 1.5rem;
  }
  
  .nav-arrow {
    width: 40px;
    height: 40px;
  }
  
  .slider-dots {
    gap: 0.5rem;
  }
  
  .dot {
    width: 10px;
    height: 10px;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-features {
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
  }
}

/* Parallax Background Layers */
.parallax-layer {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 120%;
  will-change: transform;
  transform: translateZ(0); /* Hardware acceleration */
}

.parallax-back {
  z-index: 1;
}

.parallax-mid {
  z-index: 2;
}

.parallax-element {
  position: absolute;
  background: linear-gradient(135deg, rgba(82, 115, 108, 0.25), rgba(135, 115, 94, 0.15));
  border-radius: 50%;
  will-change: transform;
  transform: translateZ(0); /* Hardware acceleration */
  backdrop-filter: blur(3px);
  box-shadow: 0 12px 40px rgba(82, 115, 108, 0.2);
  border: 1px solid rgba(82, 115, 108, 0.1);
}

.element-1 {
  width: 300px;
  height: 300px;
  top: 5%;
  left: -5%;
  animation: float-slow 25s infinite ease-in-out;
}

.element-2 {
  width: 200px;
  height: 200px;
  top: 50%;
  right: -10%;
  animation: float-slow 30s infinite ease-in-out reverse;
}

.element-3 {
  width: 150px;
  height: 150px;
  top: 75%;
  left: 10%;
  animation: float-slow 20s infinite ease-in-out;
}

.parallax-grid {
  position: absolute;
  top: -10%;
  left: -10%;
  width: 120%;
  height: 120%;
  background-image: 
    linear-gradient(rgba(82, 115, 108, 0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(82, 115, 108, 0.08) 1px, transparent 1px);
  background-size: 60px 60px;
  animation: grid-move 50s linear infinite;
  opacity: 0.8;
}



@keyframes float-slow {
  0%, 100% {
    transform: translateY(0px) scale(1) rotate(0deg);
  }
  33% {
    transform: translateY(-30px) scale(1.05) rotate(2deg);
  }
  66% {
    transform: translateY(20px) scale(0.95) rotate(-1deg);
  }
}

@keyframes grid-move {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(60px, 60px);
  }
}

/* Floating Shapes Animation */
.floating-shapes {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 3;
  will-change: transform;
  transform: translateZ(0); /* Hardware acceleration */
}

.shape {
  position: absolute;
  background: rgba(82, 115, 108, 0.3);
  border-radius: 50%;
  animation: float 20s infinite linear;
  will-change: transform;
  backdrop-filter: blur(2px);
  box-shadow: 0 6px 25px rgba(82, 115, 108, 0.2);
  transform: translateZ(0); /* Hardware acceleration */
  border: 1px solid rgba(82, 115, 108, 0.15);
}

.shape-1 {
  width: 80px;
  height: 80px;
  top: 20%;
  left: 10%;
  animation-delay: 0s;
  animation-duration: 25s;
}

.shape-2 {
  width: 120px;
  height: 120px;
  top: 60%;
  right: 15%;
  animation-delay: -5s;
  animation-duration: 30s;
}

.shape-3 {
  width: 60px;
  height: 60px;
  top: 80%;
  left: 20%;
  animation-delay: -10s;
  animation-duration: 20s;
}

.shape-4 {
  width: 100px;
  height: 100px;
  top: 10%;
  right: 25%;
  animation-delay: -15s;
  animation-duration: 35s;
}

.shape-5 {
  width: 40px;
  height: 40px;
  top: 40%;
  left: 60%;
  animation-delay: -20s;
  animation-duration: 15s;
}

@keyframes float {
  0% {
    transform: translateY(0px) rotate(0deg);
    opacity: 0.4;
  }
  25% {
    transform: translateY(-20px) rotate(90deg);
    opacity: 0.7;
  }
  50% {
    transform: translateY(-30px) rotate(180deg);
    opacity: 0.9;
  }
  75% {
    transform: translateY(-10px) rotate(270deg);
    opacity: 0.6;
  }
  100% {
    transform: translateY(0px) rotate(360deg);
    opacity: 0.4;
  }
}

/* Pulse animation for shapes */
.shape:nth-child(odd) {
  animation: float 20s infinite linear, pulse 4s infinite ease-in-out;
}

.shape:nth-child(even) {
  animation: float 20s infinite linear, pulse 6s infinite ease-in-out;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

/* Scroll-triggered animations */
.slide-in-left,
.slide-in-right,
.slide-in-up,
.fade-in-up,
.fade-in-up-delay,
.fade-in-up-delay-2 {
  opacity: 0;
  transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.slide-in-left {
  transform: translateX(-50px);
}

.slide-in-right {
  transform: translateX(50px);
}

.slide-in-up,
.fade-in-up,
.fade-in-up-delay,
.fade-in-up-delay-2 {
  transform: translateY(30px);
}

.fade-in-up-delay {
  transition-delay: 0.2s;
}

.fade-in-up-delay-2 {
  transition-delay: 0.4s;
}

/* Animation active state */
.slide-in-left.animate-in,
.slide-in-right.animate-in,
.slide-in-up.animate-in,
.fade-in-up.animate-in,
.fade-in-up-delay.animate-in,
.fade-in-up-delay-2.animate-in {
  opacity: 1;
  transform: translateX(0) translateY(0);
}
</style>