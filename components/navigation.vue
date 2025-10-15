<template>
  <div class="navigation-container1">
    <div class="navigation-container2">
      <div class="navigation-container3">
        <DangerousHTML
          html="<style>
          @keyframes navigation-glow-pulse {0%,100% {opacity: 0.4;}
  50% {opacity: 0.8;}}@keyframes navigation-orbit-spin {from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}}@keyframes navigation-core-pulse {0%,100% {transform: scale(1);}
  50% {transform: scale(1.15);}}@keyframes navigation-slide-in {to {opacity: 1;
  transform: translateX(0);}}@keyframes navigation-scanline {0%,100% {opacity: 0;
  transform: translateX(-100%);}
  50% {opacity: 0.6;
  transform: translateX(100%);}}
          </style> "
        ></DangerousHTML>
      </div>
    </div>
    <div class="navigation-container4">
      <div class="navigation-container5">
        <DangerousHTML
          html="<script defer data-name='navigation'>
  (function(){
    const navigationToggle = document.getElementById('navigationToggle')
    const navigationMobile = document.getElementById('navigationMobile')
    const navigation = document.getElementById('navigationMain')
  
    // Toggle mobile menu
    navigationToggle.addEventListener('click', () => {
      const isExpanded = navigationToggle.getAttribute('aria-expanded') === 'true'
  
      navigationToggle.setAttribute('aria-expanded', !isExpanded)
      navigationMobile.classList.toggle('navigation__mobile--active')
  
      // Prevent body scroll when menu is open
      if (!isExpanded) {
        document.body.style.overflow = 'hidden'
      } else {
        document.body.style.overflow = ''
      }
    })
  
    // Close mobile menu when clicking on backdrop
    const backdrop = navigationMobile.querySelector(
      '.navigation__mobile-backdrop'
    )
    backdrop.addEventListener('click', () => {
      navigationToggle.setAttribute('aria-expanded', 'false')
      navigationMobile.classList.remove('navigation__mobile--active')
      document.body.style.overflow = ''
    })
  
    // Close mobile menu when clicking on a link
    const mobileLinks = navigationMobile.querySelectorAll(
      '.navigation__mobile-link'
    )
    mobileLinks.forEach((link) => {
      link.addEventListener('click', () => {
        navigationToggle.setAttribute('aria-expanded', 'false')
        navigationMobile.classList.remove('navigation__mobile--active')
        document.body.style.overflow = ''
      })
    })
  
    // Add scroll effect to navigation
    let lastScroll = 0
    window.addEventListener('scroll', () => {
      const currentScroll = window.pageYOffset
  
      if (currentScroll > 100) {
        navigation.style.background =
          'color-mix(in srgb, var(--color-surface) 95%, transparent)'
        navigation.style.boxShadow =
          '0 8px 32px color-mix(in srgb, var(--color-primary) 15%, transparent)'
      } else {
        navigation.style.background =
          'color-mix(in srgb, var(--color-surface) 85%, transparent)'
        navigation.style.boxShadow =
          '0 4px 24px color-mix(in srgb, var(--color-primary) 8%, transparent)'
      }
  
      lastScroll = currentScroll
    })
  
    // Add active state to current section link
    const sections = document.querySelectorAll('section[id]')
    const navLinks = document.querySelectorAll('.navigation__link')
  
    const observerOptions = {
      root: null,
      rootMargin: '-50% 0px -50% 0px',
      threshold: 0,
    }
  
    const observerCallback = (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const sectionId = entry.target.getAttribute('id')
  
          navLinks.forEach((link) => {
            const linkHref = link.getAttribute('href')
            if (linkHref === `#${sectionId}`) {
              link.style.opacity = '1'
            } else {
              link.style.opacity = '0.7'
            }
          })
        }
      })
    }
  
    const observer = new IntersectionObserver(observerCallback, observerOptions)
  
    sections.forEach((section) => {
      observer.observe(section)
    })
  })()
  </script>"
        ></DangerousHTML>
      </div>
    </div>
    <nav id="navigationMain" aria-label="Main navigation" class="navigation">
      <div class="navigation__container">
        <a href="/">
          <div aria-label="SolveSphere - Homepage" class="navigation__logo">
            <div class="navigation__logo-icon">
              <div class="navigation__logo-orbit"></div>
              <div class="navigation__logo-core"></div>
            </div>
            <span class="navigation__logo-text">SolveSphere</span>
          </div>
        </a>
        <div class="navigation__links">
          <a href="#solutions">
            <div class="navigation__link">
              <span class="navigation__link-text">AI Solutions</span>
              <span class="navigation__link-glow"></span>
            </div>
          </a>
          <a href="#experts">
            <div class="navigation__link">
              <span class="navigation__link-text">Find Experts</span>
              <span class="navigation__link-glow"></span>
            </div>
          </a>
          <a href="#categories">
            <div class="navigation__link">
              <span class="navigation__link-text">Categories</span>
              <span class="navigation__link-glow"></span>
            </div>
          </a>
          <a href="#how-it-works">
            <div class="navigation__link">
              <span class="navigation__link-text">How It Works</span>
              <span class="navigation__link-glow"></span>
            </div>
          </a>
          <a href="#about">
            <div class="navigation__link">
              <span class="navigation__link-text">About</span>
              <span class="navigation__link-glow"></span>
            </div>
          </a>
        </div>
        <div class="navigation__actions">
          <button
            id="navigationSearchBtn"
            aria-label="Search"
            class="navigation__search-btn navigation__action-btn"
          >
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
                <path d="m21 21l-4.34-4.34"></path>
                <circle r="8" cx="11" cy="11"></circle>
              </g>
            </svg>
          </button>
          <a href="#login">
            <div aria-label="User account" class="navigation__action-btn">
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
                  <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"></path>
                  <circle r="4" cx="12" cy="7"></circle>
                </g>
              </svg>
            </div>
          </a>
          <button class="navigation__cta btn-primary btn">Get Started</button>
          <button
            id="navigationToggle"
            aria-label="Toggle mobile menu"
            aria-expanded="false"
            class="navigation__toggle"
          >
            <span class="navigation-navigationtoggle-icon">
              <svg
                width="24"
                xmlns="http://www.w3.org/2000/svg"
                height="24"
                viewBox="0 0 24 24"
                class="navigation-navigationtoggle-menu"
              >
                <path
                  d="M4 5h16M4 12h16M4 19h16"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path></svg
              ><svg
                width="24"
                xmlns="http://www.w3.org/2000/svg"
                height="24"
                viewBox="0 0 24 24"
                class="navigation-navigationtoggle-close"
              >
                <path
                  d="M18 6L6 18M6 6l12 12"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path>
              </svg>
            </span>
          </button>
        </div>
      </div>
      <div id="navigationMobile" class="navigation__mobile">
        <div class="navigation__mobile-content">
          <div class="navigation__mobile-links">
            <a href="#solutions">
              <div class="navigation__mobile-link">
                <span class="navigation__mobile-link-text">AI Solutions</span>
                <span class="navigation__mobile-link-arrow">→</span>
              </div>
            </a>
            <a href="#experts">
              <div class="navigation__mobile-link">
                <span class="navigation__mobile-link-text">Find Experts</span>
                <span class="navigation__mobile-link-arrow">→</span>
              </div>
            </a>
            <a href="#categories">
              <div class="navigation__mobile-link">
                <span class="navigation__mobile-link-text">Categories</span>
                <span class="navigation__mobile-link-arrow">→</span>
              </div>
            </a>
            <a href="#how-it-works">
              <div class="navigation__mobile-link">
                <span class="navigation__mobile-link-text">How It Works</span>
                <span class="navigation__mobile-link-arrow">→</span>
              </div>
            </a>
            <a href="#about">
              <div class="navigation__mobile-link">
                <span class="navigation__mobile-link-text">About</span>
                <span class="navigation__mobile-link-arrow">→</span>
              </div>
            </a>
          </div>
          <div class="navigation__mobile-actions">
            <button class="btn-primary navigation__mobile-cta btn">
              Get Started
              <span v-html="rawbe7v"></span>
            </button>
            <a href="#login">
              <div class="navigation__mobile-login btn-outline btn">
                <span>
                  Sign In
                  <span v-html="rawwqkr"></span>
                </span>
              </div>
            </a>
          </div>
        </div>
        <div class="navigation__mobile-backdrop"></div>
      </div>
      <div class="navigation__scanline"></div>
    </nav>
  </div>
</template>

<script>
import DangerousHTML from 'dangerous-html/dist/vue/lib.js'

export default {
  name: 'Navigation',
  props: {},
  components: {
    DangerousHTML,
  },
  data() {
    return {
      rawbe7v: ' ',
      rawwqkr: ' ',
    }
  },
}
</script>

<style scoped>
.navigation-container1 {
  display: contents;
}
 
.navigation-container2 {
  display: none;
}
 
.navigation-container3 {
  display: contents;
}
 
.navigation-container4 {
  display: none;
}
 
.navigation-container5 {
  display: contents;
}
 
.navigation-navigationtoggle-icon {
  width: 24px;
  height: 24px;
  position: relative;
}
 
.navigation-navigationtoggle-menu {
  top: 0;
  left: 0;
  width: 24px;
  height: 24px;
  opacity: 1;
  position: absolute;
  transform: rotate(0deg);
  transition: all 0.3s var(--animation-curve-primary);
}
 
.navigation-navigationtoggle-close {
  top: 0;
  left: 0;
  width: 24px;
  height: 24px;
  opacity: 0;
  position: absolute;
  transform: rotate(90deg);
  transition: all 0.3s var(--animation-curve-primary);
}
</style>
