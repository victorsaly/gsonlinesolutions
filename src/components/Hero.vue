<template>
  <section id="home" class="hero">
    <!-- Hero Slider -->
    <div class="swiper hero-slider">
      <div class="swiper-wrapper">
        <!-- Slide 1 - Bookkeeping -->
        <div class="swiper-slide hero-slide-1">
          <div class="hero-content slide-in-element slide-in-up">
            <h1>Professional <span>Bookkeeping Accounts</span> & Expert Advisory</h1>
            <p>Expert financial management and bookkeeping services tailored for small to medium businesses. Our Xero certified professionals ensure accuracy, compliance, and peace of mind while you focus on growing your business.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-phone-line"></i>
                Get Free Consultation
              </a>
              <a href="#services" class="btn btn-outline">
                <i class="ri-service-line"></i>
                Our Services
              </a>
            </div>
            <!-- Trust Indicators -->
            <div class="trust-indicators">
              <div class="trust-item">
                <img src="/xero-logo.png" alt="Xero Certified" class="cert-logo">
                <span>Xero Certified</span>
              </div>
              <div class="trust-item">
                <img src="/icb_logo.png" alt="ICB Member" class="cert-logo">
                <span>ICB Member</span>
              </div>
              <div class="trust-item">
                <i class="ri-shield-check-line"></i>
                <span>Fully Insured</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Slide 2 - Tax Preparation -->
        <div class="swiper-slide hero-slide-2">
          <div class="hero-content slide-in-element slide-in-up">
            <h1><span>Tax Preparation</span> & Compliance Solutions</h1>
            <p>Navigate tax season with confidence. Our expert team ensures accurate filing, maximum deductions, and compliance with all regulations for individuals and businesses.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-calculator-line"></i>
                Start Tax Planning
              </a>
              <a href="#about" class="btn btn-outline">
                <i class="ri-team-line"></i>
                Meet Our Team
              </a>
            </div>
            <!-- Stats -->
            <div class="hero-stats">
              <div class="stat-item">
                <span class="stat-number">500+</span>
                <span class="stat-label">Happy Clients</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">10+</span>
                <span class="stat-label">Years Experience</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">99%</span>
                <span class="stat-label">Accuracy Rate</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Slide 3 - Financial Consulting -->
        <div class="swiper-slide hero-slide-3">
          <div class="hero-content slide-in-element slide-in-up">
            <h1>Strategic <span>Financial Advisory</span> & Growth Planning</h1>
            <p>Strategic financial guidance to help your business thrive. From cash flow management to growth planning, we provide insights that drive success.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-line-chart-line"></i>
                Schedule Strategy Call
              </a>
              <a href="#testimonials" class="btn btn-outline">
                <i class="ri-customer-service-2-line"></i>
                Success Stories
              </a>
            </div>
            <!-- Features -->
            <div class="hero-features">
              <div class="feature-item">
                <i class="ri-calculator-line"></i>
                <span>Accurate Calculations</span>
              </div>
              <div class="feature-item">
                <i class="ri-file-shield-line"></i>
                <span>Tax Compliance</span>
              </div>
              <div class="feature-item">
                <i class="ri-award-line"></i>
                <span>Certified Experts</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Navigation -->
      <div class="swiper-button-next"></div>
      <div class="swiper-button-prev"></div>
      
      <!-- Pagination -->
      <div class="swiper-pagination"></div>
    </div>

    <!-- Scroll Indicator -->
    <div class="scroll-indicator">
      <a href="#services" class="scroll-link">
        <div class="scroll-mouse">
          <div class="scroll-wheel"></div>
        </div>
        <span>Scroll Down</span>
        <i class="ri-arrow-down-line"></i>
      </a>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Initialize Swiper when component mounts
  setTimeout(() => {
    if (window.Swiper) {
      const heroSwiper = new window.Swiper('.hero-slider', {
        loop: true,
        autoplay: {
          delay: 8000,
          disableOnInteraction: false,
        },
        effect: 'fade',
        fadeEffect: {
          crossFade: true
        },
        speed: 2000,
        allowTouchMove: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
        // Add smooth parallax effect
        on: {
          slideChangeTransitionStart: function () {
            // Add zoom out effect to current slide
            const activeSlide = this.slides[this.activeIndex];
            if (activeSlide) {
              activeSlide.style.transform = 'scale(1.05)';
            }
          },
          slideChangeTransitionEnd: function () {
            // Reset all slides
            this.slides.forEach(slide => {
              slide.style.transform = 'scale(1)';
            });
            // Add zoom in effect to new active slide
            const activeSlide = this.slides[this.activeIndex];
            if (activeSlide) {
              activeSlide.style.transform = 'scale(1.02)';
            }
          }
        }
      })
    }
  }, 100)
})
</script>

