<template>
  <section id="about" class="section section-alt">
    <div class="container">
      <div class="about-content">
        <div class="about-text">
          <h2 class="fade-in-up">Why Partner with Us?</h2>
          <p class="text-large fade-in-up-delay">
            We do care – if you succeed, we succeed. Our success is directly tied to helping 
            your business grow and prosper.
          </p>
        </div>
        
        <div class="benefits-grid fade-in-up-delay-2">
          <div class="benefit-card" v-for="benefit in benefits" :key="benefit.id">
            <div class="benefit-icon" v-html="benefit.icon"></div>
            <h4>{{ benefit.title }}</h4>
            <p>{{ benefit.description }}</p>
          </div>
        </div>
      </div>
      
      <div class="team-approach">
        <div class="approach-content">
          <div class="approach-text">
            <h3>Your Trusted Finance Business Partner</h3>
            <p>
              We work as your extended team, combining local expertise with specialized 
              outsourced professionals to provide comprehensive coverage across all areas 
              of finance and accounting. This approach allows us to offer enterprise-level 
              service while maintaining cost-effectiveness for businesses of all sizes.
            </p>
            
            <div class="approach-features">
              <div class="feature-row">
                <div class="feature-icon">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="feature-content">
                  <h5>Expert Team Network</h5>
                  <p>Access to specialists across all areas of accounting and finance</p>
                </div>
              </div>
              
              <div class="feature-row">
                <div class="feature-icon">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="feature-content">
                  <h5>Scalable Solutions</h5>
                  <p>Services that grow with your business needs</p>
                </div>
              </div>
              
              <div class="feature-row">
                <div class="feature-icon">
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="feature-content">
                  <h5>Proactive Approach</h5>
                  <p>Strategic guidance to help you plan ahead and succeed</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="approach-visual">
            <div class="team-diagram">
              <div class="central-hub">
                <div class="hub-content">
                  <h4>GS Online Services</h4>
                  <p>Your Finance Team</p>
                </div>
              </div>
              
              <div class="team-member specialist-1">
                <div class="member-badge">Tax Specialist</div>
              </div>
              
              <div class="team-member specialist-2">
                <div class="member-badge">Bookkeeper</div>
              </div>
              
              <div class="team-member specialist-3">
                <div class="member-badge">Controller</div>
              </div>
              
              <div class="team-member specialist-4">
                <div class="member-badge">Payroll Expert</div>
              </div>
              
              <div class="connection-lines">
                <div class="line line-1"></div>
                <div class="line line-2"></div>
                <div class="line line-3"></div>
                <div class="line line-4"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const benefits = [
  {
    id: 1,
    title: '15+ Years Experience',
    description: 'Extensive background in audit and accounting, with hands-on experience working with startups and growing businesses.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4M12.5,7V12.25L17,14.92L16.25,16.15L11,13V7H12.5Z"/>
    </svg>`
  },
  {
    id: 2,
    title: 'Flexible Contracts',
    description: 'Monthly rolling contract giving you the freedom of a flexible arrangement that adapts to your changing needs.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M17,12C17,14.42 15.28,16.44 13,16.9V21H11V16.9C8.72,16.44 7,14.42 7,12C7,9.58 8.72,7.56 11,7.1V3H13V7.1C15.28,7.56 17,9.58 17,12M12,9A3,3 0 0,0 9,12A3,3 0 0,0 12,15A3,3 0 0,0 15,12A3,3 0 0,0 12,9Z"/>
    </svg>`
  },
  {
    id: 3,
    title: 'Fixed Monthly Fees',
    description: 'Predictable costs allowing better cashflow management and budget planning for your business.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M7,15H9C9,16.08 10.37,17 12,17C13.63,17 15,16.08 15,15C15,13.9 13.96,13.5 11.76,12.97C9.64,12.44 7,11.78 7,9C7,7.21 8.47,5.69 10.5,5.18V3H13.5V5.18C15.53,5.69 17,7.21 17,9H15C15,7.92 13.63,7 12,7C10.37,7 9,7.92 9,9C9,10.1 10.04,10.5 12.24,11.03C14.36,11.56 17,12.22 17,15C17,16.79 15.53,18.31 13.5,18.82V21H10.5V18.82C8.47,18.31 7,16.79 7,15Z"/>
    </svg>`
  },
  {
    id: 4,
    title: 'Ongoing Support',
    description: 'Continuous support keeping your finances on track with regular reviews and proactive advice.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M18.72,14.76C19.07,13.91 19.26,13 19.26,12C19.26,11.28 19.15,10.59 18.96,9.95C18.31,10.1 17.63,10.18 16.92,10.18C13.86,10.18 11.15,8.67 9.5,6.34C8.61,8.5 6.91,10.26 4.77,11.22C4.73,11.47 4.73,11.74 4.73,12A7.27,7.27 0 0,0 12,19.27C13.05,19.27 14.06,19.04 14.97,18.63C15.54,19.72 15.8,20.26 15.78,20.26C14.14,20.81 12.87,21.08 12,21.08C9.58,21.08 7.27,20.13 5.78,18.4C4.28,16.67 3.3,14.42 3.26,12C3.26,9.58 4.28,7.27 5.78,5.78C7.27,4.3 9.58,3.26 12,3.26C14.42,3.26 16.73,4.28 18.22,5.78C19.7,7.27 20.74,9.58 20.74,12C20.71,12.64 20.63,13.27 20.49,13.88C20.1,14.15 19.4,14.59 18.72,14.76M7.75,10.3L9,8.5L12,17L17,8.5L18.25,10.3L12,21.5L7.75,10.3Z"/>
    </svg>`
  },
  {
    id: 5,
    title: 'Multilingual Service',
    description: 'English, Portuguese, Spanish and Italian language support for international expansion.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M12.87,15.07L10.33,12.56L10.36,12.53C12.1,10.59 13.34,8.36 14.07,6H17V4H10V2H8V4H1V6H12.17C11.5,7.92 10.44,9.75 9,11.35C8.07,10.32 7.3,9.19 6.69,8H4.69C5.42,9.63 6.42,11.17 7.67,12.56L2.58,17.58L4,19L9,14L12.11,17.11L12.87,15.07M18.5,10H16.5L12,22H14L15.12,19H19.87L21,22H23L18.5,10M15.88,17L17.5,12.67L19.12,17H15.88Z"/>
    </svg>`
  },
  {
    id: 6,
    title: 'Technology-Driven',
    description: 'Modern cloud-based systems and processes to ensure efficiency and real-time visibility.',
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="var(--primary)">
      <path d="M4,6H20V16H4M20,18A2,2 0 0,0 22,16V6C22,4.89 21.1,4 20,4H4C2.89,4 2,4.89 2,6V16A2,2 0 0,0 4,18H0V20H24V18H20Z"/>
    </svg>`
  }
]
</script>

