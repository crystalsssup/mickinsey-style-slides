# Visual Direction Presets

Three distinct design systems for the user to choose from.

---

## Option A: Editorial Bold

**Vibe:** Magazine covers, high fashion, Wired/T magazine

### Palette

```css
:root {
  --bg: #0a0a0a;
  --surface: #141414;
  --text-primary: #ffffff;
  --text-secondary: #888888;
  --accent: #ff3366;  /* Hot pink/red */
  --accent-2: #00d4aa; /* Mint contrast */
}
```

### Typography

- **Headlines:** System sans, 800 weight, tight tracking (-0.02em)
- **Body:** Same family, 400 weight, generous line-height (1.6)
- **Scale:** Headline can be 15% of viewport height

### Layout DNA

- Asymmetric grids (60/40, 70/30 splits)
- Full-bleed images with gradient overlays
- Oversized punctuation and numbers
- Generous negative space

### Signature Moves

- Text that bleeds off edges
- Diagonal section dividers
- Mixing serif (quotes) with sans-serif (body)
- High contrast photography

---

## Option B: Tech Modern

**Vibe:** Linear, Stripe, Vercel — dark mode premium SaaS

### Palette

```css
:root {
  --bg: #0d1117;
  --surface: #161b22;
  --surface-elevated: #21262d;
  --text-primary: #e6edf3;
  --text-secondary: #7d8590;
  --accent: #58a6ff;      /* Electric blue */
  --accent-glow: rgba(88, 166, 255, 0.3);
}
```

### Typography

- **Headlines:** Geometric sans, 600-700 weight
- **Code/Numbers:** Monospace for data credibility
- **Scale:** Measured, harmonious ratios

### Layout DNA

- Card-based organization
- Subtle borders (1px, low opacity)
- Glassmorphism (backdrop-blur)
- Gradients for depth

### Signature Moves

- Glowing accents on hover/focus
- Subtle grid backgrounds
- Code snippets as visual elements
- Data visualization styling

---

## Option C: Organic Warm

**Vibe:** Headspace, Notion, friendly consumer apps

### Palette

```css
:root {
  --bg: #faf9f6;        /* Warm white */
  --surface: #ffffff;
  --text-primary: #2d3436;
  --text-secondary: #636e72;
  --accent: #ff7675;    /* Coral */
  --accent-2: #74b9ff;  /* Soft blue */
  --accent-3: #00b894;  /* Mint */
}
```

### Typography

- **Headlines:** Rounded or humanist sans, 700 weight
- **Body:** Same family, 400 weight
- **Scale:** Comfortable, approachable sizing

### Layout DNA

- Rounded corners (12px-24px)
- Soft shadows (large blur, low opacity)
- Pastel gradient backgrounds
- Centered, balanced compositions

### Signature Moves

- Blob shapes as decorative elements
- Hand-drawn style icons
- Soft focus photography
- Playful micro-interactions

---

## Motion Patterns

### Entrance Choreography

```css
/* 1. Background reveals first */
@keyframes bgReveal {
  from { clip-path: inset(100% 0 0 0); }
  to { clip-path: inset(0 0 0 0); }
}

/* 2. Headline slides up */
@keyframes headlineUp {
  from { 
    opacity: 0; 
    transform: translateY(40px); 
  }
  to { 
    opacity: 1; 
    transform: translateY(0); 
  }
}

/* 3. Body content fades in */
@keyframes bodyFade {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* 4. Accent elements get attention */
@keyframes accentPulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}
```

### Scroll Behaviors

```css
/* Parallax layers */
.parallax-slow { transform: translateY(calc(var(--scroll) * 0.3)); }
.parallax-fast { transform: translateY(calc(var(--scroll) * -0.2)); }

/* Pin and reveal */
.pin-section {
  position: sticky;
  top: 0;
}
```

### Micro-interactions

```css
/* Hover states */
.interactive-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.interactive-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
}

/* Active states */
.interactive-card:active {
  transform: translateY(-2px);
}
```

---

## Layout Patterns Library

### Hero

One big statement. Headline + subhead + optional CTA.

```
┌─────────────────────────────┐
│                             │
│                             │
│     MASSIVE HEADLINE        │
│     that spans width        │
│                             │
│     Subtitle text here      │
│                             │
│              [Optional CTA] │
│                             │
└─────────────────────────────┘
```

### Three-Up

Three cards, staggered reveal.

```
┌─────────────────────────────┐
│  Title                      │
├─────────────────────────────┤
│  ┌────┐  ┌────┐  ┌────┐    │
│  │ 1  │  │ 2  │  │ 3  │    │
│  │    │  │    │  │    │    │
│  └────┘  └────┘  └────┘    │
│   0.2s   0.4s   0.6s delay │
└─────────────────────────────┘
```

### Split

Side-by-side comparison or image + text.

```
┌─────────────────────────────┐
│  ┌──────────┬──────────┐   │
│  │          │          │   │
│  │  IMAGE   │   TEXT   │   │
│  │          │          │   │
│  │          │          │   │
│  └──────────┴──────────┘   │
└─────────────────────────────┘
```

### Quote

Centered, typographic focus.

```
┌─────────────────────────────┐
│                             │
│                             │
│     "The quote text         │
│      goes here and          │
│      can be long"           │
│                             │
│     — Attribution           │
│                             │
└─────────────────────────────┘
```

### Data

Big number with context.

```
┌─────────────────────────────┐
│                             │
│          847%               │
│      growth rate            │
│                             │
│   Contextual explanation    │
│   goes here in smaller      │
│   text below                │
│                             │
└─────────────────────────────┘
```
