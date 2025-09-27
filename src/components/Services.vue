<template>
  <section id="services" class="section">
    <div class="container">
      <div class="section-header">
        <h2 class="fade-in-up">Our Services</h2>
        <p class="subtitle fade-in-up-delay">
          Comprehensive finance and accounting services tailored to your business needs
        </p>
      </div>
      
      <div class="services-intro fade-in-up-delay-2">
        <div class="card card-gradient">
          <div class="intro-content text-center">
            <h3 class="text-gradient">Tailored solutions that grow with your business</h3>
            <p class="text-large">
              At GS Online Solutions, we understand that every business is unique. Founded with 
              a commitment to personalized service, we work closely with each client to understand 
              your specific needs and deliver solutions that drive growth and financial clarity.
            </p>
          </div>
        </div>
      </div>
      
      <div class="services-grid">
        <div class="service-card card card-elevated slide-in-up" v-for="service in services" :key="service.id">
          <div class="service-icon" v-html="service.icon"></div>
          <h4 class="mb-4">{{ service.title }}</h4>
          <p class="mb-6">{{ service.description }}</p>
          <ul class="service-features" v-if="service.features">
            <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
          </ul>
        </div>
      </div>
      
      <div class="services-cta text-center slide-in-up">
        <h3>Ready to streamline your finances?</h3>
        <p>Get in touch to discuss how we can support your business growth</p>
        <div class="cta-buttons">
          <a href="#contact" class="btn btn-primary btn-large">Get Started</a>
          <a href="/extended-services" class="btn btn-secondary btn-large">Explore Extended Services</a>
        </div>
        <p class="cta-note">From bookkeeping to wealth management - we have expert partners for every need</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onUnmounted } from 'vue'