<style scoped>
.section {
  padding: 5rem 0;
}

.about-text {
  text-align: center;
  margin-bottom: 4rem;
}

.about-text h2 {
  font-size: 2.5rem;
  color: var(--primary);
  margin-bottom: 1.5rem;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 5rem;
}

.benefit-card {
  background: var(--white);
  padding: 2rem;
  border-radius: 1rem;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  border: 1px solid var(--gray-100);
  transition: all 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1),
              0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

.benefit-icon {
  margin-bottom: 1.5rem;
}

.benefit-card h4 {
  font-size: 1.25rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.benefit-card p {
  color: var(--gray-600);
  line-height: 1.6;
}

.team-approach {
  background: var(--white);
  padding: 4rem 2rem;
  border-radius: 1.5rem;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
              0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.approach-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.approach-text h3 {
  font-size: 2rem;
  color: var(--primary);
  margin-bottom: 1.5rem;
}

.approach-text p {
  font-size: 1.125rem;
  line-height: 1.7;
  color: var(--gray-600);
  margin-bottom: 2rem;
}

.approach-features {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.feature-row {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
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
}

.feature-content p {
  color: var(--gray-600);
  margin: 0;
  font-size: 0.95rem;
}

.team-diagram {
  position: relative;
  width: 100%;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.central-hub {
  position: absolute;
  width: 160px;
  height: 160px;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-align: center;
  z-index: 2;
}

.hub-content h4 {
  font-size: 1rem;
  margin: 0 0 0.25rem 0;
  color: white;
}

.hub-content p {
  font-size: 0.875rem;
  margin: 0;
  color: rgba(255, 255, 255, 0.9);
}

.team-member {
  position: absolute;
  width: 100px;
  height: 60px;
  background: var(--white);
  border: 2px solid var(--primary);
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2;
}

.member-badge {
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--primary);
  text-align: center;
}

.specialist-1 { top: 50px; left: 50%; transform: translateX(-50%); }
.specialist-2 { top: 50%; right: 20px; transform: translateY(-50%); }
.specialist-3 { bottom: 50px; left: 50%; transform: translateX(-50%); }
.specialist-4 { top: 50%; left: 20px; transform: translateY(-50%); }

.connection-lines {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.line {
  position: absolute;
  background: var(--primary);
  opacity: 0.3;
}

.line-1 {
  width: 2px;
  height: 60px;
  top: 110px;
  left: 50%;
  transform: translateX(-50%);
}

.line-2 {
  width: 60px;
  height: 2px;
  top: 50%;
  right: 80px;
  transform: translateY(-50%);
}

.line-3 {
  width: 2px;
  height: 60px;
  bottom: 110px;
  left: 50%;
  transform: translateX(-50%);
}

.line-4 {
  width: 60px;
  height: 2px;
  top: 50%;
  left: 80px;
  transform: translateY(-50%);
}

@media (max-width: 768px) {
  .benefits-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .benefit-card {
    padding: 1.5rem;
  }
  
  .about-text h2 {
    font-size: 2rem;
  }
  
  .team-approach {
    padding: 2rem 1rem;
  }
  
  .approach-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .approach-text h3 {
    font-size: 1.5rem;
  }
  
  .team-diagram {
    height: 300px;
  }
  
  .central-hub {
    width: 120px;
    height: 120px;
  }
  
  .team-member {
    width: 80px;
    height: 50px;
    border-radius: 25px;
  }
  
  .member-badge {
    font-size: 0.7rem;
  }
  
  .specialist-1 { top: 30px; }
  .specialist-2 { right: 10px; }
  .specialist-3 { bottom: 30px; }
  .specialist-4 { left: 10px; }
  
  .line-1, .line-3 { height: 50px; }
  .line-2, .line-4 { width: 50px; }
  .line-2 { right: 60px; }
  .line-4 { left: 60px; }
  .line-1 { top: 90px; }
  .line-3 { bottom: 90px; }
}
</style>