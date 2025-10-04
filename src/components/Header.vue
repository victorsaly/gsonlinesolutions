<template>
  <header class="header-area">
    <!-- Navigation Bar -->
    <nav class="navbar navbar-expand-lg navbar-light fixed-top">
      <div class="container">
        <!-- Brand Logo -->
        <a class="navbar-brand" href="/">
          <img src="/logo_gs.svg" alt="GS Online Solutions" class="logo-img">
        </a>

        <!-- Mobile Menu Toggle -->
        <button 
          class="navbar-toggler" 
          type="button" 
          data-bs-toggle="collapse" 
          data-bs-target="#navbarNav"
          aria-controls="navbarNav" 
          aria-expanded="false" 
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <!-- Navigation Menu -->
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#home">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#about">About</a>
            </li>
            <li class="nav-item dropdown">
              <a 
                class="nav-link dropdown-toggle" 
                href="#services" 
                id="servicesDropdown" 
                role="button" 
                data-bs-toggle="dropdown" 
                aria-expanded="false"
              >
                Services
              </a>
              <ul class="dropdown-menu" aria-labelledby="servicesDropdown">
                <li><a class="dropdown-item" href="#services">All Services</a></li>
                <li><hr class="dropdown-divider"></li>
                <li><a class="dropdown-item" href="/services/bookkeeping">
                  <i class="ri-file-list-3-line"></i>
                  Professional Bookkeeping
                </a></li>
                <li><a class="dropdown-item" href="/services/tax-preparation">
                  <i class="ri-calculator-line"></i>
                  Tax Preparation & Planning
                </a></li>
                <li><a class="dropdown-item" href="/services/financial-controller">
                  <i class="ri-line-chart-line"></i>
                  Fractional Financial Controller
                </a></li>
                <li><hr class="dropdown-divider"></li>
                <li><a class="dropdown-item" href="/extended-services">
                  <i class="ri-more-line"></i>
                  Extended Services
                </a></li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#contact">Contact</a>
            </li>
          </ul>
          
          <!-- CTA Button -->
          <div class="navbar-cta ms-3">
            <a href="#contact" class="btn btn-primary">
              <i class="ri-phone-line"></i>
              Get Quote
            </a>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Handle navbar scroll effect
  const navbar = document.querySelector('.navbar')
  
  const handleScroll = () => {
    if (window.scrollY > 50) {
      navbar?.classList.add('scrolled')
    } else {
      navbar?.classList.remove('scrolled')
    }
  }
  
  window.addEventListener('scroll', handleScroll)
  
  // Active link highlighting
  const sections = document.querySelectorAll('section[id]')
  const navLinks = document.querySelectorAll('.nav-link[href^="#"]')
  
  const highlightActiveLink = () => {
    let current = ''
    
    sections.forEach(section => {
      const sectionTop = section.offsetTop - 100
      const sectionHeight = section.offsetHeight
      
      if (window.scrollY >= sectionTop && window.scrollY < sectionTop + sectionHeight) {
        current = section.getAttribute('id')
      }
    })
    
    navLinks.forEach(link => {
      link.classList.remove('active')
      if (link.getAttribute('href') === `#${current}`) {
        link.classList.add('active')
      }
    })
  }
  
  window.addEventListener('scroll', highlightActiveLink)
  
  // Cleanup on unmount
  return () => {
    window.removeEventListener('scroll', handleScroll)
    window.removeEventListener('scroll', highlightActiveLink)
  }
})
</script>

<style scoped>
.header-area {
  position: relative;
  z-index: 1000;
}

.navbar {
  padding: 20px 0;
  transition: var(--transition);
  background: transparent;
}

.navbar.scrolled {
  padding: 15px 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 37, 44, 0.1);
}

.navbar-brand {
  display: flex;
  align-items: center;
  text-decoration: none;
  font-weight: 700;
  font-size: 24px;
  color: var(--whiteColor);
  transition: var(--transition);
}

.navbar.scrolled .navbar-brand {
  color: var(--primaryColor);
}

.logo-img {
  width: 180px;
  height: 80px;
  filter: brightness(0) invert(1);
  transition: var(--transition);
}

