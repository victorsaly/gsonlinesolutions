<template>
  <section id="home" class="hero">
    <!-- Hero Slider -->
    <div class="swiper hero-slider-one">
      <div class="swiper-wrapper">
        <!-- Slide 1 - Bookkeeping -->
        <div class="swiper-slide hero-slide">
          <div class="hero-content slide-in-element slide-in-up">
            <h1>Transform Your <span>Business Finances</span> with Expert Bookkeeping</h1>
            <p>Stop worrying about numbers and start growing your business. Our Xero-certified professionals deliver accurate, compliant financial management that saves you time and money while providing the insights you need to make confident decisions.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-phone-line"></i>
                Get Free Consultation
              </a>
              <a href="#services" class="btn btn-outline">
                <i class="ri-service-line"></i>
                View All Services
              </a>
            </div>
            <!-- Trust Indicators -->
            <div class="trust-indicators">
              <div class="trust-item">
                <img src="/gsonlinesolutions/xero-logo.png" alt="Xero Certified" class="cert-logo">
                <span>Xero Certified Partner</span>
              </div>
              <div class="trust-item">
                <img src="/gsonlinesolutions/icb_logo.png" alt="ICB Member" class="cert-logo">
                <span>ICB Qualified</span>
              </div>
              <div class="trust-item">
                <i class="ri-shield-check-line"></i>
                <span>Fully Insured & Bonded</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Slide 2 - Tax Preparation -->
        <div class="swiper-slide hero-slide">
          <div class="hero-content slide-in-element slide-in-up">
            <h1>Maximize Your <span>Tax Savings</span> with Expert Planning</h1>
            <p>Don't leave money on the table. Our tax experts ensure you claim every deduction while staying fully compliant. From corporation tax to VAT returns, we handle the complexity so you can focus on what matters most - your business success.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-calculator-line"></i>
                Book Tax Review
              </a>
              <a href="/services/tax-preparation" class="btn btn-outline">
                <i class="ri-file-list-3-line"></i>
                Tax Services
              </a>
            </div>
            <!-- Stats -->
            <div class="hero-stats">
              <div class="stat-item">
                <span class="stat-number">£50K+</span>
                <span class="stat-label">Average Annual Savings</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">15+</span>
                <span class="stat-label">Years Experience</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">99.9%</span>
                <span class="stat-label">Accuracy Rate</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Slide 3 - Financial Advisory -->
        <div class="swiper-slide hero-slide">
          <div class="hero-content slide-in-element slide-in-up">
            <h1>Scale Your Business with <span>Strategic Financial Leadership</span></h1>
            <p>Get C-level financial expertise without the C-level cost. Our fractional CFO services provide strategic insights, cash flow optimization, and growth planning that transforms good businesses into great ones.</p>
            <div class="hero-buttons">
              <a href="#contact" class="btn btn-primary">
                <i class="ri-line-chart-line"></i>
                Schedule Strategy Session
              </a>
              <a href="/services/financial-controller" class="btn btn-outline">
                <i class="ri-presentation-line"></i>
                Learn More
              </a>
            </div>
            <!-- Features -->
            <div class="hero-features">
              <div class="feature-item">
                <i class="ri-funds-line"></i>
                <span>Cash Flow Management</span>
              </div>
              <div class="feature-item">
                <i class="ri-line-chart-line"></i>
                <span>Financial Planning</span>
              </div>
              <div class="feature-item">
                <i class="ri-trophy-line"></i>
                <span>Growth Strategy</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Navigation Arrows (keep for additional navigation) -->
      <div class="swiper-button-next"></div>
      <div class="swiper-button-prev"></div>
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
import { onMounted, nextTick, onBeforeUnmount } from 'vue'

// Store swiper instance for cleanup
let heroSwiper = null;

