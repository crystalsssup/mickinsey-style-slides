# SlideCraft HTML Architecture

How the generated HTML is structured.

---

## Document Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ presentation_title }}</title>
  
  <!-- Critical CSS inlined for speed -->
  <style>
    /* Design tokens */
    :root {
      /* Populated from chosen visual direction */
    }
    
    /* Reset and base */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html, body { 
      height: 100%; 
      overflow: hidden;
      font-family: var(--font-body);
      background: var(--bg);
      color: var(--text-primary);
    }
    
    /* Slide system */
    .deck {
      height: 100vh;
      overflow-y: scroll;
      scroll-snap-type: y mandatory;
      scroll-behavior: smooth;
    }
    
    .slide {
      height: 100vh;
      width: 100vw;
      scroll-snap-align: start;
      display: grid;
      position: relative;
      overflow: hidden;
    }
    
    /* Layout variants */
    .slide[data-layout="hero"] { place-items: center; text-align: center; }
    .slide[data-layout="split"] { grid-template-columns: 1fr 1fr; }
    .slide[data-layout="three-up"] { grid-template-rows: auto 1fr; }
    /* etc */
  </style>
</head>
<body>
  <main class="deck">
    
    <section class="slide" data-layout="hero" id="slide-1">
      <div class="slide-content">
        <!-- Content here -->
      </div>
    </section>
    
    <!-- More slides... -->
    
  </main>
  
  <!-- Navigation overlay -->
  <nav class="deck-nav">
    <span class="progress">1 / 10</span>
  </nav>
  
  <script>
    // Navigation logic
    // Animation triggers
    // Keyboard handling
  </script>
</body>
</html>
```

---

## CSS Architecture

### Design Tokens

```css
:root {
  /* Colors (from selected preset) */
  --bg: #0a0a0a;
  --surface: #141414;
  --text-primary: #ffffff;
  --text-secondary: #888888;
  --accent: #ff3366;
  
  /* Typography */
  --font-heading: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-body: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-mono: "SF Mono", Monaco, monospace;
  
  /* Spacing */
  --space-xs: 0.5rem;
  --space-sm: 1rem;
  --space-md: 2rem;
  --space-lg: 4rem;
  --space-xl: 8rem;
  
  /* Motion */
  --duration-fast: 0.3s;
  --duration-normal: 0.6s;
  --duration-slow: 1s;
  --easing: cubic-bezier(0.4, 0, 0.2, 1);
}
```

### Slide Layouts

```css
/* Base slide */
.slide {
  padding: var(--space-lg);
}

/* Hero - centered, big type */
.slide[data-layout="hero"] {
  place-items: center;
  text-align: center;
}
.slide[data-layout="hero"] h1 {
  font-size: clamp(3rem, 8vw, 8rem);
  line-height: 1;
  font-weight: 800;
}

/* Split - two columns */
.slide[data-layout="split"] {
  grid-template-columns: 1fr 1fr;
  gap: var(--space-lg);
}
@media (max-width: 768px) {
  .slide[data-layout="split"] {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr;
  }
}

/* Three-up - cards */
.slide[data-layout="three-up"] {
  grid-template-rows: auto 1fr;
}
.slide[data-layout="three-up"] .cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-md);
  align-items: start;
}

/* Quote - centered text */
.slide[data-layout="quote"] {
  place-items: center;
  padding: var(--space-xl);
}
.slide[data-layout="quote"] blockquote {
  font-size: clamp(2rem, 4vw, 4rem);
  line-height: 1.3;
  font-weight: 300;
}
```

### Animation System

```css
/* Entrance animations */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from { 
    opacity: 0; 
    transform: translateY(40px); 
  }
  to { 
    opacity: 1; 
    transform: translateY(0); 
  }
}

@keyframes scaleIn {
  from { 
    opacity: 0; 
    transform: scale(0.9); 
  }
  to { 
    opacity: 1; 
    transform: scale(1); 
  }
}

@keyframes clipReveal {
  from { clip-path: inset(100% 0 0 0); }
  to { clip-path: inset(0 0 0 0); }
}

/* Stagger utility */
.stagger-1 { animation-delay: 0.1s; }
.stagger-2 { animation-delay: 0.2s; }
.stagger-3 { animation-delay: 0.3s; }
.stagger-4 { animation-delay: 0.4s; }
.stagger-5 { animation-delay: 0.5s; }

