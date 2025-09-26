<template>
  <section id="contact" class="section">
    <div class="container">
      <div class="contact-content">
        <div class="contact-info">
          <div class="info-header">
            <h2>Get in Touch</h2>
            <p class="text-large">
              Ready to experience the difference? Let's discuss how we can support 
              your business growth and financial success.
            </p>
          </div>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M20,4H4C2.89,4 2,4.89 2,6V18A2,2 0 0,0 4,20H20A2,2 0 0,0 22,18V6C22,4.89 21.1,4 20,4M20,8L12,13L4,8V6L12,11L20,6V8Z" />
                </svg>
              </div>
              <div class="method-content">
                <h4>Email</h4>
                <a href="mailto:info@gsonlineservices.co.uk">info@gsonlineservices.co.uk</a>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M6.62,10.79C8.06,13.62 10.38,15.94 13.21,17.38L15.41,15.18C15.69,14.9 16.08,14.82 16.43,14.93C17.55,15.3 18.75,15.5 20,15.5A1,1 0 0,1 21,16.5V20A1,1 0 0,1 20,21A17,17 0 0,1 3,4A1,1 0 0,1 4,3H7.5A1,1 0 0,1 8.5,4C8.5,5.25 8.7,6.45 9.07,7.57C9.18,7.92 9.1,8.31 8.82,8.59L6.62,10.79Z" />
                </svg>
              </div>
              <div class="method-content">
                <h4>Phone</h4>
                <a href="tel:+44123456789">+44 (0) 123 456 789</a>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4M12.5,7V12.25L17,14.92L16.25,16.15L11,13V7H12.5Z"/>
                </svg>
              </div>
              <div class="method-content">
                <h4>Business Hours</h4>
                <p>Monday - Friday: 9:00 AM - 6:00 PM</p>
                <p>Saturday: 10:00 AM - 2:00 PM</p>
              </div>
            </div>
          </div>
          
          <div class="cta-buttons">
            <a href="https://calendly.com/gsonlineservices" class="btn btn-primary btn-large" target="_blank" rel="noopener">
              Book a Free Consultation
            </a>
            <a href="#services" class="btn btn-secondary btn-large">
              View Our Services
            </a>
          </div>
        </div>
        
        <div class="contact-form-container">
          <form @submit.prevent="handleSubmit" class="contact-form">
            <h3>Send us a Message</h3>
            
            <div class="form-row">
              <div class="form-group">
                <label for="firstName">First Name *</label>
                <input 
                  type="text" 
                  id="firstName" 
                  v-model="form.firstName" 
                  required 
                  class="form-input"
                >
              </div>
              
              <div class="form-group">
                <label for="lastName">Last Name *</label>
                <input 
                  type="text" 
                  id="lastName" 
                  v-model="form.lastName" 
                  required 
                  class="form-input"
                >
              </div>
            </div>
            
            <div class="form-group">
              <label for="email">Email Address *</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email" 
                required 
                class="form-input"
              >
            </div>
            
            <div class="form-group">
              <label for="company">Company Name</label>
              <input 
                type="text" 
                id="company" 
                v-model="form.company" 
                class="form-input"
              >
            </div>
            
            <div class="form-group">
              <label for="service">Service Interest</label>
              <select id="service" v-model="form.service" class="form-select">
                <option value="">Select a service...</option>
                <option value="bookkeeping">Bookkeeping Services</option>
                <option value="controller">Fractional Financial Controller</option>
                <option value="tax">Tax Preparation & Planning</option>
                <option value="payroll">Payroll Services</option>
                <option value="consulting">Financial Consulting</option>
                <option value="other">Other</option>
              </select>
            </div>
            
            <div class="form-group">
              <label for="message">Message *</label>
              <textarea 
                id="message" 
                v-model="form.message" 
                required 
                rows="5" 
                class="form-textarea"
                placeholder="Please tell us about your business and how we can help..."
              ></textarea>
            </div>
            
            <button type="submit" class="btn btn-primary btn-large form-submit" :disabled="isSubmitting">
              {{ isSubmitting ? 'Sending...' : 'Send Message' }}
            </button>
            
            <p class="form-note">
              * Required fields. We'll get back to you within 24 hours.
            </p>
          </form>
        </div>
      </div>
      
      <!-- Trust indicators -->
      <div class="trust-section">
        <div class="trust-content">
          <h3>Why Choose GS Online Services?</h3>
          <div class="trust-indicators">
            <div class="trust-item">
              <div class="trust-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M12,1L3,5V11C3,16.55 6.84,21.74 12,23C17.16,21.74 21,16.55 21,11V5L12,1M10,17L6,13L7.41,11.59L10,14.17L16.59,7.58L18,9L10,17Z"/>
                </svg>
              </div>
              <div class="trust-text">
                <h4>Secure & Confidential</h4>
                <p>Your data is protected with bank-level security</p>
              </div>
            </div>
            
            <div class="trust-item">
              <div class="trust-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M11,14L17.5,7.5L16.09,6.09L11,11.18L7.91,8.09L6.5,9.5L11,14Z"/>
                </svg>
              </div>
              <div class="trust-text">
                <h4>Qualified Professionals</h4>
                <p>Certified accountants with 15+ years experience</p>
              </div>
            </div>
            
            <div class="trust-item">
              <div class="trust-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="var(--primary)">
                  <path d="M13,9H11V7H13M13,17H11V11H13M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2Z"/>
                </svg>
              </div>
              <div class="trust-text">
                <h4>Transparent Pricing</h4>
                <p>Fixed monthly fees with no hidden charges</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const isSubmitting = ref(false)