// Alternative initialization for when CDN loads
const initializeSwiperWhenReady = () => {
  if (typeof window !== 'undefined' && window.Swiper && document.querySelector('.hero-slider-one')) {
    console.log('✅ Swiper found! Initializing...');
    
    try {
      heroSwiper = new window.Swiper('.hero-slider-one', {
        spaceBetween: 0,
        speed: 800,
        effect: "slide", // Changed from fade to slide
        autoplay: {
          delay: 8000, // 8 seconds per slide
          disableOnInteraction: false,
        },
        loop: true,
        allowTouchMove: true,
        
        // Better mobile touch handling
        touchRatio: 1,
        touchAngle: 45,
        simulateTouch: true,
        
        // Responsive breakpoints for better mobile experience
        breakpoints: {
          320: {
            slidesPerView: 1,
            spaceBetween: 0,
            speed: 600,
          },
          768: {
            slidesPerView: 1,
            spaceBetween: 0,
            speed: 800,
          }
        },
        
        // Keep navigation buttons for additional control
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
        
        // Event callbacks
        on: {
          slideChange: function () {
            console.log('🔄 Slide changed to:', this.activeIndex + 1);
          },
          init: function () {
            console.log('🎉 Swiper initialized successfully!');
          },
          slideChangeTransitionStart: function () {
            // Simple transition without scaling
            console.log('Slide transition started');
          },
          slideChangeTransitionEnd: function () {
            // Transition completed
            console.log('Slide transition completed');
          }
        }
      });

      // Store reference for debugging
      window.heroSwiper = heroSwiper;
      console.log('🚀 Hero slider is ready!');
      
      return true;
    } catch (error) {
      console.error('❌ Error initializing Swiper:', error);
      return false;
    }
  }
  return false;
};

// Check if we can initialize immediately
const quickInitCheck = () => {
  if (window.swiperLoaded && window.Swiper) {
    console.log('🚀 Quick init: Swiper already loaded!');
    return initializeSwiperWhenReady();
  }
  return false;
};

onMounted(() => {
  // More robust initialization with better error handling and timeout
  let attempts = 0;
  const maxAttempts = 50; // Try for up to 10 seconds
  
  const initializeSwiper = () => {
    attempts++;
    
    if (initializeSwiperWhenReady()) {
      return; // Success!
    }
    
    if (attempts < maxAttempts) {
      console.log(`⏳ Swiper not available yet, retrying... (Attempt ${attempts}/${maxAttempts})`);
      setTimeout(initializeSwiper, 200);
    } else {
      console.error('❌ Failed to load Swiper library after', maxAttempts, 'attempts');
      console.log('💡 Checking if Swiper CDN is accessible...');
      
      // Try to check if the script tag exists
      const swiperScript = document.querySelector('script[src*="swiper"]');
      if (swiperScript) {
        console.log('📦 Swiper script tag found:', swiperScript.src);
      } else {
        console.log('❌ No Swiper script tag found in DOM');
      }
      
      // Fallback: try to load Swiper manually
      if (!window.Swiper) {
        console.log('🔄 Attempting manual Swiper load...');
        const script = document.createElement('script');
        script.src = 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js';
        script.onload = () => {
          console.log('📦 Swiper manually loaded, attempting initialization...');
          setTimeout(() => initializeSwiperWhenReady(), 100);
        };
        script.onerror = () => {
          console.error('❌ Failed to manually load Swiper from CDN');
        };
        document.head.appendChild(script);
      }
    }
  };

  // Wait for DOM to be ready and start initialization
  nextTick(() => {
    console.log('🔧 Starting Swiper initialization...');
    
    // Try quick initialization first
    if (quickInitCheck()) {
      return;
    }
    
    // Otherwise, start the retry loop
    setTimeout(initializeSwiper, 100);
  });
})

// Cleanup on component unmount
onBeforeUnmount(() => {
  if (heroSwiper) {
    heroSwiper.destroy(true, true);
    console.log('🧹 Swiper instance destroyed');
  }
})
</script>

<style scoped>
.hero {
  height: 100vh;
  min-height: calc(100vh - 120px); /* Account for desktop navbar */
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #00252c 0%, #1a4b56 50%, #2d6a77 100%);
  padding-top: 120px; /* Space for fixed navbar */
}

