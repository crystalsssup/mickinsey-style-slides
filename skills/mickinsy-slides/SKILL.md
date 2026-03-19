---
name: mickinsy-slides
description: Create professional, high-density consulting presentations in the style of top-tier strategy firms (McKinsey/BCG) blended with high-end editorial aesthetics. Features complex data visualization, strategic frameworks, and information-rich layouts.
author: crystalsssup
version: 1.0.0
---

# McKinsey-Style Consulting Decks

Generate strategy-firm quality presentations with cinematic precision. This skill crafts high-density, data-rich slide decks that mirror the analytical rigor and visual authority of top-tier consulting firms.

## What This Creates

- **Consulting-grade aesthetics** — McKinsey/BCG visual language with editorial polish
- **High information density** — Data-rich slides, not empty title pages
- **Complex visualizations** — Stacked bars, waterfall charts, 2x2 matrices, detailed tables
- **Strategic frameworks** — Battle-tested consulting frameworks presented with clarity
- **Single-file output** — One HTML, zero dependencies, print-ready

## Visual Language System

### Typography Hierarchy

```css
/* Headlines — Authority and premium feel */
font-family: 'Times New Roman', Times, Georgia, serif;
font-weight: 700;
/* Used for: Slide titles, section headers, key numbers */

/* Body & Labels — Clarity and precision */
font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
font-weight: 400, 500, 600;
/* Used for: Data labels, chart text, body copy, table content */

/* Scale Relationships */
--title: 2.25rem (36px);      /* Slide headlines */
--subtitle: 1.125rem (18px);  /* Supporting text */
--body: 0.875rem (14px);      /* Primary content */
--small: 0.75rem (12px);      /* Data labels, captions */
--tiny: 0.625rem (10px);      /* Table headers, footnotes */
```

### Color Palette

```css
:root {
  /* Primary — Deep Royal Blue */
  --royal-blue: #1e3a8a;        /* Primary charts, key metrics */
  --royal-blue-light: #3b82f6;  /* Secondary data series */
  --royal-blue-pale: #93c5fd;   /* Tertiary/background accents */
  
  /* Neutrals — Sophisticated grays */
  --black: #000000;             /* Primary text */
  --gray-800: #1f2937;          /* Headlines */
  --gray-600: #4b5563;          /* Body text */
  --gray-400: #9ca3af;          /* Labels, captions */
  --gray-200: #e5e7eb;          /* Borders, dividers */
  --gray-100: #f3f4f6;          /* Subtle backgrounds */
  --white: #ffffff;             /* Slide background */
  
  /* Semantic Colors */
  --positive: #10b981;          /* Growth, gains (subtle green) */
  --negative: #ef4444;          /* Decline, losses (subtle red) */
  --warning: #f59e0b;           /* Attention, risks */
}
```

### Grid & Spacing

```css
/* Fixed slide dimensions — 16:9 HD */
--slide-width: 1280px;
--slide-height: 720px;

/* Information-dense padding */
--padding-outer: 40px (2.5rem);   /* Slide edges */
--padding-inner: 24px (1.5rem);   /* Content areas */
--gap: 16px-24px;                  /* Between elements */

/* Hairline precision */
--border-thin: 0.5px;             /* Table borders, dividers */
--border-standard: 1px;           /* Section separators */
```

## Core Layout Patterns

### 1. Title Slide (Cover)

Structure:
- Top: Confidential label + Date
- Center: Large serif headline (2-3 lines), subtitle, divider line
- Bottom: Prepared for / Presented by + Page number

```
┌─────────────────────────────────────────────────────────┐
│  CONFIDENTIAL                      Q4 2024              │
│                                                         │
│                                                         │
│     Strategic Market Analysis                           │
│     & Growth Strategy                                   │
│     ─────────────────────                               │
│                                                         │
│     Comprehensive assessment of market dynamics...      │
│                                                         │
│                                                         │
│  Prepared for                  December 2024            │
│  Executive Team                Strategy Division        │
└─────────────────────────────────────────────────────────┘
```

### 2. Executive Summary

Structure:
- Left (65%): 3-4 insight highlights with left-border accent
- Right (35%): Key metrics at-a-glance (large numbers)