const form = reactive({
  firstName: '',
  lastName: '',
  email: '',
  company: '',
  service: '',
  message: ''
})

const handleSubmit = async () => {
  isSubmitting.value = true
  
  try {
    // Here you would typically send the form data to your backend
    // For now, we'll simulate a form submission
    await new Promise(resolve => setTimeout(resolve, 1000))
    
    // Reset form after successful submission
    Object.keys(form).forEach(key => {
      form[key] = ''
    })
    
    // Show success message (you could add a toast notification here)
    alert('Thank you for your message! We\'ll get back to you within 24 hours.')
    
  } catch (error) {
    console.error('Form submission error:', error)
    alert('Sorry, there was an error sending your message. Please try again.')
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
.section {
  padding: 5rem 0;
  background: var(--white);
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-bottom: 4rem;
}

.info-header h2 {
  font-size: 2.5rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.info-header p {
  color: var(--gray-600);
  margin-bottom: 2rem;
}

.contact-methods {
  margin-bottom: 2rem;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding: 1rem;
  background: var(--gray-50);
  border-radius: 0.5rem;
}

.method-icon {
  flex-shrink: 0;
  width: 48px;
  height: 48px;
  background: rgba(82, 115, 108, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.method-content h4 {
  font-size: 1.125rem;
  color: var(--primary);
  margin-bottom: 0.25rem;
}

.method-content a {
  color: var(--gray-600);
  text-decoration: none;
}

.method-content a:hover {
  color: var(--primary);
}

.method-content p {
  color: var(--gray-600);
  margin: 0;
  font-size: 0.9rem;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-form-container {
  background: var(--gray-50);
  padding: 2rem;
  border-radius: 1rem;
}

.contact-form h3 {
  font-size: 1.5rem;
  color: var(--primary);
  margin-bottom: 1.5rem;
  text-align: center;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: var(--gray-800);
  font-weight: 500;
}

.form-input,
.form-select,
.form-textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid var(--gray-300);
  border-radius: 0.5rem;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-input:focus,
.form-select:focus,
.form-textarea:focus {
  outline: none;
  border-color: var(--primary);
}

.form-textarea {
  resize: vertical;
  min-height: 120px;
}

.form-submit {
  width: 100%;
  margin-bottom: 1rem;
}

.form-submit:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.form-note {
  font-size: 0.875rem;
  color: var(--gray-600);
  text-align: center;
  margin: 0;
}

.trust-section {
  background: var(--gray-50);
  padding: 3rem 2rem;
  border-radius: 1rem;
}

.trust-content h3 {
  font-size: 1.75rem;
  color: var(--primary);
  text-align: center;
  margin-bottom: 2rem;
}

.trust-indicators {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  text-align: left;
}

.trust-icon {
  flex-shrink: 0;
  width: 60px;
  height: 60px;
  background: rgba(82, 115, 108, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.trust-text h4 {
  font-size: 1.125rem;
  color: var(--primary);
  margin-bottom: 0.25rem;
}

.trust-text p {
  color: var(--gray-600);
  margin: 0;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .info-header h2 {
    font-size: 2rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
  }
  
  .contact-form-container {
    padding: 1.5rem;
  }
  
  .trust-indicators {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .trust-item {
    flex-direction: column;
    text-align: center;
  }
  
  .cta-buttons {
    flex-direction: column;
  }
}

@media (max-width: 480px) {
  .contact-method {
    flex-direction: column;
    text-align: center;
  }
  
  .trust-section {
    padding: 2rem 1rem;
  }
}
</style>