<style scoped>
.hero {
  height: 100vh;
  position: relative;
  overflow: hidden;
}

.hero-slider {
  height: 100%;
  width: 100%;
}

.swiper-slide {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-size: cover;
  background-position: center;
  color: var(--whiteColor);
  position: relative;
  overflow: hidden;
}

.hero-slide-1 {
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.65), rgba(57, 55, 55, 0.55)), url('/hero/hero_slide_1.jpg');
  background-size: cover;
  background-position: center;
}

.hero-slide-1::before {
  content: '';
  position: absolute;
  top: -10%;
  left: -10%;
  width: 120%;
  height: 120%;
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.65), rgba(57, 55, 55, 0.55)), url('/hero/hero_slide_1.jpg');
  background-size: cover;
  background-position: center;
  animation: slowZoom 12s ease-in-out infinite alternate;
  z-index: -1;
}

.hero-slide-2 {
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.75), rgba(57, 55, 55, 0.65)), url('/services/service-2.jpg');
  background-size: cover;
  background-position: center;
}

.hero-slide-2::before {
  content: '';
  position: absolute;
  top: -10%;
  left: -10%;
  width: 120%;
  height: 120%;
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.75), rgba(57, 55, 55, 0.65)), url('/services/service-2.jpg');
  background-size: cover;
  background-position: center;
  animation: slowZoom 15s ease-in-out infinite alternate;
  z-index: -1;
}

.hero-slide-3 {
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.75), rgba(57, 55, 55, 0.65)), url('/services/service-3.jpg');
  background-size: cover;
  background-position: center;
}

.hero-slide-3::before {
  content: '';
  position: absolute;
  top: -10%;
  left: -10%;
  width: 120%;
  height: 120%;
  background: linear-gradient(135deg, rgba(0, 37, 44, 0.75), rgba(57, 55, 55, 0.65)), url('/services/service-3.jpg');
  background-size: cover;
  background-position: center;
  animation: slowZoom 18s ease-in-out infinite alternate;
  z-index: -1;
}



.hero-content {
  text-align: center;
  max-width: 800px;
  padding: 0 20px;
  position: relative;
  z-index: 10;
  animation: floatContent 8s ease-in-out infinite;
}

/* Smooth zoom animation for backgrounds */
@keyframes slowZoom {
  0% {
    transform: scale(1) rotate(0deg);
  }
  100% {
    transform: scale(1.1) rotate(0.5deg);
  }
}

/* Floating animation for content */
@keyframes floatContent {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-8px);
  }
}

