# HTML Template Structure

HTML template specifications for Mickinsey slides.

---

## Basic Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ presentation_title }}</title>
  <style>
    /* CSS Styles */
  </style>
</head>
<body>
  <div class="presentation">
    <!-- Slide Pages -->
  </div>
  <script>
    /* JavaScript Interactions */
  </script>
</body>
</html>
```

---

## CSS Base Styles

```css
/* ===== Reset & Base ===== */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  width: 100%;
  height: 100%;
  overflow: hidden;
  font-family: "Noto Sans SC", "PingFang SC", "Microsoft YaHei", sans-serif;
}

/* ===== Presentation Container ===== */
.presentation {
  width: 100%;
  height: 100%;
  position: relative;
}

/* ===== Single Slide ===== */
.slide {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  display: none;
  padding: 60px 80px;
  overflow: hidden;
}

.slide.active {
  display: flex;
  flex-direction: column;
  animation: slideIn 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

/* ===== Animation Definitions ===== */
@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* ===== Content Components ===== */
.slide-title {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 40px;
  line-height: 1.3;
}

.slide-subtitle {
  font-size: 24px;
  font-weight: 400;
  opacity: 0.8;
  margin-bottom: 20px;
}

.content-grid {
  display: grid;
  gap: 30px;
  flex: 1;
}

.content-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 30px;
  backdrop-filter: blur(10px);
}

/* ===== Navigation Controls ===== */
.nav-hint {
  position: fixed;
  bottom: 20px;
  right: 30px;
  font-size: 14px;
  opacity: 0.5;
  z-index: 1000;
}

.page-number {
  position: fixed;
  bottom: 20px;
  left: 30px;
  font-size: 14px;
  opacity: 0.5;
  z-index: 1000;
}

/* ===== Print/PDF Export ===== */
@media print {
  .slide {
    display: flex !important;
    position: relative;
    page-break-after: always;
    break-after: page;
  }
  
  .nav-hint, .page-number {
    display: none;
  }
}
```

---

## JavaScript Interactions

```javascript
(function() {
  'use strict';
  
  // ===== Configuration =====
  const config = {
    animationDuration: 600,
    autoPlay: false,
    autoPlayInterval: 5000
  };
  
  // ===== Get Elements =====
  const slides = document.querySelectorAll('.slide');
  const totalSlides = slides.length;
  let currentSlide = 0;
  
  // ===== Navigation Functions =====
  function goToSlide(index) {
    if (index < 0 || index >= totalSlides) return;
    
    slides[currentSlide].classList.remove('active');
    slides[index].classList.add('active');
    currentSlide = index;
    updatePageNumber();
  }
  
  function nextSlide() {
    goToSlide(currentSlide + 1);
  }
  
  function prevSlide() {
    goToSlide(currentSlide - 1);
  }
  
  function updatePageNumber() {
    const pageNum = document.querySelector('.page-number');
    if (pageNum) {
      pageNum.textContent = `${currentSlide + 1} / ${totalSlides}`;
    }
  }
  
  // ===== Keyboard Controls =====
  document.addEventListener('keydown', (e) => {
    switch(e.key) {
      case 'ArrowRight':
      case 'ArrowDown':
      case ' ':
        e.preventDefault();
        nextSlide();
        break;
      case 'ArrowLeft':
      case 'ArrowUp':
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
  
  // ===== Touch Swipe Support =====
  let touchStartY = 0;
  let touchEndY = 0;
  
  document.addEventListener('touchstart', (e) => {
    touchStartY = e.changedTouches[0].screenY;
  });
  
  document.addEventListener('touchend', (e) => {
    touchEndY = e.changedTouches[0].screenY;
    handleSwipe();
  });
  
  function handleSwipe() {
    const threshold = 50;
    const diff = touchStartY - touchEndY;
    
    if (Math.abs(diff) > threshold) {
      if (diff > 0) {
        nextSlide();
      } else {
        prevSlide();
      }
    }
  }
  
  // ===== Initialization =====
  function init() {
    // Show first slide
    if (slides.length > 0) {
      slides[0].classList.add('active');
      updatePageNumber();
    }
    
    // Add navigation hint
    const hint = document.createElement('div');
    hint.className = 'nav-hint';
    hint.textContent = '← → or Space to navigate';
    document.body.appendChild(hint);
    
    const pageIndicator = document.createElement('div');
    pageIndicator.className = 'page-number';
    document.body.appendChild(pageIndicator);
    updatePageNumber();
  }
  
  // Start
  init();
  
})();
```

---

## Page Template Examples

### Cover Slide

```html
<div class="slide cover">
  <div class="cover-content">
    <h1 class="slide-title">{{ title }}</h1>
    <p class="slide-subtitle">{{ subtitle }}</p>
    <div class="speaker-info">
      <p>{{ speaker }}</p>
      <p>{{ date }}</p>
    </div>
  </div>
  <div class="cover-decoration"></div>
</div>
```

### Content Slide

```html
<div class="slide content">
  <h2 class="slide-title">{{ page_title }}</h2>
  <div class="content-grid">
    <div class="content-card">
      <h3>{{ item_title }}</h3>
      <p>{{ item_content }}</p>
    </div>
    <!-- More cards... -->
  </div>
</div>
```

### Data Slide

```html
<div class="slide data">
  <h2 class="slide-title">{{ data_title }}</h2>
  <div class="data-grid">
    <div class="data-item">
      <span class="data-number">{{ number }}</span>
      <span class="data-label">{{ label }}</span>
    </div>
    <!-- More data... -->
  </div>
</div>
```