/* Play state controlled by JS */
.animate {
  animation-fill-mode: backwards;
  animation-duration: var(--duration-normal);
  animation-timing-function: var(--easing);
}
.animate.when-visible {
  animation-play-state: paused;
}
.animate.is-visible {
  animation-play-state: running;
}
```

---

## JavaScript Architecture

### Core Module

```javascript
(function() {
  'use strict';
  
  const deck = document.querySelector('.deck');
  const slides = document.querySelectorAll('.slide');
  const progress = document.querySelector('.progress');
  
  // Current slide tracking
  let currentSlide = 0;
  const totalSlides = slides.length;
  
  // Update progress indicator
  function updateProgress() {
    if (progress) {
      progress.textContent = `${currentSlide + 1} / ${totalSlides}`;
    }
  }
  
  // Intersection Observer for animations
  const observerOptions = {
    root: deck,
    threshold: 0.5
  };
  
  const slideObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        currentSlide = Array.from(slides).indexOf(entry.target);
        updateProgress();
      }
    });
  }, observerOptions);
  
  slides.forEach(slide => {
    slide.classList.add('when-visible');
    slideObserver.observe(slide);
  });
  
  // Keyboard navigation
  document.addEventListener('keydown', (e) => {
    switch(e.key) {
      case 'ArrowDown':
      case 'ArrowRight':
      case ' ':
        e.preventDefault();
        nextSlide();
        break;
      case 'ArrowUp':
      case 'ArrowLeft':
        e.preventDefault();
        prevSlide();
        break;
      case 'Home':
        e.preventDefault();
        goToSlide(0);
        break;
      case 'End':
        e.preventDefault();
        goToSlide(totalSlides - 1);
        break;
    }
  });
  
  function nextSlide() {
    if (currentSlide < totalSlides - 1) {
      slides[currentSlide + 1].scrollIntoView({ behavior: 'smooth' });
    }
  }
  
  function prevSlide() {
    if (currentSlide > 0) {
      slides[currentSlide - 1].scrollIntoView({ behavior: 'smooth' });
    }
  }
  
  function goToSlide(index) {
    if (index >= 0 && index < totalSlides) {
      slides[index].scrollIntoView({ behavior: 'smooth' });
    }
  }
  
  // Touch/swipe support
  let touchStartY = 0;
  
  deck.addEventListener('touchstart', (e) => {
    touchStartY = e.touches[0].clientY;
  }, { passive: true });
  
  deck.addEventListener('touchend', (e) => {
    const touchEndY = e.changedTouches[0].clientY;
    const diff = touchStartY - touchEndY;
    
    if (Math.abs(diff) > 50) {
      if (diff > 0) {
        nextSlide();
      } else {
        prevSlide();
      }
    }
  }, { passive: true });
  
  // Initialize
  updateProgress();
  
})();
```

---

## Print/PDF Styles

```css
@media print {
  @page {
    size: 1920px 1080px;
    margin: 0;
  }
  
  html, body {
    height: auto;
    overflow: visible;
  }
  
  .deck {
    height: auto;
    overflow: visible;
    scroll-snap-type: none;
  }
  
  .slide {
    page-break-after: always;
    break-after: page;
    height: 1080px;
    width: 1920px;
    display: grid !important;
    opacity: 1 !important;
  }
  
  .deck-nav,
  .nav-hint {
    display: none !important;
  }
  
  /* Ensure animations are complete */
  .animate {
    animation: none !important;
    opacity: 1 !important;
    transform: none !important;
  }
}
```

---

## Speaker Notes

Optional hidden notes for presenters:

```html
<section class="slide" data-layout="hero">
  <div class="slide-content">
    <h1>Title</h1>
  </div>
  <aside class="speaker-notes">
    Don't forget to mention the Q3 numbers here.
    Pause for dramatic effect after the reveal.
  </aside>
</section>
```

```css
.speaker-notes {
  display: none;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 1rem;
  background: rgba(0,0,0,0.8);
  color: white;
  font-size: 14px;
}

/* Show in presenter mode */
body.presenter-mode .speaker-notes {
  display: block;
}
```
