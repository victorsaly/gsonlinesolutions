<template>
  <section class="hero">
    <div class="hero-background">
      <div class="hero-gradient"></div>
    </div>
    
    <div class="container">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title fade-in-up">
            Outsource Your Finance Function 
            <span class="highlight">with Confidence</span>
          </h1>
          
          <p class="hero-description fade-in-up-delay">
            Tailored bookkeeping and financial controller services designed to 
            support businesses of all sizes. Let our expert team handle your 
            finances while you focus on growing your business.
          </p>
          
          <div class="hero-actions fade-in-up-delay-2">
            <a href="#services" class="btn btn-primary btn-large">
              Explore Our Services
            </a>
            <a href="#contact" class="btn btn-secondary btn-large">
              Book a Consultation
            </a>
          </div>
          
          <div class="hero-features fade-in-up-delay-2">
            <div class="feature-item">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="var(--primary)">
                <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
              </svg>
              <span>Fixed Monthly Fees</span>
            </div>
            <div class="feature-item">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="var(--primary)">
                <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
              </svg>
              <span>Expert Team</span>
            </div>
            <div class="feature-item">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="var(--primary)">
                <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
              </svg>
              <span>Scalable Solutions</span>
            </div>
          </div>
        </div>
        
        <div class="hero-visual fade-in-up">
          <div class="hero-card">
            <div class="card-header">
              <h3>Your Business Growth Partner</h3>
            </div>
            <div class="card-content">
              <div class="metric">
                <div class="metric-value">15+</div>
                <div class="metric-label">Years Experience</div>
              </div>
              <div class="metric">
                <div class="metric-value">200+</div>
                <div class="metric-label">Happy Clients</div>
              </div>
              <div class="metric">
                <div class="metric-value">99%</div>
                <div class="metric-label">Satisfaction Rate</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <div class="hero-scroll-indicator">
      <div class="scroll-arrow"></div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
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
    rgba(82, 115, 108, 0.05) 0%, 
    rgba(135, 115, 94, 0.05) 50%, 
    transparent 100%
  );
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
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
  bottom: 2rem;
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
</style>