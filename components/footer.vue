<template>
  <div class="footer-container1">
    <div class="footer-container2">
      <div class="footer-container3">
        <DangerousHTML
          html="<style>
          @keyframes footer-grid-move {0% {transform: translate(0, 0);}
  100% {transform: translate(40px, 40px);}}@keyframes footer-scanline-move {0%,100% {transform: translateY(0) scaleX(0.3);
  opacity: 0;}
  50% {transform: translateY(400px) scaleX(1);
  opacity: 1;}}@keyframes footer-logo-pulse {0%,100% {opacity: 0.3;
  transform: translate(-50%, -50%) scale(1);}
  50% {opacity: 0.5;
  transform: translate(-50%, -50%) scale(1.1);}}@keyframes footer-divider-pulse {0%,100% {opacity: 0.2;
  transform: translate(-50%, -50%) scaleX(1);}
  50% {opacity: 0.4;
  transform: translate(-50%, -50%) scaleX(1.2);}}@keyframes footer-particle-float {0%,100% {transform: translateY(100vh) scale(0);
  opacity: 0;}
  10% {opacity: 1;}
  90% {opacity: 1;}
  100% {transform: translateY(-20px) scale(1);
  opacity: 0;}}
          </style> "
        ></DangerousHTML>
      </div>
    </div>
    <div class="footer-container4">
      <div class="footer-container5">
        <DangerousHTML
          html="<style>
  a.footer-contact-value:hover {
    color: var(--color-primary);
  }
  @media (prefers-reduced-motion: reduce) {
  .footer-bg-pattern, .footer-scanline, .footer-logo-glow, .footer-divider-glow, .footer-particle {
    animation: none;
  }
  .footer-badge:hover, .footer-link:hover, .footer-contact-item:hover, .footer-social-link:hover {
    transform: none;
  }
  }
  </style>"
        ></DangerousHTML>
      </div>
    </div>
    <div class="footer-container6">
      <div class="footer-container7">
        <DangerousHTML
          html="<script defer data-name='footer-solvesphere'>
  (function(){
    // Enhanced footer interactions for tech-savvy experience
  
    // Glowing link trail effect
    const footerLinks = document.querySelectorAll(
      '.footer-link, .footer-legal-link, .footer-social-link'
    )
  
    footerLinks.forEach((link) => {
      link.addEventListener('mouseenter', function (e) {
        const ripple = document.createElement('span')
        ripple.style.position = 'absolute'
        ripple.style.width = '6px'
        ripple.style.height = '6px'
        ripple.style.background = 'var(--color-primary)'
        ripple.style.borderRadius = '50%'
        ripple.style.pointerEvents = 'none'
        ripple.style.boxShadow = '0 0 10px var(--color-primary)'
        ripple.style.opacity = '0'
        ripple.style.transition = 'all 0.6s ease-out'
        ripple.style.left = e.offsetX + 'px'
        ripple.style.top = e.offsetY + 'px'
        ripple.style.zIndex = '10'
  
        this.style.position = 'relative'
        this.appendChild(ripple)
  
        setTimeout(() => {
          ripple.style.opacity = '1'
          ripple.style.transform = 'scale(3)'
        }, 10)
  
        setTimeout(() => {
          ripple.style.opacity = '0'
          setTimeout(() => ripple.remove(), 600)
        }, 300)
      })
    })
  
    // Tech stats counter animation
    const statValues = document.querySelectorAll('.footer-stat-value')
    const observerOptions = {
      threshold: 0.5,
      rootMargin: '0px',
    }
  
    const statsObserver = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.style.animation =
            'footer-stat-glow 2s ease-in-out infinite'
        }
      })
    }, observerOptions)
  
    statValues.forEach((stat) => {
      statsObserver.observe(stat)
    })
  
    // Add glow animation dynamically
    const style = document.createElement('style')
    style.textContent = `
    @keyframes footer-stat-glow {
      0%, 100% {
        text-shadow: 0 0 10px color-mix(in srgb, var(--color-primary) 30%, transparent);
      }
      50% {
        text-shadow: 0 0 20px color-mix(in srgb, var(--color-primary) 60%, transparent),
                     0 0 30px color-mix(in srgb, var(--color-primary) 40%, transparent);
      }
    }
  `
    document.head.appendChild(style)
  
    // Contact item hover enhancement
    const contactItems = document.querySelectorAll('.footer-contact-item')
    contactItems.forEach((item) => {
      item.addEventListener('mouseenter', function () {
        const icon = this.querySelector('.footer-contact-icon')
        if (icon) {
          icon.style.transition = 'all 0.3s var(--animation-curve-primary)'
        }
      })
    })
  
    // Social link sequential hover effect
    const socialLinks = document.querySelectorAll('.footer-social-link')
    let hoverTimeout
  
    socialLinks.forEach((link, index) => {
      link.addEventListener('mouseenter', function () {
        clearTimeout(hoverTimeout)
  
        socialLinks.forEach((otherLink, otherIndex) => {
          if (otherIndex !== index) {
            hoverTimeout = setTimeout(() => {
              otherLink.style.opacity = '0.5'
              otherLink.style.transform = 'scale(0.95)'
            }, 50)
          }
        })
      })
  
      link.addEventListener('mouseleave', function () {
        clearTimeout(hoverTimeout)
        socialLinks.forEach((otherLink) => {
          otherLink.style.opacity = '1'
          otherLink.style.transform = 'scale(1)'
        })
      })
    })
  
    // Trust badge pulse effect on scroll
    const trustBadges = document.querySelectorAll('.footer-badge')
    const badgeObserver = new IntersectionObserver((entries) => {
      entries.forEach((entry, index) => {
        if (entry.isIntersecting) {
          setTimeout(() => {
            entry.target.style.animation =
              'footer-badge-appear 0.6s ease-out forwards'
          }, index * 100)
        }
      })
    }, observerOptions)
  
    trustBadges.forEach((badge) => {
      badge.style.opacity = '0'
      badge.style.transform = 'translateY(20px)'
      badgeObserver.observe(badge)
    })
  
    const badgeStyle = document.createElement('style')
    badgeStyle.textContent = `
    @keyframes footer-badge-appear {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  `
    document.head.appendChild(badgeStyle)
  
    // Logo glow intensity on hover
    const logo = document
      .getElementById('footer-solvesphere')
      .querySelector('.footer-logo-wrapper')
    if (logo) {
      logo.addEventListener('mouseenter', function () {
        const glow = this.querySelector('.footer-logo-glow')
        if (glow) {
          glow.style.opacity = '0.6'
          glow.style.transform = 'translate(-50%, -50%) scale(1.3)'
        }
      })
  
      logo.addEventListener('mouseleave', function () {
        const glow = this.querySelector('.footer-logo-glow')
        if (glow) {
          glow.style.opacity = '0.3'
          glow.style.transform = 'translate(-50%, -50%) scale(1)'
        }
      })
    }
  })()
  </script>"
        ></DangerousHTML>
      </div>
    </div>
    <footer id="footer-solvesphere" class="footer-container">
      <div aria-hidden="true" class="footer-bg-pattern"></div>
      <div aria-hidden="true" class="footer-scanline"></div>
      <div class="footer-content-wrapper">
        <div class="footer-main">
          <div class="footer-brand-column">
            <div class="footer-logo-wrapper">
              <div aria-hidden="true" class="footer-logo-glow"></div>
              <h2 class="footer-logo">SolveSphere</h2>
            </div>
            <p class="footer-tagline">
              Instant Problem Solver. AI-powered solutions connecting you with
              expert service providers for every challenge.
              <span v-html="raw268f"></span>
            </p>
            <div class="footer-trust-badges">
              <div class="footer-badge">
                <div class="footer-badge-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                </div>
                <span class="footer-badge-text">Secure</span>
              </div>
              <div class="footer-badge">
                <div class="footer-badge-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M4 14a1 1 0 0 1-.78-1.63l9.9-10.2a.5.5 0 0 1 .86.46l-1.92 6.02A1 1 0 0 0 13 10h7a1 1 0 0 1 .78 1.63l-9.9 10.2a.5.5 0 0 1-.86-.46l1.92-6.02A1 1 0 0 0 11 14z"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                </div>
                <span class="footer-badge-text">Fast AI</span>
              </div>
              <div class="footer-badge">
                <div class="footer-badge-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <g
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    >
                      <path
                        d="m15.477 12.89l1.515 8.526a.5.5 0 0 1-.81.47l-3.58-2.687a1 1 0 0 0-1.197 0l-3.586 2.686a.5.5 0 0 1-.81-.469l1.514-8.526"
                      ></path>
                      <circle r="6" cx="12" cy="8"></circle>
                    </g>
                  </svg>
                </div>
                <span class="footer-badge-text">Verified Experts</span>
              </div>
            </div>
          </div>
          <div class="footer-links-column">
            <h3 class="footer-column-title">
              <span class="footer-footer-title-accent1"></span>
              <span>
                Quick Links
                <span v-html="rawq825"></span>
              </span>
            </h3>
            <ul class="footer-links-list">
              <li class="footer-link-item">
                <a href="/">
                  <div class="footer-link"><span>Homepage</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#about">
                  <div class="footer-link"><span>About IPS</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#how-it-works">
                  <div class="footer-link"><span>How It Works</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#services">
                  <div class="footer-link"><span>Service Categories</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#experts">
                  <div class="footer-link"><span>Find Experts</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#pricing">
                  <div class="footer-link"><span>Pricing</span></div>
                </a>
              </li>
            </ul>
          </div>
          <div class="footer-links-column">
            <h3 class="footer-column-title">
              <span class="footer-footer-title-accent2"></span>
              <span>
                For Experts
                <span v-html="rawhjzy"></span>
              </span>
            </h3>
            <ul class="footer-links-list">
              <li class="footer-link-item">
                <a href="#register-expert">
                  <div class="footer-link"><span>Become an Expert</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#expert-dashboard">
                  <div class="footer-link"><span>Expert Dashboard</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#earnings">
                  <div class="footer-link">
                    <span>Earnings &amp; Payouts</span>
                  </div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#expert-guidelines">
                  <div class="footer-link">
                    <span>
                      Service Guidelines
                      <span v-html="rawuzsn"></span>
                    </span>
                  </div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#expert-support">
                  <div class="footer-link"><span>Expert Support</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#ratings">
                  <div class="footer-link">
                    <span>Ratings &amp; Reviews</span>
                  </div>
                </a>
              </li>
            </ul>
          </div>
          <div class="footer-links-column">
            <h3 class="footer-column-title">
              <span class="footer-footer-title-accent3"></span>
              <span>
                Support
                <span v-html="rawqamm"></span>
              </span>
            </h3>
            <ul class="footer-links-list">
              <li class="footer-link-item">
                <a href="#faq">
                  <div class="footer-link"><span>FAQ</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#help-center">
                  <div class="footer-link"><span>Help Center</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#booking-process">
                  <div class="footer-link"><span>Booking Process</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#payment-info">
                  <div class="footer-link"><span>Payment Information</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#rewards">
                  <div class="footer-link"><span>Reward Points</span></div>
                </a>
              </li>
              <li class="footer-link-item">
                <a href="#safety">
                  <div class="footer-link">
                    <span>Safety &amp; Security</span>
                  </div>
                </a>
              </li>
            </ul>
          </div>
          <div class="footer-contact-column">
            <h3 class="footer-column-title">
              <span class="footer-footer-title-accent4"></span>
              <span>
                Get in Touch
                <span v-html="rawm9vz"></span>
              </span>
            </h3>
            <div class="footer-contact-items">
              <div class="footer-contact-item">
                <div class="footer-contact-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M13.832 16.568a1 1 0 0 0 1.213-.303l.355-.465A2 2 0 0 1 17 15h3a2 2 0 0 1 2 2v3a2 2 0 0 1-2 2A18 18 0 0 1 2 4a2 2 0 0 1 2-2h3a2 2 0 0 1 2 2v3a2 2 0 0 1-.8 1.6l-.468.351a1 1 0 0 0-.292 1.233a14 14 0 0 0 6.392 6.384"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                </div>
                <div class="footer-contact-info">
                  <span class="footer-contact-label">Call Us</span>
                  <a href="tel:+911234567890">
                    <div class="footer-contact-value">
                      <span>
                        +91 123 456 7890
                        <span v-html="raws5pq"></span>
                      </span>
                    </div>
                  </a>
                </div>
              </div>
              <div class="footer-contact-item">
                <div class="footer-contact-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <g
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    >
                      <path d="m22 7l-8.991 5.727a2 2 0 0 1-2.009 0L2 7"></path>
                      <rect x="2" y="4" rx="2" width="20" height="16"></rect>
                    </g>
                  </svg>
                </div>
                <div class="footer-contact-info">
                  <span class="footer-contact-label">Email Us</span>
                  <a href="mailto:support@solvesphere.com?subject=">
                    <div class="footer-contact-value">
                      <span>
                        support@solvesphere.com
                        <span v-html="rawhnc8"></span>
                      </span>
                    </div>
                  </a>
                </div>
              </div>
              <div class="footer-contact-item">
                <div class="footer-contact-icon">
                  <svg
                    width="24"
                    xmlns="http://www.w3.org/2000/svg"
                    height="24"
                    viewBox="0 0 24 24"
                  >
                    <g
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    >
                      <path
                        d="M17.97 9.304A8 8 0 0 0 2 10c0 4.69 4.887 9.562 7.022 11.468m12.356-4.842a1 1 0 0 0-3.004-3.004l-4.01 4.012a2 2 0 0 0-.506.854l-.837 2.87a.5.5 0 0 0 .62.62l2.87-.837a2 2 0 0 0 .854-.506z"
                      ></path>
                      <circle r="3" cx="10" cy="10"></circle>
                    </g>
                  </svg>
                </div>
                <div class="footer-contact-info">
                  <span class="footer-contact-label">Location</span>
                  <span class="footer-contact-value">
                    Mumbai, Maharashtra, India
                    <span v-html="raw5dyq"></span>
                  </span>
                </div>
              </div>
            </div>
            <div class="footer-social-section">
              <h4 class="footer-social-title">Follow Us</h4>
              <div class="footer-social-links">
                <a href="#facebook">
                  <div aria-label="Facebook" class="footer-social-link">
                    <svg
                      width="24"
                      xmlns="http://www.w3.org/2000/svg"
                      height="24"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </a>
                <a href="#twitter">
                  <div aria-label="Twitter" class="footer-social-link">
                    <svg
                      width="24"
                      xmlns="http://www.w3.org/2000/svg"
                      height="24"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6c2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4c-.9-4.2 4-6.6 7-3.8c1.1 0 3-1.2 3-1.2"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </a>
                <a href="#linkedin">
                  <div aria-label="LinkedIn" class="footer-social-link">
                    <svg
                      width="24"
                      xmlns="http://www.w3.org/2000/svg"
                      height="24"
                      viewBox="0 0 24 24"
                    >
                      <g
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      >
                        <path
                          d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2a2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6M2 9h4v12H2z"
                        ></path>
                        <circle r="2" cx="4" cy="4"></circle>
                      </g>
                    </svg>
                  </div>
                </a>
                <a href="#instagram">
                  <div aria-label="Instagram" class="footer-social-link">
                    <svg
                      width="24"
                      xmlns="http://www.w3.org/2000/svg"
                      height="24"
                      viewBox="0 0 24 24"
                    >
                      <g
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      >
                        <rect
                          x="2"
                          y="2"
                          rx="5"
                          ry="5"
                          width="20"
                          height="20"
                        ></rect>
                        <path
                          d="M16 11.37A4 4 0 1 1 12.63 8A4 4 0 0 1 16 11.37m1.5-4.87h.01"
                        ></path>
                      </g>
                    </svg>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>
        <div class="footer-divider">
          <div class="footer-divider-line"></div>
          <div aria-hidden="true" class="footer-divider-glow"></div>
        </div>
        <div class="footer-bottom">
          <div class="footer-bottom-content">
            <p class="footer-copyright">
              © 2025 SolveSphere. All rights reserved. Powered by AI &amp;
              Innovation.
              <span v-html="raw9aha"></span>
            </p>
            <div class="footer-legal-links">
              <a href="#privacy">
                <div class="footer-legal-link"><span>Privacy Policy</span></div>
              </a>
              <span class="footer-legal-separator">•</span>
              <a href="#terms">
                <div class="footer-legal-link"><span>Terms of Service</span></div>
              </a>
              <span class="footer-legal-separator">•</span>
              <a href="#cookies">
                <div class="footer-legal-link"><span>Cookie Policy</span></div>
              </a>
              <span class="footer-legal-separator">•</span>
              <a href="#refund">
                <div class="footer-legal-link"><span>Refund Policy</span></div>
              </a>
            </div>
          </div>
          <div class="footer-stats">
            <div class="footer-stat-item">
              <span class="footer-stat-value">99.9%</span>
              <span class="footer-stat-label">Uptime</span>
            </div>
            <div class="footer-stat-divider"></div>
            <div class="footer-stat-item">
              <span class="footer-stat-value">24/7</span>
              <span class="footer-stat-label">Support</span>
            </div>
            <div class="footer-stat-divider"></div>
            <div class="footer-stat-item">
              <span class="footer-stat-value">AI</span>
              <span class="footer-stat-label">Powered</span>
            </div>
          </div>
        </div>
      </div>
      <div aria-hidden="true" class="footer-particles">
        <div class="footer-particle"></div>
        <div class="footer-particle"></div>
        <div class="footer-particle"></div>
        <div class="footer-particle"></div>
        <div class="footer-particle"></div>
        <div class="footer-particle"></div>
      </div>
    </footer>
  </div>