.navbar.scrolled .logo-img {
  filter: brightness(0) saturate(100%) invert(27%) sepia(8%) saturate(1000%) hue-rotate(88deg) brightness(95%) contrast(90%);
}



.navbar-toggler {
  border: none;
  padding: 4px 8px;
  background: var(--secondaryColor);
  border-radius: 6px;
}

.navbar-toggler:focus {
  box-shadow: none;
}

.navbar-nav {
  align-items: center;
}

.nav-link {
  color: var(--whiteColor) !important;
  font-family: var(--primaryFont);
  font-weight: 500;
  font-size: 16px;
  margin: 0 8px;
  padding: 8px 16px !important;
  border-radius: 6px;
  transition: var(--transition);
  position: relative;
}

.navbar.scrolled .nav-link {
  color: var(--primaryColor) !important;
}

.nav-link:hover,
.nav-link.active {
  color: var(--whiteColor) !important;
  background: rgba(185, 248, 177, 0.1);
}

.navbar.scrolled .nav-link:hover,
.navbar.scrolled .nav-link.active {
  color: var(--primaryColor) !important;
  background: rgba(0, 37, 44, 0.05);
}

.dropdown-menu {
  background: var(--whiteColor);
  border: 1px solid rgba(0, 37, 44, 0.1);
  border-radius: 12px;
  box-shadow: 0 10px 40px rgba(0, 37, 44, 0.15);
  padding: 12px 0;
  margin-top: 8px;
  min-width: 220px;
}

.dropdown-item {
  color: var(--titleColor);
  font-family: var(--primaryFont);
  font-weight: 500;
  padding: 10px 20px;
  transition: var(--transition);
}

.dropdown-item:hover {
  color: var(--primaryColor);
  background: rgba(185, 248, 177, 0.1);
}

.navbar-cta .btn {
  padding: 10px 24px;
  font-weight: 600;
  font-size: 14px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  gap: 8px;
}

.navbar-cta .btn i {
  font-size: 16px;
}

/* Dropdown menu styling */
.dropdown-menu {
  border: none;
  box-shadow: 0 10px 30px rgba(0, 37, 44, 0.15);
  border-radius: 12px;
  padding: 12px 0;
  margin-top: 8px;
}

.dropdown-item {
  padding: 12px 20px;
  display: flex;
  align-items: center;
  gap: 12px;
  transition: all 0.3s ease;
}

.dropdown-item i {
  font-size: 16px;
  color: var(--primaryColor);
  width: 20px;
}

.dropdown-item:hover {
  background: linear-gradient(135deg, rgba(185, 248, 177, 0.1), rgba(168, 231, 160, 0.1));
  color: var(--primaryColor);
}

.dropdown-divider {
  margin: 8px 16px;
  border-color: rgba(0, 37, 44, 0.1);
}

/* Mobile Responsive */
@media (max-width: 991px) {
  .navbar {
    background: var(--whiteColor) !important;
    box-shadow: 0 2px 10px rgba(0, 37, 44, 0.1);
  }
  
  .logo-img {
    filter: brightness(0) saturate(100%) invert(27%) sepia(8%) saturate(1000%) hue-rotate(88deg) brightness(95%) contrast(90%);
  }
  
  .navbar-collapse {
    margin-top: 20px;
    padding-top: 20px;
    border-top: 1px solid rgba(0, 37, 44, 0.1);
  }
  
  .nav-link {
    color: var(--titleColor) !important;
    padding: 12px 0 !important;
    margin: 0;
    border-radius: 0;
  }
  
  .nav-link:hover,
  .nav-link.active {
    color: var(--primaryColor) !important;
    background: transparent;
  }
  
  .navbar-cta {
    margin-top: 20px;
    margin-left: 0 !important;
  }
  
  .navbar-cta .btn {
    width: 100%;
    justify-content: center;
  }
}

@media (max-width: 576px) {
  .brand-text {
    font-size: 18px;
  }
  
  .logo-img {
    width: 50px;
    height: 50px;
  }
}
</style>