const services = [
  {
    id: 1,
    title: 'Fractional Financial Controller',
    description: 'Strategic financial leadership and oversight for growing businesses without the full-time cost.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </svg>`,
    features: [
      'Financial planning & analysis',
      'Management reporting',
      'Cash flow management',
      'Budget planning & forecasting'
    ]
  },
  {
    id: 2,
    title: 'Bookkeeping Services',
    description: 'Complete bookkeeping solutions to keep your financial records accurate and up-to-date.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M14,2H6A2,2 0 0,0 4,4V20A2,2 0 0,0 6,22H18A2,2 0 0,0 20,20V8L14,2M18,20H6V4H13V9H18V20Z"/>
    </svg>`,
    features: [
      'Daily transaction processing',
      'Bank reconciliation',
      'Accounts payable & receivable',
      'Monthly financial statements'
    ]
  },
  {
    id: 3,
    title: 'Tax Preparation & Planning',
    description: 'Expert tax services to minimize your liability and ensure compliance with all regulations.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M14,2H6A2,2 0 0,0 4,4V20A2,2 0 0,0 6,22H18A2,2 0 0,0 20,20V8L14,2M18,20H6V4H13V9H18V20Z"/>
    </svg>`,
    features: [
      'Corporation tax returns',
      'Personal tax returns',
      'VAT returns & planning',
      'Tax planning strategies'
    ]
  },
  {
    id: 4,
    title: 'Payroll Services',
    description: 'Complete payroll management ensuring accurate and timely payments to your employees.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M7.07,18.28C7.5,17.38 10.12,16.5 12,16.5C13.88,16.5 16.5,17.38 16.93,18.28C15.57,19.36 13.86,20 12,20C10.14,20 8.43,19.36 7.07,18.28M18.36,16.83C16.93,15.09 13.46,14.5 12,14.5C10.54,14.5 7.07,15.09 5.64,16.83C4.62,15.5 4,13.82 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,13.82 19.38,15.5 18.36,16.83M12,6C10.06,6 8.5,7.56 8.5,9.5C8.5,11.44 10.06,13 12,13C13.94,13 15.5,11.44 15.5,9.5C15.5,7.56 13.94,6 12,6M12,11A1.5,1.5 0 0,1 10.5,9.5A1.5,1.5 0 0,1 12,8A1.5,1.5 0 0,1 13.5,9.5A1.5,1.5 0 0,1 12,11Z"/>
    </svg>`,
    features: [
      'Monthly payroll processing',
      'PAYE & NI calculations',
      'Pension auto-enrolment',
      'Employee reporting'
    ]
  },
  {
    id: 5,
    title: 'Management Reporting',
    description: 'Clear, actionable financial reports to help you make informed business decisions.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M22,21H2V3H4V19H6V10H10V19H12V6H16V19H18V14H22V21Z"/>
    </svg>`,
    features: [
      'Monthly management accounts',
      'KPI dashboards',
      'Performance analysis',
      'Custom reporting'
    ]
  },
  {
    id: 6,
    title: 'Systems & Process Improvement',
    description: 'Optimize your financial processes and systems for better efficiency and accuracy.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,8A4,4 0 0,1 16,12A4,4 0 0,1 12,16A4,4 0 0,1 8,12A4,4 0 0,1 12,8M12,10A2,2 0 0,0 10,12A2,2 0 0,0 12,14A2,2 0 0,0 14,12A2,2 0 0,0 12,10M10,22C9.75,22 9.54,21.82 9.5,21.58L9.13,18.93C8.5,18.68 7.96,18.34 7.44,17.94L4.95,18.95C4.73,19.03 4.46,18.95 4.34,18.73L2.34,15.27C2.21,15.05 2.27,14.78 2.46,14.63L4.57,12.97L4.5,12L4.57,11L2.46,9.37C2.27,9.22 2.21,8.95 2.34,8.73L4.34,5.27C4.46,5.05 4.73,4.96 4.95,5.05L7.44,6.05C7.96,5.66 8.5,5.32 9.13,5.07L9.5,2.42C9.54,2.18 9.75,2 10,2H14C14.25,2 14.46,2.18 14.5,2.42L14.87,5.07C15.5,5.32 16.04,5.66 16.56,6.05L19.05,5.05C19.27,4.96 19.54,5.05 19.66,5.27L21.66,8.73C21.79,8.95 21.73,9.22 21.54,9.37L19.43,11L19.5,12L19.43,13L21.54,14.63C21.73,14.78 21.79,15.05 21.66,15.27L19.66,18.73C19.54,18.95 19.27,19.04 19.05,18.95L16.56,17.95C16.04,18.34 15.5,18.68 14.87,18.93L14.5,21.58C14.46,21.82 14.25,22 14,22H10M11.25,4L10.88,6.61C9.68,6.86 8.62,7.5 7.85,8.39L5.44,7.35L4.69,8.65L6.8,10.2C6.4,11.37 6.4,12.64 6.8,13.8L4.68,15.36L5.43,16.66L7.86,15.62C8.63,16.5 9.68,17.14 10.87,17.38L11.24,20H12.76L13.13,17.39C14.32,17.14 15.37,16.5 16.14,15.62L18.57,16.66L19.32,15.36L17.2,13.81C17.6,12.64 17.6,11.37 17.2,10.2L19.31,8.65L18.56,7.35L16.15,8.39C15.38,7.5 14.32,6.86 13.12,6.62L12.75,4H11.25Z"/>
    </svg>`,
    features: [
      'Process documentation',
      'System implementation',
      'Workflow optimization',
      'Training & support'
    ]
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
}

.section-header {
  margin-bottom: 3rem;
}

.section-header h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.services-intro {
  max-width: 800px;
  margin: 0 auto 4rem;
  text-align: center;
}

.intro-content h3 {
  font-size: 1.75rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.intro-content p {
  font-size: 1.125rem;
  line-height: 1.7;
  color: var(--gray-600);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.service-card {
  background: var(--white);
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  border: 1px solid var(--gray-100);
  transition: all 0.3s ease;
  height: 100%;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1),
              0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

.service-icon {
  margin-bottom: 1.5rem;
}

.service-card h4 {
  font-size: 1.25rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.service-card p {
  color: var(--gray-600);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.service-features {
  list-style: none;
}

.service-features li {
  position: relative;
  padding-left: 1.5rem;
  margin-bottom: 0.5rem;
  color: var(--gray-600);
  font-size: 0.9rem;
}

.service-features li:before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--primary);
  font-weight: bold;
}

.services-cta {
  background: linear-gradient(135deg, var(--gray-50) 0%, var(--white) 100%);
  padding: 3rem 2rem;
  border-radius: 1rem;
  margin-top: 3rem;
}

.services-cta h3 {
  font-size: 1.75rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.services-cta p {
  font-size: 1.125rem;
  color: var(--gray-600);
  margin-bottom: 2rem;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 1.5rem;
}

.cta-note {
  font-size: 0.9rem;
  color: var(--gray-500);
  font-style: italic;
  margin: 0;
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .service-card {
    padding: 1.5rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .services-intro {
    margin-bottom: 3rem;
  }
  
  .intro-content h3 {
    font-size: 1.5rem;
  }
  
  .intro-content p {
    font-size: 1rem;
  }
  
  .services-cta {
    padding: 2rem 1.5rem;
  }
  
  .services-cta h3 {
    font-size: 1.5rem;
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

/* Staggered animation for service cards */
.service-card {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.service-card:nth-child(1) { transition-delay: 0.1s; }
.service-card:nth-child(2) { transition-delay: 0.2s; }
.service-card:nth-child(3) { transition-delay: 0.3s; }
.service-card:nth-child(4) { transition-delay: 0.4s; }
.service-card:nth-child(5) { transition-delay: 0.5s; }
.service-card:nth-child(6) { transition-delay: 0.6s; }

.service-card.animate-in {
  opacity: 1;
  transform: translateY(0);
}
</style>