</template>

<script>
import DangerousHTML from 'dangerous-html/dist/vue/lib.js'

export default {
  name: 'Footer',
  props: {},
  components: {
    DangerousHTML,
  },
  data() {
    return {
      raw268f: ' ',
      rawq825: ' ',
      rawhjzy: ' ',
      rawuzsn: ' ',
      rawqamm: ' ',
      rawm9vz: ' ',
      raws5pq: ' ',
      rawhnc8: ' ',
      raw5dyq: ' ',
      raw9aha: ' ',
    }
  },
}
</script>

<style scoped>
.footer-container1 {
  display: contents;
}
 
.footer-container2 {
  display: none;
}
 
.footer-container3 {
  display: contents;
}
 
.footer-container4 {
  display: none;
}
 
.footer-container5 {
  display: contents;
}
 
.footer-container6 {
  display: none;
}
 
.footer-container7 {
  display: contents;
}
 
.footer-footer-title-accent1 {
  top: 50%;
  left: 0;
  width: 3px;
  height: 100%;
  position: absolute;
  transform: translateY(-50%);
  background: linear-gradient(
      180deg,
      var(--color-primary) 0%,
      var(--color-accent) 100%
    );
  box-shadow: 0 0 10px var(--color-primary);
  border-radius: var(--border-radius-sm);
}
 
.footer-footer-title-accent2 {
  top: 50%;
  left: 0;
  width: 3px;
  height: 100%;
  position: absolute;
  transform: translateY(-50%);
  background: linear-gradient(
      180deg,
      var(--color-primary) 0%,
      var(--color-accent) 100%
    );
  box-shadow: 0 0 10px var(--color-primary);
  border-radius: var(--border-radius-sm);
}
 
.footer-footer-title-accent3 {
  top: 50%;
  left: 0;
  width: 3px;
  height: 100%;
  position: absolute;
  transform: translateY(-50%);
  background: linear-gradient(
      180deg,
      var(--color-primary) 0%,
      var(--color-accent) 100%
    );
  box-shadow: 0 0 10px var(--color-primary);
  border-radius: var(--border-radius-sm);
}
 
.footer-footer-title-accent4 {
  top: 50%;
  left: 0;
  width: 3px;
  height: 100%;
  position: absolute;
  transform: translateY(-50%);
  background: linear-gradient(
      180deg,
      var(--color-primary) 0%,
      var(--color-accent) 100%
    );
  box-shadow: 0 0 10px var(--color-primary);
  border-radius: var(--border-radius-sm);
}
</style>
