<template>
  <div class="home-container10">
    <app-navigation></app-navigation>
    <div class="home-container11">
      <div class="home-container12">
        <DangerousHTML
          html="<style>
          @keyframes cardFloat {0%,100% {transform: translateY(0);}
  50% {transform: translateY(-6px);}}@keyframes badgeGlow {0% {box-shadow: 0 0 4px
          color-mix(in srgb, var(--color-accent) 30%, transparent);}
  100% {box-shadow: 0 0 12px
          color-mix(in srgb, var(--color-accent) 60%, transparent);}}@keyframes aiPulse {0% {box-shadow: var(--shadow-level-2),
          0 0 16px color-mix(in srgb, var(--color-primary) 15%, transparent);}
  100% {box-shadow: var(--shadow-level-3),
          0 0 32px color-mix(in srgb, var(--color-primary) 30%, transparent);}}@keyframes suggestionGlow {0% {opacity: 0;
  transform: scale(0.95);}
  100% {opacity: 1;
  transform: scale(1);}}@keyframes stepPulse {0% {box-shadow: 0 0 8px
          color-mix(in srgb, var(--color-primary) 40%, transparent);}
  100% {box-shadow: 0 0 16px
          color-mix(in srgb, var(--color-primary) 60%, transparent);}}@keyframes badgeGlowAbout {0% {box-shadow: 0 0 4px
          color-mix(in srgb, var(--color-accent) 20%, transparent);}
  100% {box-shadow: 0 0 12px
          color-mix(in srgb, var(--color-accent) 50%, transparent);}}@keyframes trustEntrance {0% {opacity: 0;
  transform: translateY(8px);}
  100% {opacity: 1;
  transform: translateY(0);}}
          </style> "
        ></DangerousHTML>
      </div>
    </div>
    <div class="home-container13">
      <div class="home-container14">
        <DangerousHTML
          html="<style>
  #hero-section {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-2xl);
    overflow: hidden;
  }
  #problem-submission-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #smart-search-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #featured-experts-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #registration-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #how-it-works-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #about-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  #testimonials-section {
    padding: var(--section-gap) var(--spacing-2xl);
    background: var(--color-surface);
  }
  @media (max-width: 479px) {
  #hero-section, #problem-submission-section, #smart-search-section, #featured-experts-section, #registration-section, #how-it-works-section, #about-section, #testimonials-section {
    padding: var(--spacing-xl) var(--spacing-md);
  }
  }
  @media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  .hero-card {
    animation: none;
  }
  .ai-preview-card {
    animation: none;
  }
  .trust-badge, .safety-badge {
    animation: none;
  }
  .step-marker {
    animation: none;
  }
  }
  </style>"
        ></DangerousHTML>
      </div>
    </div>
    <div class="home-container15">
      <div class="home-container16">
        <DangerousHTML
          html="<script defer data-name='homepage-interactions'>
  (function(){
    // Hero search input animation
    const heroSearchInput = document.getElementById('hero-search-input')
    if (heroSearchInput) {
      heroSearchInput.addEventListener('focus', function () {
        this.parentElement.classList.add('focused')
      })
  
      heroSearchInput.addEventListener('blur', function () {
        this.parentElement.classList.remove('focused')
      })
    }
  
    // Category chip selection
    const categoryChips = document.querySelectorAll('.category-chip')
    categoryChips.forEach((chip) => {
      chip.addEventListener('click', function () {
        this.classList.toggle('active')
      })
    })
  
    // Smart search live suggestions
    const smartSearchInput = document.getElementById('smart-search-input')
    if (smartSearchInput) {
      smartSearchInput.addEventListener('input', function () {
        const suggestionChips = document.querySelectorAll('.suggestion-chip')
        suggestionChips.forEach((chip, index) => {
          chip.style.animationDelay = `${index * 0.1}s`
          chip.classList.remove('active')
        })
        if (this.value.length > 2) {
          if (suggestionChips[0]) {
            suggestionChips[0].classList.add('active')
          }
        }
      })
    }
  
    // Suggestion chip selection
    const suggestionChips = document.querySelectorAll('.suggestion-chip')
    suggestionChips.forEach((chip) => {
      chip.addEventListener('click', function () {
        suggestionChips.forEach((c) => c.classList.remove('active'))
        this.classList.add('active')
      })
    })
  
    // Role card selection with progress animation
    const roleCards = document.querySelectorAll('.role-card')
    const progressBar = document.querySelector('.progress-bar')
    roleCards.forEach((card) => {
      card.addEventListener('click', function () {
        roleCards.forEach((c) => c.setAttribute('aria-pressed', 'false'))
        this.setAttribute('aria-pressed', 'true')
  
        if (progressBar) {
          progressBar.style.width = '33%'
          setTimeout(() => {
            progressBar.style.width = '66%'
          }, 500)
          setTimeout(() => {
            progressBar.style.width = '100%'
          }, 1000)
        }
      })
    })
  
    // Parallax effect for hero cards
    const heroCards = document.querySelectorAll('.hero-card')
    let scrollOffset = 0
  
    window.addEventListener('scroll', function () {
      scrollOffset = window.pageYOffset
  
      heroCards.forEach((card, index) => {
        const offset = scrollOffset * 0.05 * (index + 1)
        card.style.transform = `translateY(${-offset}px)`
      })
    })
  
    // Expert card keyboard navigation
    const expertCards = document.querySelectorAll(
      '.expert-result-card, .expert-card'
    )
    expertCards.forEach((card) => {
      card.addEventListener('keypress', function (e) {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault()
          this.click()
        }
      })
    })
  
    // Media dropzone interaction
    const dropzone = document.querySelector('.media-dropzone')
    if (dropzone) {
      dropzone.addEventListener('dragover', function (e) {
        e.preventDefault()
        this.style.borderColor = 'var(--color-primary)'
        this.style.background =
          'color-mix(in srgb, var(--color-primary) 10%, transparent)'
      })
  
      dropzone.addEventListener('dragleave', function () {
        this.style.borderColor = ''
        this.style.background = ''
      })
  
      dropzone.addEventListener('drop', function (e) {
        e.preventDefault()
        this.style.borderColor = ''
        this.style.background = ''
      })
    }
  
    // Form validation feedback
    const problemInput = document.getElementById('problem-input')
    if (problemInput) {
      problemInput.addEventListener('input', function () {
        if (this.value.length > 10) {
          this.style.borderColor = 'var(--color-accent)'
        } else {
          this.style.borderColor = ''
        }
      })
    }
  
    // Intersection Observer for animation triggers
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -50px 0px',
    }
  
    const animateOnScroll = new IntersectionObserver(function (entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = '1'
          entry.target.style.transform = 'translateY(0)'
        }
      })
    }, observerOptions)
  
    const animatedElements = document.querySelectorAll(
      '.step-card, .testimonial-card, .metric-widget'
    )
    animatedElements.forEach((el) => {
      el.style.opacity = '0'
      el.style.transform = 'translateY(20px)'
      el.style.transition = 'opacity 0.6s ease-out, transform 0.6s ease-out'
      animateOnScroll.observe(el)
    })
  })()
  </script>"
        ></DangerousHTML>
      </div>
    </div>
    <section id="hero-section" aria-label="SolveSphere Instant Problem Solver">
      <div class="hero-container">
        <video
          src="https://videos.pexels.com/video-files/33164273/14134127_640_360_30fps.mp4"
          loop="true"
          muted="true"
          autoplay="true"
          aria-hidden="true"
          playsinline="true"
          class="hero-bg-video"
        ></video>
        <div class="hero-video-overlay"></div>
        <div class="hero-content-grid">
          <div class="hero-feature-col">
            <h1 class="hero-title">SolveSphere Instant Problem Solver</h1>
            <p class="hero-subtitle">
              Real solutions, delivered instantly. Describe your issue or search
              for a fix — powered by AI, validated by local experts.
              <span v-html="rawimj3"></span>
            </p>
            <div
              role="search"
              aria-label="Search problems"
              class="hero-search-group"
            >
              <div class="search-input-wrapper">
                <svg
                  width="24"
                  xmlns="http://www.w3.org/2000/svg"
                  height="24"
                  viewBox="0 0 24 24"
                  class="search-icon"
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
                <input
                  type="search"
                  id="hero-search-input"
                  aria-label="Search problems, experts, or services"
                  placeholder="Search problems, experts, or services..."
                  class="hero-search-input"
                />
              </div>
            </div>
            <div class="hero-cta-row">
              <button
                type="button"
                aria-label="Start solving problems with AI assistance"
                class="btn-lg btn-primary btn"
              >
                Start Solving
                <span v-html="raw22xm"></span>
              </button>
              <button
                type="button"
                aria-label="Register as Customer"
                class="btn-link btn"
              >
                Register as Customer
                <span v-html="rawci6c"></span>
              </button>
            </div>
          </div>
          <div class="hero-card-stack">
            <article
              aria-label="Quick problem submission"
              class="quick-submit-card hero-card"
            >
              <h3 class="hero-card-title">Quick Submit</h3>
              <div class="quick-submit-actions">
                <button
                  type="button"
                  aria-label="Voice input"
                  class="quick-action-btn"
                >
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
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
                        d="M9 5a3 3 0 0 1 3-3h0a3 3 0 0 1 3 3v5a3 3 0 0 1-3 3h0a3 3 0 0 1-3-3z"
                      ></path>
                      <path d="M5 10a7 7 0 0 0 14 0M8 21h8m-4-4v4"></path>
                    </g>
                  </svg>
                  <span>Voice</span>
                </button>
                <button
                  type="button"
                  aria-label="Upload photo or video"
                  class="quick-action-btn"
                >
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M12 3v12m5-7l-5-5l-5 5m14 7v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                  <span>Upload</span>
                </button>
              </div>
            </article>
            <article
              role="region"
              aria-label="Featured experts"
              aria-roledescription="carousel"
              class="featured-experts-card hero-card"
            >
              <h3 class="hero-card-title">Top Experts</h3>
              <div class="expert-mini-list">
                <div class="expert-mini-item">
                  <img
                    alt="Expert profile"
                    src="https://images.pexels.com/photos/5726705/pexels-photo-5726705.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                    class="expert-mini-thumb"
                  />
                  <div class="expert-mini-info">
                    <p class="expert-mini-name">Asha Verma</p>
                    <p class="expert-mini-meta">Electrician • 4.9</p>
                  </div>
                </div>
                <div class="expert-mini-item">
                  <img
                    alt="Expert profile"
                    src="https://images.pexels.com/photos/3825585/pexels-photo-3825585.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                    class="expert-mini-thumb"
                  />
                  <div class="expert-mini-info">
                    <p class="expert-mini-name">Rohan Mehta</p>
                    <p class="expert-mini-meta">Appliances • 4.8</p>
                  </div>
                </div>
              </div>
            </article>
            <article
              aria-label="Trust indicators"
              class="hero-card trust-badges-card"
            >
              <div class="trust-badges-row">
                <div class="trust-badge">
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
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
                  <span>Verified</span>
                </div>
                <div class="trust-badge">
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
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
                  <span>Instant AI</span>
                </div>
                <div class="trust-badge">
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
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
                  <span>5-Star Pros</span>
                </div>
              </div>
            </article>
          </div>
        </div>
      </div>
    </section>
    <section
      id="problem-submission-section"
      aria-labelledby="problem-submission-title"
    >
      <div class="problem-submission-container">
        <div class="problem-grid">
          <div class="problem-form-col">
            <h2 id="problem-submission-title" class="section-title">
              Instant Fix in Seconds
              <span v-html="rawidwm"></span>
            </h2>
            <p class="section-subtitle">
              Type or speak your problem and get an AI-crafted solution
              immediately. No wait, no jargon, just actionable steps.
              <span v-html="rawk5e6"></span>
            </p>
            <div class="form-group">
              <label for="problem-input" class="form-label">
                Describe your issue
                <span v-html="rawpdvc"></span>
              </label>
              <textarea
                id="problem-input"
                rows="4"
                placeholder="e.g., Ceiling fan not spinning, making clicking noise..."
                class="form-textarea"
              ></textarea>
            </div>
            <div class="category-chips-container">
              <p class="form-label">Select category</p>
              <div class="category-chips">
                <button type="button" class="category-chip">Appliances</button>
                <button type="button" class="category-chip">Electrical</button>
                <button type="button" class="category-chip">Plumbing</button>
                <button type="button" class="category-chip">HVAC</button>
                <button type="button" class="category-chip">Network</button>
                <button type="button" class="category-chip">Furniture</button>
              </div>
            </div>
            <div
              role="button"
              tabindex="0"
              aria-label="Upload photos or video"
              class="media-dropzone"
            >
              <svg
                width="32"
                xmlns="http://www.w3.org/2000/svg"
                height="32"
                viewBox="0 0 24 24"
              >
                <path
                  d="M12 3v12m5-7l-5-5l-5 5m14 7v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path>
              </svg>
              <p class="dropzone-text">Attach photos or short video</p>
              <p class="dropzone-helper">
                Upload images or 30s clip for visual context
                <span v-html="raws0fu"></span>
              </p>
            </div>
            <div class="form-actions">
              <button type="button" class="btn-primary btn">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
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
                      d="M9 5a3 3 0 0 1 3-3h0a3 3 0 0 1 3 3v5a3 3 0 0 1-3 3h0a3 3 0 0 1-3-3z"
                    ></path>
                    <path d="M5 10a7 7 0 0 0 14 0M8 21h8m-4-4v4"></path>
                  </g>
                </svg>
                <span>
                  Voice Input
                  <span v-html="rawelp7"></span>
                </span>
              </button>
              <button type="submit" class="btn-accent btn-lg btn">
                Get Instant Solution
                <span v-html="rawdkwz"></span>
              </button>
            </div>
          </div>
          <div class="problem-results-col">
            <article class="ai-preview-card">
              <div class="ai-preview-header">
                <div class="ai-badge">
                  <svg
                    width="20"
                    xmlns="http://www.w3.org/2000/svg"
                    height="20"
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
                  <span>AI Solution</span>
                </div>
              </div>
              <h3 class="ai-preview-title">Troubleshooting Steps</h3>
              <div class="ai-checklist">
                <div class="checklist-item">
                  <svg
                    width="18"
                    xmlns="http://www.w3.org/2000/svg"
                    height="18"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M20 6L9 17l-5-5"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                  <span>Check power supply connection</span>
                </div>
                <div class="checklist-item">
                  <svg
                    width="18"
                    xmlns="http://www.w3.org/2000/svg"
                    height="18"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M20 6L9 17l-5-5"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                  <span>Inspect circuit breaker status</span>
                </div>
                <div class="checklist-item">
                  <svg
                    width="18"
                    xmlns="http://www.w3.org/2000/svg"
                    height="18"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M20 6L9 17l-5-5"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    ></path>
                  </svg>
                  <span>Test fan speed settings</span>
                </div>
              </div>
            </article>
            <article class="quick-tips-card">
              <h3 class="card-mini-title">Quick Tips</h3>
              <p class="card-mini-text">
                Include clear photos and mention device model for faster, more
                accurate solutions.
                <span v-html="rawr420"></span>
              </p>
            </article>
            <article class="expert-snapshot-card">
              <h3 class="card-mini-title">Need Expert Help?</h3>
              <p class="card-mini-text">3 nearby experts available</p>
              <button type="button" class="btn-outline btn-sm btn">
                Book Now
              </button>
            </article>
          </div>
        </div>
      </div>
    </section>
    <section id="smart-search-section" aria-labelledby="smart-search-title">
      <div class="smart-search-container">
        <div class="search-split-grid">
          <div class="search-feature-col">
            <h2 id="smart-search-title" class="section-title">
              Search smarter. Fix faster.
              <span v-html="rawujef"></span>
            </h2>
            <p class="section-content">
              Type or speak your issue — IPS predicts solutions and nearby experts
              in real time.
              <span v-html="raw7d8p"></span>
            </p>
            <div class="search-primary-group">
              <div class="search-input-advanced">
                <svg
                  width="24"
                  xmlns="http://www.w3.org/2000/svg"
                  height="24"
                  viewBox="0 0 24 24"
                  class="search-icon"
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
                <input
                  type="search"
                  id="smart-search-input"
                  role="search"
                  aria-label="Search problems and experts"
                  placeholder="Try: Ceiling fan not spinning..."
                  aria-controls="suggestion-list"
                  aria-autocomplete="list"
                  class="search-input-field"
                />
              </div>
            </div>
            <div class="predictive-shortcuts">
              <p class="shortcuts-label">Popular searches</p>
              <div class="shortcuts-list">
                <button type="button" class="shortcut-chip">
                  Washing machine leaking
                  <span v-html="rawhlux"></span>
                </button>
                <button type="button" class="shortcut-chip">
                  Smart bulb flicker
                  <span v-html="rawxdvw"></span>
                </button>
                <button type="button" class="shortcut-chip">
                  AC not cooling
                </button>
              </div>
            </div>
            <div class="micro-actions">
              <button type="button" class="micro-action-item">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M12 3v12m5-7l-5-5l-5 5m14 7v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Upload photo</span>
              </button>
              <button type="button" class="micro-action-item">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
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
                      d="M9 5a3 3 0 0 1 3-3h0a3 3 0 0 1 3 3v5a3 3 0 0 1-3 3h0a3 3 0 0 1-3-3z"
                    ></path>
                    <path d="M5 10a7 7 0 0 0 14 0M8 21h8m-4-4v4"></path>
                  </g>
                </svg>
                <span>Voice note</span>
              </button>
            </div>
          </div>
          <div class="search-results-col">
            <div id="suggestion-list" role="listbox" class="live-suggestions-row">
              <button role="option" type="button" class="suggestion-chip">
                DIY Guides
                <span v-html="raw32rn"></span>
              </button>
              <button role="option" type="button" class="suggestion-chip">
                Nearby Experts
                <span v-html="raw95u2"></span>
              </button>
              <button role="option" type="button" class="suggestion-chip">
                Video Tutorials
                <span v-html="raw6jsi"></span>
              </button>
              <button
                role="option"
                type="button"
                aria-selected="true"
                class="active suggestion-chip"
              >
                Quick Fix
                <span v-html="raw1rpz"></span>
              </button>
            </div>
            <div class="expert-results-grid">
              <article
                role="article"
                tabindex="0"
                aria-label="Expert: Asha Verma, 2.1km away"
                class="expert-result-card"
              >
                <div class="expert-result-thumb">
                  <img
                    alt="Asha Verma"
                    src="https://images.pexels.com/photos/5726705/pexels-photo-5726705.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                  />
                  <div class="verified-badge">
                    <svg
                      width="16"
                      xmlns="http://www.w3.org/2000/svg"
                      height="16"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M20 6L9 17l-5-5"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
                <div class="expert-result-info">
                  <h3 class="expert-result-name">Asha Verma</h3>
                  <p class="expert-result-meta">Electrician • 4.9 ⭐</p>
                  <p class="expert-result-distance">2.1 km • 15 min ETA</p>
                </div>
              </article>
              <article
                role="article"
                tabindex="0"
                aria-label="Expert: Rohan Mehta, 3.4km away"
                class="expert-result-card"
              >
                <div class="expert-result-thumb">
                  <img
                    alt="Rohan Mehta"
                    src="https://images.pexels.com/photos/3825585/pexels-photo-3825585.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                  />
                  <div class="verified-badge">
                    <svg
                      width="16"
                      xmlns="http://www.w3.org/2000/svg"
                      height="16"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M20 6L9 17l-5-5"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
                <div class="expert-result-info">
                  <h3 class="expert-result-name">Rohan Mehta</h3>
                  <p class="expert-result-meta">Appliances • 4.8 ⭐</p>
                  <p class="expert-result-distance">3.4 km • 20 min ETA</p>
                </div>
              </article>
              <article
                role="article"
                tabindex="0"
                aria-label="Expert: Priya Shah, 1.8km away"
                class="expert-result-card"
              >
                <div class="expert-result-thumb">
                  <img
                    alt="Priya Shah"
                    src="https://images.pexels.com/photos/5726701/pexels-photo-5726701.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                  />
                  <div class="verified-badge">
                    <svg
                      width="16"
                      xmlns="http://www.w3.org/2000/svg"
                      height="16"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M20 6L9 17l-5-5"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
                <div class="expert-result-info">
                  <h3 class="expert-result-name">Priya Shah</h3>
                  <p class="expert-result-meta">Plumbing • 4.9 ⭐</p>
                  <p class="expert-result-distance">1.8 km • 12 min ETA</p>
                </div>
              </article>
              <article
                role="article"
                tabindex="0"
                aria-label="Expert: Vikram Singh, 2.7km away"
                class="expert-result-card"
              >
                <div class="expert-result-thumb">
                  <img
                    alt="Vikram Singh"
                    src="https://images.pexels.com/photos/5726706/pexels-photo-5726706.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                    loading="lazy"
                  />
                  <div class="verified-badge">
                    <svg
                      width="16"
                      xmlns="http://www.w3.org/2000/svg"
                      height="16"
                      viewBox="0 0 24 24"
                    >
                      <path
                        d="M20 6L9 17l-5-5"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
                <div class="expert-result-info">
                  <h3 class="expert-result-name">Vikram Singh</h3>
                  <p class="expert-result-meta">HVAC • 4.7 ⭐</p>
                  <p class="expert-result-distance">2.7 km • 18 min ETA</p>
                </div>
              </article>
            </div>
            <div class="mini-map-strip">
              <svg
                width="20"
                xmlns="http://www.w3.org/2000/svg"
                height="20"
                viewBox="0 0 24 24"
              >
                <path
                  d="M14.106 5.553a2 2 0 0 0 1.788 0l3.659-1.83A1 1 0 0 1 21 4.619v12.764a1 1 0 0 1-.553.894l-4.553 2.277a2 2 0 0 1-1.788 0l-4.212-2.106a2 2 0 0 0-1.788 0l-3.659 1.83A1 1 0 0 1 3 19.381V6.618a1 1 0 0 1 .553-.894l4.553-2.277a2 2 0 0 1 1.788 0zm.894.211v15M9 3.236v15"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path>
              </svg>
              <span>4 experts within 5km</span>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section
      id="featured-experts-section"
      aria-labelledby="featured-experts-title"
    >
      <div class="featured-experts-container">
        <div class="experts-header-row">
          <div class="experts-header-content">
            <h2 id="featured-experts-title" class="section-title">
              Featured Experts
              <span v-html="rawe4xw"></span>
            </h2>
            <p class="section-subtitle">
              Top-rated local specialists — vetted, rated, and ready to solve.
              Browse handpicked professionals with proven results.
              <span v-html="rawovbg"></span>
            </p>
          </div>
          <div class="experts-filters">
            <button type="button" aria-label="Filter experts" class="filter-btn">
              <svg
                width="20"
                xmlns="http://www.w3.org/2000/svg"
                height="20"
                viewBox="0 0 24 24"
              >
                <path
                  d="M2 5h20M6 12h12m-9 7h6"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path>
              </svg>
              <span>
                Filter
                <span v-html="rawoawd"></span>
              </span>
            </button>
          </div>
        </div>
        <div class="experts-grid">
          <article class="featured-card expert-card">
            <div class="expert-card-header">
              <div class="expert-thumb-large">
                <img
                  alt="Asha Verma"
                  src="https://images.pexels.com/photos/5726705/pexels-photo-5726705.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                  loading="lazy"
                />
              </div>
              <div class="expert-header-info">
                <p class="expert-id">EXP-00482</p>
                <h3 class="expert-name">Asha Verma</h3>
                <p class="expert-title">Senior Electrician</p>
              </div>
            </div>
            <div class="expert-metadata-row">
              <div class="metadata-item">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>4.9</span>
              </div>
              <div class="metadata-item"><span>12 yrs</span></div>
              <div class="metadata-item"><span>2.1 km</span></div>
            </div>
            <div class="expert-cta-cluster">
              <button
                type="button"
                aria-label="Book Asha Verma"
                class="btn-primary btn"
              >
                Book Now
                <span v-html="rawck9x"></span>
              </button>
              <button
                type="button"
                aria-label="View profile of Asha Verma"
                class="btn-outline btn-sm btn"
              >
                View Profile
                <span v-html="raw2i0x"></span>
              </button>
              <button
                type="button"
                aria-label="Chat with Asha Verma"
                class="btn-outline btn-sm btn"
              >
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M2.992 16.342a2 2 0 0 1 .094 1.167l-1.065 3.29a1 1 0 0 0 1.236 1.168l3.413-.998a2 2 0 0 1 1.099.092a10 10 0 1 0-4.777-4.719"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>
                  Chat
                  <span v-html="rawc1f4"></span>
                </span>
              </button>
            </div>
          </article>
          <article class="support-card expert-card">
            <div class="expert-card-header">
              <div class="expert-thumb">
                <img
                  alt="Rohan Mehta"
                  src="https://images.pexels.com/photos/3825585/pexels-photo-3825585.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                  loading="lazy"
                />
              </div>
              <div class="expert-header-info">
                <p class="expert-id">EXP-00917</p>
                <h3 class="expert-name">Rohan Mehta</h3>
                <p class="expert-title">Appliance Repair</p>
              </div>
            </div>
            <div class="expert-metadata-row">
              <div class="metadata-item">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>4.8</span>
              </div>
              <div class="metadata-item"><span>8 yrs</span></div>
              <div class="metadata-item"><span>3.4 km</span></div>
            </div>
            <div class="expert-cta-cluster">
              <button
                type="button"
                aria-label="Book Rohan Mehta"
                class="btn-primary btn-sm btn"
              >
                Book
                <span v-html="raw9e0g"></span>
              </button>
              <button
                type="button"
                aria-label="View profile of Rohan Mehta"
                class="btn-outline btn-sm btn"
              >
                View
                <span v-html="rawmv5y"></span>
              </button>
            </div>
          </article>
          <article class="support-card expert-card">
            <div class="expert-card-header">
              <div class="expert-thumb">
                <img
                  alt="Priya Shah"
                  src="https://images.pexels.com/photos/5726701/pexels-photo-5726701.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                  loading="lazy"
                />
              </div>
              <div class="expert-header-info">
                <p class="expert-id">EXP-00233</p>
                <h3 class="expert-name">Priya Shah</h3>
                <p class="expert-title">Plumbing Specialist</p>
              </div>
            </div>
            <div class="expert-metadata-row">
              <div class="metadata-item">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>4.9</span>
              </div>
              <div class="metadata-item"><span>10 yrs</span></div>
              <div class="metadata-item"><span>1.8 km</span></div>
            </div>
            <div class="expert-cta-cluster">
              <button
                type="button"
                aria-label="Book Priya Shah"
                class="btn-primary btn-sm btn"
              >
                Book
                <span v-html="raw0jp3"></span>
              </button>
              <button
                type="button"
                aria-label="View profile of Priya Shah"
                class="btn-outline btn-sm btn"
              >
                View
                <span v-html="raw5pw2"></span>
              </button>
            </div>
          </article>
        </div>
        <div class="experts-footer-cta">
          <button type="button" class="btn-lg btn-outline btn">
            See All Experts
            <span v-html="raw8owc"></span>
          </button>
        </div>
      </div>
    </section>
    <section id="registration-section" aria-labelledby="registration-title">
      <div class="registration-container">
        <div class="registration-grid">
          <div class="registration-intro-col">
            <h2 id="registration-title" class="section-title">
              Choose your path
            </h2>
            <p class="section-content">
              Get instant solutions or share your expertise. Fast, secure
              registration with role-specific dashboards.
              <span v-html="rawcjrt"></span>
            </p>
            <div class="benefits-list">
              <div class="benefit-item">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Instant OTP verification</span>
              </div>
              <div class="benefit-item">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Secure data encryption</span>
              </div>
              <div class="benefit-item">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Real-time profile activation</span>
              </div>
            </div>
          </div>
          <div class="registration-role-col">
            <div class="role-cards-wrapper">
              <article
                role="button"
                tabindex="0"
                aria-pressed="false"
                class="role-card"
              >
                <div class="role-icon">
                  <svg
                    width="32"
                    xmlns="http://www.w3.org/2000/svg"
                    height="32"
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
                        d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2M16 3.128a4 4 0 0 1 0 7.744M22 21v-2a4 4 0 0 0-3-3.87"
                      ></path>
                      <circle r="4" cx="9" cy="7"></circle>
                    </g>
                  </svg>
                </div>
                <h3 class="role-label">Customer</h3>
                <p class="role-description">
                  Get instant problem solutions and book local experts
                  <span v-html="raw4pnz"></span>
                </p>
                <button type="button" class="btn-primary btn-sm btn">
                  Sign Up
                  <span v-html="rawqc37"></span>
                </button>
              </article>
              <article
                role="button"
                tabindex="0"
                aria-pressed="false"
                class="role-card"
              >
                <div class="role-icon">
                  <svg
                    width="32"
                    xmlns="http://www.w3.org/2000/svg"
                    height="32"
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
                <h3 class="role-label">Expert</h3>
                <p class="role-description">
                  Join as a vetted professional and receive verified local
                  requests
                  <span v-html="raw9g8a"></span>
                </p>
                <button type="button" class="btn-accent btn-sm btn">
                  Join Now
                  <span v-html="rawjqu4"></span>
                </button>
              </article>
            </div>
            <div class="progress-widget">
              <div class="progress-steps">
                <div class="progress-step"><span>Verify</span></div>
                <div class="progress-step"><span>Setup</span></div>
                <div class="progress-step"><span>Go Live</span></div>
              </div>
              <div class="progress-bar-container">
                <div
                  role="progressbar"
                  aria-valuemax="100"
                  aria-valuemin="0"
                  aria-valuenow="0"
                  class="progress-bar"
                ></div>
              </div>
            </div>
          </div>
          <div class="registration-metrics-col">
            <article class="metric-widget">
              <div class="metric-value"><span>10,000+</span></div>
              <div class="metric-label"><span>Active Users</span></div>
              <div class="metric-badge">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </div>
            </article>
            <article class="metric-widget">
              <div class="metric-value"><span>2,500+</span></div>
              <div class="metric-label"><span>Verified Experts</span></div>
              <div class="metric-badge">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
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
            </article>
            <article class="metric-widget">
              <div class="metric-value"><span>98%</span></div>
              <div class="metric-label"><span>Success Rate</span></div>
              <div class="metric-badge">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <g
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  >
                    <circle r="10" cx="12" cy="12"></circle>
                    <circle r="6" cx="12" cy="12"></circle>
                    <circle r="2" cx="12" cy="12"></circle>
                  </g>
                </svg>
              </div>
            </article>
          </div>
        </div>
      </div>
    </section>
    <section id="how-it-works-section" aria-labelledby="how-it-works-title">
      <div class="how-it-works-container">
        <div class="lead-panel">
          <div class="lead-panel-content">
            <h2 id="how-it-works-title" class="section-title">
              How IPS Works — Instant, Intelligent, Local
              <span v-html="raweak0"></span>
            </h2>
            <p class="section-subtitle">
              From problem to solution in five seamless steps. Experience the
              future of service delivery.
              <span v-html="rawoaoq"></span>
            </p>
            <button
              type="button"
              aria-label="Get started with IPS"
              class="btn-primary btn"
            >
              Get Started
              <span v-html="rawjm6s"></span>
            </button>
          </div>
          <div class="lead-panel-visual">
            <img
              alt="AI Technology Interface"
              src="https://images.pexels.com/photos/3861969/pexels-photo-3861969.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
              loading="lazy"
            />
          </div>
        </div>
        <div class="steps-grid">
          <article aria-labelledby="step-1-title" class="step-card">
            <div class="step-marker"><span>1</span></div>
            <h3 id="step-1-title" class="step-title">Post Your Problem</h3>
            <p class="step-description">
              Type or speak your issue, attach photos or video, and tag a
              category. A unique Problem ID is generated instantly.
              <span v-html="rawcq5r"></span>
            </p>
          </article>
          <article aria-labelledby="step-2-title" class="emphasis-card step-card">
            <div class="ai-marker step-marker">
              <svg
                width="20"
                xmlns="http://www.w3.org/2000/svg"
                height="20"
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
            <h3 id="step-2-title" class="step-title">Instant AI Guidance</h3>
            <p class="step-description">
              Our OpenAI-powered engine provides concise, actionable
              troubleshooting steps and curated DIY resources in seconds.
              <span v-html="rawxlgu"></span>
            </p>
          </article>
          <article aria-labelledby="step-3-title" class="step-card">
            <div class="step-marker"><span>3</span></div>
            <h3 id="step-3-title" class="step-title">Connect with Experts</h3>
            <p class="step-description">
              Browse verified local experts tailored to your problem. View
              ratings, experience, and request a visit with one tap.
              <span v-html="raw3ea9"></span>
            </p>
          </article>
          <article aria-labelledby="step-4-title" class="step-card">
            <div class="step-marker"><span>4</span></div>
            <h3 id="step-4-title" class="step-title">Seamless Payment</h3>
            <p class="step-description">
              Confirm service, pay securely via Razorpay or QR, and receive
              instant booking confirmation with transaction logging.
              <span v-html="rawkj77"></span>
            </p>
          </article>
          <article aria-labelledby="step-5-title" class="reward-card step-card">
            <div class="step-marker reward-marker">
              <svg
                width="20"
                xmlns="http://www.w3.org/2000/svg"
                height="20"
                viewBox="0 0 24 24"
              >
                <g
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <rect x="3" y="8" rx="1" width="18" height="4"></rect>
                  <path
                    d="M12 8v13m7-9v7a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2v-7m2.5-4a2.5 2.5 0 0 1 0-5A4.8 8 0 0 1 12 8a4.8 8 0 0 1 4.5-5a2.5 2.5 0 0 1 0 5"
                  ></path>
                </g>
              </svg>
            </div>
            <h3 id="step-5-title" class="step-title">Earn Rewards</h3>
            <p class="step-description">
              Complete the job to earn reward points (₹100 → +5 points). Redeem on
              future bookings and rate the expert.
              <span v-html="rawjanp"></span>
            </p>
          </article>
        </div>
      </div>
    </section>
    <section id="about-section" aria-labelledby="about-title">
      <div class="about-section-container">
        <div class="about-grid">
          <div class="about-main">
            <h2 id="about-title" class="section-title">About SolveSphere IPS</h2>
            <p class="about-elevator">
              Instant Problem Solver (IPS) is a next-generation service platform
              that turns everyday problems into instant, actionable solutions.
              <span v-html="rawvssl"></span>
            </p>
            <p class="about-body">
              Engineered for speed and accuracy, IPS combines real-time AI
              guidance with a vetted local expert network so you get reliable
              fixes, DIY steps, or booked help — all within moments.
              <span v-html="rawzpij"></span>
            </p>
            <p class="about-body">
              We prioritize your safety and privacy. Experts undergo identity and
              background verification, transactions are secured with encrypted
              payments, and customer data is protected by industry-standard
              authentication and storage.
              <span v-html="rawapk1"></span>
            </p>
            <div class="safety-badges-row">
              <div class="safety-badge">
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
                      x="3"
                      y="11"
                      rx="2"
                      ry="2"
                      width="18"
                      height="11"
                    ></rect>
                    <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
                  </g>
                </svg>
                <span>Encrypted</span>
              </div>
              <div class="safety-badge">
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
                <span>Verified</span>
              </div>
              <div class="safety-badge">
                <svg
                  width="24"
                  xmlns="http://www.w3.org/2000/svg"
                  height="24"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Secure</span>
              </div>
            </div>
            <div class="about-cta-row">
              <button
                type="button"
                aria-label="Learn more about IPS"
                class="btn-primary btn"
              >
                Learn More
                <span v-html="rawoudd"></span>
              </button>
              <button type="button" class="btn-link btn">Contact Us</button>
            </div>
          </div>
          <div class="about-trust">
            <h3 class="trust-panel-title">Quick Facts</h3>
            <div class="trust-facts-list">
              <div class="trust-fact">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>AI-powered instant solutions</span>
              </div>
              <div class="trust-fact">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Verified expert network</span>
              </div>
              <div class="trust-fact">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Secure payment processing</span>
              </div>
              <div class="trust-fact">
                <svg
                  width="20"
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M20 6L9 17l-5-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
                <span>Reward points system</span>
              </div>
            </div>
            <div class="expert-micro-cards">
              <div class="micro-card">
                <img
                  alt="Verified expert"
                  src="https://images.pexels.com/photos/5726705/pexels-photo-5726705.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                  loading="lazy"
                />
                <div class="micro-card-badge">
                  <svg
                    width="14"
                    xmlns="http://www.w3.org/2000/svg"
                    height="14"
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
              </div>
              <div class="micro-card">
                <img
                  alt="Verified expert"
                  src="https://images.pexels.com/photos/3825585/pexels-photo-3825585.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                  loading="lazy"
                />
                <div class="micro-card-badge">
                  <svg
                    width="14"
                    xmlns="http://www.w3.org/2000/svg"
                    height="14"
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
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="testimonials-section" aria-labelledby="testimonials-title">
      <div class="testimonials-container">
        <h2 id="testimonials-title" class="section-title">What Our Users Say</h2>
        <p class="section-subtitle">
          Real experiences from customers and experts who trust SolveSphere
          <span v-html="rawxtaz"></span>
        </p>
        <div class="testimonials-grid">
          <article class="testimonial-card">
            <div class="testimonial-header">
              <img
                alt="Customer photo"
                src="https://images.pexels.com/photos/5726699/pexels-photo-5726699.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                loading="lazy"
                class="testimonial-avatar"
              />
              <div class="testimonial-author-info">
                <h3 class="testimonial-author">Neha Kapoor</h3>
                <p class="testimonial-role">Customer</p>
              </div>
              <div class="testimonial-rating">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </div>
            </div>
            <p class="testimonial-text">
              The AI solution was spot-on! Fixed my washing machine issue in 5
              minutes without calling anyone. When I needed professional help
              later, booking was instant.
              <span v-html="rawytng"></span>
            </p>
          </article>
          <article class="testimonial-card">
            <div class="testimonial-header">
              <img
                alt="Expert photo"
                src="https://images.pexels.com/photos/3825377/pexels-photo-3825377.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                loading="lazy"
                class="testimonial-avatar"
              />
              <div class="testimonial-author-info">
                <h3 class="testimonial-author">Rajesh Kumar</h3>
                <p class="testimonial-role">Expert - HVAC</p>
              </div>
              <div class="testimonial-rating">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </div>
            </div>
            <p class="testimonial-text">
              As an expert, IPS has transformed my business. I get qualified leads
              with problem details and customer context before I even arrive.
              Payment is seamless and instant.
              <span v-html="raw0lez"></span>
            </p>
          </article>
          <article class="testimonial-card">
            <div class="testimonial-header">
              <img
                alt="Customer photo"
                src="https://images.pexels.com/photos/5726703/pexels-photo-5726703.jpeg?auto=compress&amp;cs=tinysrgb&amp;h=650&amp;w=940"
                loading="lazy"
                class="testimonial-avatar"
              />
              <div class="testimonial-author-info">
                <h3 class="testimonial-author">Amit Patel</h3>
                <p class="testimonial-role">Customer</p>
              </div>
              <div class="testimonial-rating">
                <svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path></svg
                ><svg
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                  height="16"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.12 2.12 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.12 2.12 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.12 2.12 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.12 2.12 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.12 2.12 0 0 0 1.597-1.16z"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </div>
            </div>
            <p class="testimonial-text">
              Love the reward system! Every booking earns points that I can use
              for discounts. The platform is fast, secure, and the experts are
              highly professional.
              <span v-html="raw9oum"></span>
            </p>
          </article>
        </div>
      </div>
    </section>
    <app-footer></app-footer>
    <a href="https://play.teleporthq.io/signup">
      <div aria-label="Sign up to TeleportHQ" class="home-container25">
        <svg
          width="24"
          height="24"
          viewBox="0 0 19 21"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="home-icon239"
        >
          <path
            d="M9.1017 4.64355H2.17867C0.711684 4.64355 -0.477539 5.79975 -0.477539 7.22599V13.9567C-0.477539 15.3829 0.711684 16.5391 2.17867 16.5391H9.1017C10.5687 16.5391 11.7579 15.3829 11.7579 13.9567V7.22599C11.7579 5.79975 10.5687 4.64355 9.1017 4.64355Z"
            fill="#B23ADE"
          ></path>
          <path
            d="M10.9733 12.7878C14.4208 12.7878 17.2156 10.0706 17.2156 6.71886C17.2156 3.3671 14.4208 0.649963 10.9733 0.649963C7.52573 0.649963 4.73096 3.3671 4.73096 6.71886C4.73096 10.0706 7.52573 12.7878 10.9733 12.7878Z"
            fill="#FF5C5C"
          ></path>
          <path
            d="M17.7373 13.3654C19.1497 14.1588 19.1497 15.4634 17.7373 16.2493L10.0865 20.5387C8.67402 21.332 7.51855 20.6836 7.51855 19.0968V10.5141C7.51855 8.92916 8.67402 8.2807 10.0865 9.07221L17.7373 13.3654Z"
            fill="#2874DE"
          ></path>
        </svg>
        <span class="home-text56">Built in TeleportHQ</span>
      </div>
    </a>
  </div>