```
┌─────────────────────────────────────────────────────────┐
│  EXECUTIVE SUMMARY                              [tab]   │
├─────────────────────────────────────────────────────────┤
│  ┌─────────────────────────────┐  ┌──────────────────┐  │
│  │ ▌ Market Opportunity        │  │ $47.2B           │  │
│  │   The addressable market... │  │ TAM by 2026      │  │
│  │                             │  │ +12.3% CAGR      │  │
│  │ ▌ Competitive Position      │  │ ───────────────  │  │
│  │   Our analysis reveals...   │  │ 23%              │  │
│  │                             │  │ Premium Share    │  │
│  │ ▌ Strategic Imperatives     │  │ ───────────────  │  │
│  │   Three strategic levers... │  │ 340bps           │  │
│  └─────────────────────────────┘  │ Margin Impact    │  │
│                                   └──────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

### 3. Data Visualization Slide

Structure:
- Left/Middle (60-70%): Primary chart (stacked bar, line, or combo)
- Right (30-40%): Segment breakdown cards + key insight callout

Charts to use:
- **Stacked bar** — Market composition over time
- **Waterfall** — Revenue bridges, variance analysis
- **Line + Bar combo** — Trend with volume overlay

### 4. Competitive Matrix (2x2)

Structure:
- Left (60%): 2x2 grid with quadrants labeled
- Right (40%): Strategic implications + share evolution table

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│     ↑ Capability        ┌────────────┬────────────┐    │
│       Completeness      │  LEADERS   │VISIONARIES │    │
│                         │     ●      │     ◆      │    │
│                         │   (23%)    │   (New)    │    │
│     ────────────────────┼────────────┼────────────┤    │
│                         │SPECIALISTS │CHALLENGERS │    │
│                         │     ▲      │     ■      │    │
│                         └────────────┴────────────┘    │
│                            Market Reach →               │
└─────────────────────────────────────────────────────────┘
```

### 5. Financial Bridge (Waterfall)

Structure:
- Left (55%): Waterfall chart showing step-by-step changes
- Right (45%): Driver analysis cards (green for positive, red for negative)

Drivers to visualize:
- Volume growth
- Price/mix optimization
- New products
- Legacy decline
- Competitive pressure
- FX impact

### 6. Strategic Framework

Structure:
- 3-column grid for strategic pillars
- Each pillar: Number badge, title, 3 initiative cards, financial summary

```
┌─────────────────────────────────────────────────────────┐
│  STRATEGIC GROWTH FRAMEWORK                             │
├─────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │ ① Digital   │  │ ② Market    │  │ ③ Portfolio │     │
│  │   Excellence│  │   Expansion │  │Optimization │     │
│  │             │  │             │  │             │     │
│  │ ▪ AI-powered│  │ ▪ Geographic│  │ ▪ Mix shift │     │
│  │ ▪ Platform  │  │ ▪ SMB       │  │ ▪ Services  │     │
│  │ ▪ Automation│  │ ▪ Partners  │  │ ▪ Pricing   │     │
│  │             │  │             │  │             │     │
│  │ Inv: $12M   │  │ Inv: $8M    │  │ Inv: $3M    │     │
│  │ Rev: +$28M  │  │ Rev: +$22M  │  │ Rev: +$13M  │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
└─────────────────────────────────────────────────────────┘
```

### 7. Implementation Roadmap

Structure:
- Horizontal timeline (4 phases)
- Each phase: Dot on timeline, title, duration, key activities, investment
- Bottom: Risk mitigation section

### 8. Summary & Next Steps

Structure:
- Left (50%): 3 key takeaways with numbered badges
- Right (50%): Immediate action cards (priority + timeline)

## Data Visualization Specifications

### Chart.js Configuration

```javascript
// Global defaults for consulting aesthetic
Chart.defaults.font.family = "'Inter', sans-serif";
Chart.defaults.font.size = 11;
Chart.defaults.color = '#4b5563';

// Bar/Column Chart
{
  type: 'bar',
  data: {
    datasets: [{
      backgroundColor: ['#1e3a8a', '#3b82f6', '#93c5fd'], // Blue gradient
      barPercentage: 0.6,
      categoryPercentage: 0.8
    }]
  },
  options: {
    plugins: {
      legend: {
        position: 'bottom',
        labels: { usePointStyle: true, padding: 20 }
      },
      title: {
        font: { family: "'Times New Roman', serif", size: 14, weight: 'bold' }
      }
    },
    scales: {
      x: { grid: { display: false } },
      y: { 
        grid: { color: '#e5e7eb', drawBorder: false },
        ticks: { callback: (value) => '$' + value + 'B' }
      }
    }
  }
}

// Waterfall Chart (using bar with floating bars)
{
  type: 'bar',
  data: {
    datasets: [{
      data: [255, 42, 18, 23, -12, -8, 318],
      backgroundColor: [
        '#1e3a8a', // Base
        '#10b981', '#10b981', '#10b981', // Positive
        '#ef4444', '#ef4444', // Negative
        '#1e3a8a'  // Final
      ]
    }]
  }
}
```

### Table Specifications

