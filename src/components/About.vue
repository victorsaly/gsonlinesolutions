<template>
  <section id="about" class="section section-alt">
    <div class="container">
      <div class="about-content">
        <div class="section-header">
          <h2 class="fade-in-up">Why Choose GS Online Solutions?</h2>
          <p class="subtitle fade-in-up-delay">
            Founded by Gosia Saly in 2024, GS Online Solutions brings fresh energy 
            and modern expertise to business finance management. We believe in building 
            long-term partnerships with our clients through dedicated service and innovative solutions.
          </p>
        </div>
        
        <div class="benefits-grid">
          <div class="benefit-card card card-elevated slide-in-up" v-for="benefit in benefits" :key="benefit.id">
            <div class="benefit-icon" v-html="benefit.icon"></div>
            <h4 class="mb-4">{{ benefit.title }}</h4>
            <p>{{ benefit.description }}</p>
          </div>
        </div>
      </div>
      
      <div class="team-approach">
        <div class="approach-content">
          <div class="approach-text slide-in-left">
            <h3>Meet Your Dedicated Finance Partner</h3>
            <p>
              Founded by Gosia Saly, GS Online Solutions represents a fresh approach to 
              business finance management. As a growing practice, we combine personal attention 
              with modern expertise, ensuring every client receives the dedicated service they deserve. 
              Our goal is to grow alongside your business, providing scalable solutions that evolve with your needs.
            </p>
            
            <div class="approach-features">
              <div class="feature-row">
                <div class="feature-icon">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="feature-content">
                  <h5>Personal Service</h5>
                  <p>Direct access to founder Gosia Saly for all your financial needs</p>
                </div>
              </div>
              
              <div class="feature-row">
                <div class="feature-icon">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="feature-content">
                  <h5>Growing with You</h5>
                  <p>Scalable solutions that adapt as your business expands</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="approach-visual slide-in-right">
            <div class="founder-profile">
              <div class="founder-image">
                <img src="/gsonlinesolutions/GosiaProfile.jpg" alt="Gosia Saly - Founder of GS Online Solutions" class="profile-photo" />
                <div class="founder-badge">
                  <span>Founder & Financial Expert</span>
                </div>
              </div>
              <div class="founder-info">
                <h4>Gosia Saly</h4>
                <p class="founder-title">Founder & Financial Expert</p>
                <p class="founder-description">
                  With years of experience in financial management and a passion for helping businesses grow, 
                  Gosia founded GS Online Solutions to provide personalized, expert financial services.
                </p>
                <div class="founder-credentials">
                  <div class="credential">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="var(--primary)">
                      <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                    </svg>
                    <span>Qualified Accountant</span>
                  </div>
                  <div class="credential">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="var(--primary)">
                      <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                    </svg>
                    <span>1+ Years Business Experience</span>
                  </div>
                </div>
                
                <!-- Professional Certifications -->
                <div class="certifications-section slide-in-left">
                  <h5 class="text-gradient mb-6">Professional Certifications</h5>
                  <div class="certifications-grid">
                    <div class="certification-badge card card-minimal">
                      <img src="/gsonlinesolutions/xero-logo.png" alt="Xero Advisor Certified" class="cert-logo" />
                      <div class="cert-info">
                        <h6>Xero Advisor Certified</h6>
                        <p>Cloud accounting expertise</p>
                      </div>
                    </div>
                    <div class="certification-badge card card-minimal">
                      <img src="/gsonlinesolutions/icb_logo.png" alt="ICB Member" class="cert-logo" />
                      <div class="cert-info">
                        <h6>ICB Member</h6>
                        <p>Institute of Certified Bookkeepers</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onUnmounted } from 'vue'