</template>

<script>
import DangerousHTML from 'dangerous-html/dist/vue/lib.js'

import AppNavigation from '../components/navigation'
import AppFooter from '../components/footer'

export default {
  name: 'Home',
  props: {},
  components: {
    AppNavigation,
    DangerousHTML,
    AppFooter,
  },
  data() {
    return {
      rawimj3: ' ',
      raw22xm: ' ',
      rawci6c: ' ',
      rawidwm: ' ',
      rawk5e6: ' ',
      rawpdvc: ' ',
      raws0fu: ' ',
      rawelp7: ' ',
      rawdkwz: ' ',
      rawr420: ' ',
      rawujef: ' ',
      raw7d8p: ' ',
      rawhlux: ' ',
      rawxdvw: ' ',
      raw32rn: ' ',
      raw95u2: ' ',
      raw6jsi: ' ',
      raw1rpz: ' ',
      rawe4xw: ' ',
      rawovbg: ' ',
      rawoawd: ' ',
      rawck9x: ' ',
      raw2i0x: ' ',
      rawc1f4: ' ',
      raw9e0g: ' ',
      rawmv5y: ' ',
      raw0jp3: ' ',
      raw5pw2: ' ',
      raw8owc: ' ',
      rawcjrt: ' ',
      raw4pnz: ' ',
      rawqc37: ' ',
      raw9g8a: ' ',
      rawjqu4: ' ',
      raweak0: ' ',
      rawoaoq: ' ',
      rawjm6s: ' ',
      rawcq5r: ' ',
      rawxlgu: ' ',
      raw3ea9: ' ',
      rawkj77: ' ',
      rawjanp: ' ',
      rawvssl: ' ',
      rawzpij: ' ',
      rawapk1: ' ',
      rawoudd: ' ',
      rawxtaz: ' ',
      rawytng: ' ',
      raw0lez: ' ',
      raw9oum: ' ',
    }
  },
  head: {
    title: 'Colossal Beneficial Deer',
    meta: [
      {
        property: 'og:title',
        content: 'Colossal Beneficial Deer',
      },
    ],
  },
}
</script>

<style scoped>
.home-container10 {
  width: 100%;
  display: block;
  min-height: 100vh;
}
 
.home-container11 {
  display: none;
}
 
.home-container12 {
  display: contents;
}
 
.home-container13 {
  display: none;
}
 
.home-container14 {
  display: contents;
}
 
.home-container15 {
  display: none;
}
 
.home-container16 {
  display: contents;
}
 
.home-container25 {
  right: 50px;
  border: 1px solid #ffffff5c;
  bottom: 30px;
  display: flex;
  z-index: 22;
  position: fixed;
  box-shadow: 5px 5px 10px 0px rgba(31, 31, 31, 0.4);
  min-height: auto;
  align-items: center;
  padding-top: 8px;
  padding-left: 12px;
  border-radius: 8px;
  padding-right: 12px;
  padding-bottom: 8px;
  backdrop-filter: blur(6px);
  background-color: rgba(41, 41, 41, 0.41);
}
 
.home-icon239 {
  width: 24px;
  margin-right: 4px;
}
 
.home-text56 {
  color: white;
  font-size: 13px;
  font-style: normal;
  font-weight: 500;
  line-height: 24px;
}
</style>