```css
.data-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 11px;
}

.data-table th {
  border-bottom: 0.5px solid #e5e7eb;
  padding: 8px 12px;
  text-align: left;
  font-weight: 600;
  color: #4b5563;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 9px;
}

.data-table td {
  border-bottom: 0.5px solid #e5e7eb;
  padding: 8px 12px;
}

/* Alignment variants */
.data-table .numeric { text-align: right; font-feature-settings: 'tnum'; }
.data-table .change-positive { color: #10b981; }
.data-table .change-negative { color: #ef4444; }
```

## Content Guidelines

### Writing Style

1. **Headlines**: Action-oriented, specific, benefit-focused
   - ❌ "Market Analysis"
   - ✅ "$47B Market with 12% CAGR Through 2026"

2. **Insight Callouts**: Left border accent + bold thesis
   ```
   ▌ Market Opportunity
     The addressable market is projected to reach $47.2B by 2026, 
     growing at 12.3% CAGR. However, competitive intensity has 
     increased with 3 new entrants capturing 8% combined share.
   ```

3. **Data Labels**: Include context, not just numbers
   - ❌ "$47.2B"
   - ✅ "$47.2B TAM by 2026 (+12.3% CAGR)"

4. **Footnotes**: Small, gray, source attribution
   ```
   Source: Internal analysis, industry reports, expert interviews (n=24)
   ```

### Information Density Rules

- Minimum 3 data points per slide (excluding title slide)
- Charts must have ≥4 data series or time periods
- Tables should have ≥3 columns and ≥4 rows
- Every slide needs a "so what" insight

## Workflow

### Phase 1: Content Architecture (2-3 turns)

1. **Receive raw content** — Outline, notes, data dumps, existing PPT
2. **Identify slide types needed** — Map content to layout patterns
3. **Sequence the narrative** — Ensure logical flow (Situation → Complication → Resolution)
4. **Confirm data accuracy** — Validate key numbers and sources

### Phase 2: Design System Selection (1 turn)

Present 2-3 color scheme options:
- **Option A**: Deep Royal Blue (traditional McKinsey)
- **Option B**: Slate/Navy (modern BCG)
- **Option C**: Custom corporate colors

### Phase 3: Production (automated)

1. Build each slide following layout patterns
2. Generate Chart.js configurations
3. Apply consistent spacing and typography
4. Add navigation and keyboard controls
5. Include print/PDF CSS

### Phase 4: Refinement (optional)

- "Add sensitivity analysis to slide 5"
- "Break slide 3 into two slides — too dense"
- "Change chart type from bar to line"

## Output Format

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>{{ presentation_title }}</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Times+New Roman:wght@400;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --royal-blue: #1e3a8a;
      --slide-width: 1280px;
      --slide-height: 720px;
    }
    
    .slide {
      width: var(--slide-width);
      height: var(--slide-height);
      background: white;
      /* ... */
    }
    
    .font-serif-display {
      font-family: 'Times New Roman', Times, Georgia, serif;
    }
    
    /* Hairline borders */
    .border-hairline {
      border-width: 0.5px;
    }
  </style>
</head>
<body class="bg-gray-100">
  <!-- Navigation dots -->
  <!-- Slides 1-8+ -->
  <!-- Chart.js initialization -->
</body>
</html>
```

## Navigation & Interaction

```javascript
// Keyboard controls
Arrow Right/Down/Space → Next slide
Arrow Left/Up → Previous slide
Home → First slide
End → Last slide

// Touch swipe support
Left swipe → Next
Right swipe → Previous

// Visual indicators
- Progress dots (right side)
- Page counter (bottom center)
- Current slide highlight
```

## Print/PDF Optimization

```css
@media print {
  @page {
    size: 1280px 720px;
    margin: 0;
  }
  
  .slide {
    page-break-after: always;
    break-after: page;
    box-shadow: none;
  }
  
  .nav-dots,
  .page-indicator {
    display: none;
  }
}
```

## Example User Interactions

**Starting:**
```
/mickinsy-slides

> "Create a board presentation on our Q4 strategy review. 
>   I have the financial data and competitive analysis attached."
```

**After receiving content:**
```
"I'll build an 8-slide deck covering:
  1. Executive Summary
  2. Market Overview with growth charts
  3. Competitive positioning matrix
  4. Financial bridge analysis
  5. Strategic framework
  6. Implementation roadmap

  Which color scheme?
  A) Traditional Royal Blue
  B) Modern Slate
  C) Your corporate colors"
```

**Delivering:**
```
"Complete. Single HTML file with:
- 8 slides at 1280×720 resolution
- Interactive charts using Chart.js
- Keyboard and touch navigation
- Print-ready for PDF export

Open in browser, press F11 for fullscreen, 
arrow keys to navigate, Ctrl+P to save PDF.
"
```