const benefits = [
  {
    id: 1,
    title: 'Personal Founder-Led Service',
    description: 'Work directly with Gosia Saly, ensuring personalized attention and consistent quality in every interaction.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4M12.5,7V12.25L17,14.92L16.25,16.15L11,13V7H12.5Z"/>
    </svg>`
  },
  {
    id: 2,
    title: 'Modern Financial Solutions',
    description: 'Fresh approaches to traditional accounting challenges, leveraging the latest tools and technologies.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M19,3H5C3.89,3 3,3.89 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V5C21,3.89 20.1,3 19,3M19,5V19H5V5H19Z"/>
    </svg>`
  },
  {
    id: 3,
    title: 'Partnership Approach',
    description: 'We grow alongside your business, adapting our services to meet your evolving financial needs.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M16,4C18.21,4 20,5.79 20,8C20,10.21 18.21,12 16,12C13.79,12 12,10.21 12,8C12,5.79 13.79,4 16,4M16,14C18.67,14 24,15.34 24,18V20H8V18C8,15.34 13.33,14 16,14M8,4C10.21,4 12,5.79 12,8C12,10.21 10.21,12 8,12C5.79,12 4,10.21 4,8C4,5.79 5.79,4 8,4M8,14C10.67,14 16,15.34 16,18V20H0V18C0,15.34 5.33,14 8,14Z"/>
    </svg>`
  },
  {
    id: 4,
    title: 'Transparent Communication',
    description: 'Clear, jargon-free explanations of your financial position and recommendations for improvement.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M11,16.5L18,9.5L16.59,8.09L11,13.67L7.91,10.59L6.5,12L11,16.5Z"/>
    </svg>`
  },
  {
    id: 5,
    title: 'Xero & ICB Certified',
    description: 'Fully qualified with Xero certification and ICB membership, ensuring professional standards and expertise.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,1L3,5V11C3,16.55 6.84,21.74 12,23C17.16,21.74 21,16.55 21,11V5L12,1M10,17L6,13L7.41,11.59L10,14.17L16.59,7.58L18,9L10,17Z"/>
    </svg>`
  },
  {
    id: 6,
    title: 'Flexible & Scalable',
    description: 'Tailored solutions that grow with your business, from startups to established companies.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M13,9H18.5L13,3.5V9M6,2H14L20,8V20A2,2 0 0,1 18,22H6C4.89,22 4,21.1 4,20V4C4,2.89 4.89,2 6,2M11,4H6V20H11L18,13V20H6V4Z"/>
    </svg>`
  }
]

// Intersection Observer for scroll animations
let observer = null

const initializeScrollAnimations = () => {
  const options = {
    root: null,
    rootMargin: '0px 0px -100px 0px',
    threshold: 0.1
  }

  observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in')
      }
    })
  }, options)

  // Observe elements with animation classes
  const animationElements = document.querySelectorAll('.slide-in-left, .slide-in-right, .slide-in-up, .fade-in-up, .fade-in-up-delay, .fade-in-up-delay-2')
  animationElements.forEach(el => observer.observe(el))
}