.hero-slider-one {
  height: 100%;
  width: 100%;
  background: linear-gradient(135deg, #00252c 0%, #1a4b56 50%, #2d6a77 100%);
}

.swiper-wrapper {
  background: linear-gradient(135deg, #00252c 0%, #1a4b56 50%, #2d6a77 100%);
}

.swiper-slide {
  height: calc(100vh - 120px);
  min-height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-size: cover;
  background-position: center;
  color: #ffffff;
  position: relative;
  overflow: hidden;
  padding: 80px 20px 60px 20px;
}

/* Hero Slide Base Styling - Ensure all slides have background */
.hero-slide {
  background-size: cover !important;
  background-position: center !important;
  background-attachment: scroll; /* Better for mobile performance */
  min-height: calc(100vh - 120px);
  position: relative;
  /* Ensure touch events work properly on mobile */
  touch-action: pan-y;
}

/* Individual slides with the same background image and overlays */
.hero-slide:nth-child(1) {
  background: 
    linear-gradient(135deg, rgba(0, 37, 44, 0.8), rgba(26, 75, 86, 0.7)), 
    url('/gsonlinesolutions/hero/hero_slide_1.jpg');
  background-size: cover;
  background-position: center;
}

.hero-slide:nth-child(2) {
  background: 
    linear-gradient(135deg, rgba(0, 37, 44, 0.8), rgba(26, 75, 86, 0.7)), 
    url('/gsonlinesolutions/hero/hero_slide_1.jpg');
  background-size: cover;
  background-position: center;
}

.hero-slide:nth-child(3) {
  background: 
    linear-gradient(135deg, rgba(0, 37, 44, 0.8), rgba(26, 75, 86, 0.7)), 
    url('/gsonlinesolutions/hero/hero_slide_1.jpg');
  background-size: cover;
  background-position: center;
}

/* Fallback for missing images */
.hero-slide:nth-child(1),
.hero-slide:nth-child(2),
.hero-slide:nth-child(3) {
  /* Fallback solid background if images don't load */
  background-color: #1a4b56;
}

/* Remove pseudo-element animations to prevent size issues during transitions */



.hero-content {
  text-align: center;
  max-width: 800px;
  padding: 0 20px;
  position: relative;
  z-index: 100 !important;
  animation: floatContent 4s ease-in-out infinite;
  color: #ffffff !important;
  display: block !important;
  visibility: visible !important;
  opacity: 1 !important;
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
  color: #ffffff;
  background: rgba(255, 255, 255, 0.2);
  width: 50px;
  height: 50px;
  border-radius: 50%;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  opacity: 0.8;
  transition: all 0.3s ease;
}

.swiper-button-next:hover,
.swiper-button-prev:hover {
  background: rgba(255, 255, 255, 0.3);
  opacity: 1;
  transform: scale(1.1);
}

.swiper-button-next:after,
.swiper-button-prev:after {
  font-size: 18px;
  font-weight: bold;
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
  color: #ffffff;
  font-size: 14px;
}

.trust-item span {
  color: #ffffff !important;
}

.cert-logo {
  height: 50px;
}

.trust-item i {
  font-size: 20px;
  color: #B9F8B1;
}

/* Scroll Indicator Styling */
.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: #ffffff;
  z-index: 10;
  animation: bounce 2s infinite;
}

.scroll-link {
  color: inherit;
  text-decoration: none;
  display: block;
}

.scroll-link:hover {
  color: #B9F8B1;
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
  background: #ffffff;
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

/* Hero Stats Styling */
.hero-stats {
  display: flex;
  justify-content: center;
  gap: 40px;
  margin-top: 30px;
  flex-wrap: wrap;
}

.stat-item {
  text-align: center;
  color: #ffffff;
}

.stat-number {
  display: block;
  font-size: 2.5rem;
  font-weight: bold;
  color: #B9F8B1;
  margin-bottom: 5px;
}

.stat-label {
  display: block;
  font-size: 0.9rem;
  color: #ffffff;
  opacity: 0.9;
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
  color: #ffffff;
  font-size: 14px;
  opacity: 0.9;
}

.feature-item i {
  font-size: 18px;
  color: #B9F8B1;
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 24px;
  color: #ffffff;
}

.hero span {
  color: #B9F8B1;
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
  margin-top: 30px;
  z-index: 101;
  position: relative;
}

.hero-buttons .btn {
  padding: 16px 32px;
  font-size: 16px;
  font-weight: 600;
  border-radius: 8px;
  text-decoration: none;
  min-width: 180px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.btn-primary {
  background: #B9F8B1;
  color: #00252c;
  border-color: #B9F8B1;
}

.btn-primary:hover {
  background: #a8e7a0;
  border-color: #a8e7a0;
  transform: translateY(-2px);
}

.btn-outline {
  background: transparent;
  color: #ffffff;
  border-color: #ffffff;
}

.btn-outline:hover {
  background: #ffffff;
  color: #00252c;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  /* Mobile Hero Adjustments */
  .hero {
    height: 100vh;
    min-height: calc(100vh - 100px); /* Account for mobile navbar */
    padding-top: 100px; /* Space for mobile fixed navbar */
  }
  
  .swiper-slide {
    padding: 60px 15px 40px 15px;
    min-height: calc(100vh - 100px);
    height: calc(100vh - 100px);
  }
  
  /* Mobile-optimized background positioning */
  .hero-slide:nth-child(1),
  .hero-slide:nth-child(2), 
  .hero-slide:nth-child(3) {
    background-position: center center;
    background-attachment: scroll;
    /* Ensure background covers properly on mobile */
    background-size: cover;
  }
  
  .hero-content {
    max-width: 100%;
    padding: 0 10px;
    text-align: center;
    /* Reduce animation on mobile for better performance */
    animation: none;
  }
  
  .hero h1 {
    font-size: 2.2rem;
    line-height: 1.2;
    margin-bottom: 16px;
  }
  
  .hero p {
    font-size: 1.1rem;
    margin-bottom: 30px;
    padding: 10px 15px;
    line-height: 1.5;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
    gap: 15px;
    margin-top: 25px;
  }
  
  .hero-buttons .btn {
    padding: 14px 28px;
    font-size: 15px;
    min-width: 200px;
    width: 100%;
    max-width: 280px;
  }
  
  /* Mobile Trust Indicators */
  .trust-indicators {
    gap: 15px;
    margin-top: 30px;
    justify-content: center;
    flex-wrap: wrap;
    padding: 0 10px;
  }
  
  .trust-item {
    font-size: 12px;
    flex-direction: column;
    text-align: center;
    gap: 8px;
    background: rgba(255, 255, 255, 0.1);
    padding: 12px 8px;
    border-radius: 8px;
    backdrop-filter: blur(10px);
    min-width: 90px;
  }
  
  .cert-logo {
    height: 40px;
    filter: brightness(1.1);
  }
  
  /* Mobile Stats */
  .hero-stats {
    gap: 25px;
    margin-top: 25px;
    justify-content: center;
  }
  
  .stat-number {
    font-size: 2rem;
  }
  
  .stat-label {
    font-size: 0.8rem;
  }
  
  /* Mobile Features */
  .hero-features {
    gap: 20px;
    margin-top: 25px;
    justify-content: center;
    flex-wrap: wrap;
  }
  
  .feature-item {
    font-size: 13px;
    flex-direction: column;
    text-align: center;
    gap: 5px;
  }
  
  .feature-item i {
    font-size: 16px;
  }
  
  /* Mobile Navigation */
  .swiper-button-next,
  .swiper-button-prev {
    width: 40px;
    height: 40px;
    margin-top: -20px;
  }
  
  .swiper-button-next:after,
  .swiper-button-prev:after {
    font-size: 14px;
  }
  
  .swiper-button-next {
    right: 10px;
  }
  
  .swiper-button-prev {
    left: 10px;
  }
  
  /* Mobile Scroll Indicator */
  .scroll-indicator {
    bottom: 20px;
  }
  
  .scroll-indicator span {
    font-size: 11px;
  }
  
  .scroll-mouse {
    width: 20px;
    height: 30px;
  }
  
  .scroll-wheel {
    height: 4px;
    top: 4px;
  }
}

@media (max-width: 480px) {
  /* Extra small mobile adjustments */
  .hero {
    padding-top: 84px; /* Space for smallest mobile navbar */
    min-height: calc(100vh - 84px);
  }
  
  .swiper-slide {
    height: calc(100vh - 84px);
    min-height: calc(100vh - 84px);
    padding: 50px 15px 30px 15px;
  }
  
  .hero h1 {
    font-size: 1.9rem;
    line-height: 1.3;
    margin-bottom: 20px;
  }
  
  .hero p {
    font-size: 1.1rem;
    padding: 10px 15px;
    line-height: 1.5;
    margin-bottom: 25px;
  }
  
  .hero-buttons {
    margin-bottom: 20px;
  }
  
  .hero-buttons .btn {
    padding: 14px 28px;
    font-size: 15px;
    min-width: 200px;
    margin: 5px;
  }
  
  .swiper-slide {
    padding: 30px 10px;
  }
  
  /* Hide some elements on very small screens */
  .trust-indicators {
    margin-top: 25px;
    gap: 12px;
  }
  
  .trust-item {
    background: rgba(255, 255, 255, 0.15);
    padding: 10px 6px;
    border-radius: 6px;
    min-width: 85px;
    font-size: 11px;
  }
  
  .cert-logo {
    height: 35px;
  }
  
  .hero-stats {
    gap: 15px;
  }
  
  .stat-number {
    font-size: 1.8rem;
  }
  
  /* Smaller navigation buttons */
  .swiper-button-next,
  .swiper-button-prev {
    width: 35px;
    height: 35px;
    margin-top: -17px;
  }
  
  .swiper-button-next:after,
  .swiper-button-prev:after {
    font-size: 12px;
  }
  
  /* Hide decorative elements on very small screens for better performance */
  .hero::before {
    display: none;
  }
}
</style>