/* Add professional accounting decorative elements */
.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%23B9F8B1" opacity="0.08"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>'),
    url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%23B9F8B1" opacity="0.06"><path d="M11.8 10.9c-2.27-.59-3-1.2-3-2.15 0-1.09 1.01-1.85 2.7-1.85 1.78 0 2.44.85 2.5 2.1h2.21c-.07-1.72-1.12-3.3-3.21-3.81V3h-3v2.16c-1.94.42-3.5 1.68-3.5 3.61 0 2.31 1.91 3.46 4.7 4.13 2.5.6 3 1.48 3 2.41 0 .69-.49 1.79-2.7 1.79-2.06 0-2.87-.92-2.98-2.1h-2.2c.12 2.19 1.76 3.42 3.68 3.83V21h3v-2.15c1.95-.37 3.5-1.5 3.5-3.55 0-2.84-2.43-3.81-4.7-4.4z"/></svg>'),
    url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%23B9F8B1" opacity="0.05"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/></svg>');
  background-position: 85% 15%, 15% 85%, 50% 50%;
  background-repeat: no-repeat;
  background-size: 80px 80px, 60px 60px, 100px 100px;
  z-index: 1;
  pointer-events: none;
}

/* Swiper Navigation Styling */
.swiper-button-next,
.swiper-button-prev {
  color: var(--whiteColor);
  background: rgba(255, 255, 255, 0.2);
  width: 50px;
  height: 50px;
  border-radius: 50%;
  backdrop-filter: blur(10px);
}

.swiper-button-next:after,
.swiper-button-prev:after {
  font-size: 18px;
}

.swiper-pagination-bullet {
  background: rgba(255, 255, 255, 0.5);
  opacity: 1;
}

.swiper-pagination-bullet-active {
  background: var(--secondaryColor);
}

/* Trust indicators styling */
.trust-indicators {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 40px;
  flex-wrap: wrap;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 8px;
  color: var(--whiteColor);
  font-size: 14px;
}

.trust-item span {
  color: var(--whiteColor) !important;
}

.cert-logo {
  height: 50px;
}

.trust-item i {
  font-size: 20px;
  color: var(--secondaryColor);
}

/* Scroll Indicator Styling */
.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: var(--whiteColor);
  z-index: 10;
  animation: bounce 2s infinite;
}

.scroll-link {
  color: inherit;
  text-decoration: none;
  display: block;
}

.scroll-link:hover {
  color: var(--secondaryColor);
}

.scroll-mouse {
  width: 24px;
  height: 36px;
  border: 2px solid rgba(255, 255, 255, 0.8);
  border-radius: 15px;
  margin: 0 auto 10px;
  position: relative;
}

.scroll-wheel {
  width: 2px;
  height: 6px;
  background: var(--whiteColor);
  border-radius: 2px;
  position: absolute;
  top: 6px;
  left: 50%;
  transform: translateX(-50%);
  animation: scroll 2s infinite;
}

.scroll-indicator span {
  display: block;
  font-size: 12px;
  margin: 5px 0;
  opacity: 0.8;
}

.scroll-indicator i {
  font-size: 16px;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  40% {
    transform: translateX(-50%) translateY(-10px);
  }
  60% {
    transform: translateX(-50%) translateY(-5px);
  }
}

@keyframes scroll {
  0% {
    transform: translateX(-50%) translateY(0);
    opacity: 1;
  }
  100% {
    transform: translateX(-50%) translateY(18px);
    opacity: 0;
  }
}

/* Hero Features Styling */
.hero-features {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 30px;
  flex-wrap: wrap;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 8px;
  color: var(--whiteColor);
  font-size: 14px;
  opacity: 0.9;
}

.feature-item i {
  font-size: 18px;
  color: var(--secondaryColor);
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 24px;
}

.hero span {
  color: var(--secondaryColor);
}

.hero p {
  font-size: 1.25rem;
  margin-bottom: 40px;
  opacity: 1;
  color: rgba(255, 255, 255, 0.95);
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  background: rgba(0, 37, 44, 0.2);
  padding: 12px 20px;
  border-radius: 8px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.hero-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

.hero-buttons .btn {
  padding: 16px 32px;
  font-size: 16px;
  font-weight: 600;
  border-radius: 8px;
  text-decoration: none;
  min-width: 180px;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.5rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
}
</style>