onMounted(() => {
  // Add a small delay to ensure DOM is fully rendered
  setTimeout(initializeScrollAnimations, 100)
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<style scoped>
.section {
  padding: 5rem 0;
  background: var(--white);
}

.section-alt {
  background: var(--gray-50);
}

.about-content {
  margin-bottom: 5rem;
}

.about-text {
  text-align: center;
  margin-bottom: 3rem;
}

.about-text h2 {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
  color: var(--primary);
  font-weight: 300;
}

.text-large {
  font-size: 1.25rem;
  line-height: 1.7;
  color: var(--gray-600);
  max-width: 800px;
  margin: 0 auto;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.benefit-card {
  background: var(--white);
  padding: 2rem;
  border-radius: 1rem;
  text-align: center;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  border: 1px solid var(--gray-100);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px -3px rgba(0, 0, 0, 0.1);
}

.benefit-icon {
  margin-bottom: 1.5rem;
}

.benefit-card h4 {
  font-size: 1.25rem;
  margin-bottom: 1rem;
  color: var(--primary);
  font-weight: 500;
}

.benefit-card p {
  color: var(--gray-600);
  line-height: 1.6;
}

/* Team Approach Styles */
.team-approach {
  padding: 3rem 0;
}

.approach-content {
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 3rem;
  align-items: top;
}

.approach-text h3 {
  font-size: 2rem;
  color: var(--primary);
  margin-bottom: 1.5rem;
  font-weight: 300;
}

.approach-text > p {
  font-size: 1.125rem;
  color: var(--gray-600);
  line-height: 1.7;
  margin-bottom: 2rem;
}

.approach-features {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.feature-row {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.feature-icon {
  flex-shrink: 0;
  width: 48px;
  height: 48px;
  background: rgba(82, 115, 108, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.feature-content h5 {
  font-size: 1.125rem;
  color: var(--primary);
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.feature-content p {
  color: var(--gray-600);
  margin: 0;
  font-size: 0.95rem;
}

/* Founder Profile Styles */
.founder-profile {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 1.5rem;
  max-width: 400px;
  margin: 0 auto;
}

.founder-image {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.profile-photo {
  width: 280px;
  height: 280px;
  border-radius: 1rem;
  object-fit: cover;
  border: 3px solid var(--primary);
  box-shadow: 0 12px 40px rgba(82, 115, 108, 0.25);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.profile-photo:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 50px rgba(82, 115, 108, 0.35);
}

.founder-badge {
  margin-top: 1rem;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
  box-shadow: 0 4px 12px rgba(82, 115, 108, 0.3);
}

.founder-info h4 {
  font-size: 1.5rem;
  color: var(--primary);
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.founder-title {
  font-size: 1.125rem;
  color: var(--secondary);
  margin-bottom: 1rem;
  font-weight: 500;
}

.founder-description {
  color: var(--gray-600);
  line-height: 1.6;
  margin-bottom: 1.5rem;
  max-width: 400px;
}

.founder-credentials {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  align-items: center;
}

.credential {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--gray-700);
  font-size: 0.95rem;
  font-weight: 500;
}

.credential svg {
  flex-shrink: 0;
}

/* Professional Certifications */
.certifications-section {
  margin-top: 2rem;
}

.certifications-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

.certification-badge {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem !important;
}

.cert-logo {
  width: 80px;
  height: 40px;
  object-fit: contain;
  flex-shrink: 0;
}

.cert-info h6 {
  color: var(--primary);
  font-size: 0.95rem;
  font-weight: 600;
  margin: 0 0 0.25rem 0;
}

.cert-info p {
  color: var(--gray-600);
  font-size: 0.85rem;
  margin: 0;
  line-height: 1.4;
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

/* Staggered animation for benefit cards */
.benefit-card {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.benefit-card:nth-child(1) { transition-delay: 0.1s; }
.benefit-card:nth-child(2) { transition-delay: 0.2s; }
.benefit-card:nth-child(3) { transition-delay: 0.3s; }
.benefit-card:nth-child(4) { transition-delay: 0.4s; }

.benefit-card.animate-in {
  opacity: 1;
  transform: translateY(0);
}

/* Mobile Responsive Styles */
@media (max-width: 768px) {
  .section {
    padding: 3rem 0;
  }
  
  .about-text h2 {
    font-size: 2rem;
  }
  
  .benefits-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .approach-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: top;
  }
  
  .approach-text h3 {
    font-size: 1.75rem;
  }
  
  .founder-profile {
    margin-top: 2rem;
  }
  
  .profile-photo {
    width: 220px;
    height: 220px;
  }
  
  .founder-info h4 {
    font-size: 1.25rem;
  }
  
  .founder-credentials {
    gap: 0.5rem;
  }
}

@media (max-width: 480px) {
  .about-text h2 {
    font-size: 1.75rem;
  }
  
  .benefit-card {
    padding: 1.5rem;
  }
  
  .approach-text h3 {
    font-size: 1.5rem;
  }
  
  .profile-photo {
    width: 180px;
    height: 180px;
  }
  
  .founder-badge {
    padding: 0.5rem 1rem;
    font-size: 0.8rem;
  }
  
  .founder-info h4 {
    font-size: 1.125rem;
  }
}
</style>