# Mickinsey Style Presets

Visual presets for the Mickinsey style, used to generate consistent and beautiful slides.

---

## Mickinsey Pure

**Use Cases:** Business reports, product launches, corporate introductions

### Color Scheme

```css
--primary: #0A2540;        /* Deep Sea Blue */
--secondary: #00D4AA;      /* Mint Green */
--background: #FFFFFF;     /* Pure White */
--text-primary: #1A1A2E;   /* Deep Black */
--text-secondary: #6B7280; /* Gray */
--accent: #635BFF;         /* Purple Accent */
```

### Font Pairing

- **Headings:** "Noto Sans SC", "PingFang SC", sans-serif
- **Body:** "Noto Sans SC", "Microsoft YaHei", sans-serif
- **Data:** "DIN Alternate", "Roboto Mono", monospace

### Layout Characteristics

- Generous whitespace (padding: 60px-120px)
- Left-aligned titles, right-aligned content
- Circular data displays
- Thin line separators

---

## Mickinsey Dark

**Use Cases:** Tech launches, creative proposals, premium roadshows

### Color Scheme

```css
--primary: #FFD700;        /* Gold */
--secondary: #00CED1;      /* Deep Cyan */
--background: #0D1117;     /* Deep Black */
--surface: #161B22;        /* Card Background */
--text-primary: #E6EDF3;   /* Bright White */
--text-secondary: #8B949E; /* Grayish White */
```

### Font Pairing

- **Headings:** "Noto Sans SC", "Source Han Sans", sans-serif
- **Body:** "Noto Sans SC", sans-serif
- **Accent:** "Playfair Display", serif (English decorative)

### Layout Characteristics

- Dark immersive background
- Gradient light effect decorations
- Card-based content organization
- Neon color accent elements

---

## Mickinsey Warm

**Use Cases:** Education & training, team sharing, informal presentations

### Color Scheme

```css
--primary: #FF6B6B;        /* Coral Red */
--secondary: #FFE66D;      /* Warm Yellow */
--background: #FFFDF8;     /* Off White */
--surface: #FFFFFF;        /* Pure White Card */
--text-primary: #2D3436;   /* Dark Gray */
--text-secondary: #636E72; /* Medium Gray */
--accent: #A29BFE;         /* Light Purple */
```

### Font Pairing

- **Headings:** "Noto Sans SC", "ZCOOL XiaoWei", serif
- **Body:** "Noto Sans SC", "Microsoft YaHei", sans-serif
- **Handwriting:** Used for quotes and decorations

### Layout Characteristics

- Rounded elements (border-radius: 16px-24px)
- Soft shadows
- Icon accents
- Rich graphics and text

---

## Animation Patterns

### Page Transitions

```css
/* Fade + Slide Up */
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Duration: 600ms */
/* Easing: cubic-bezier(0.4, 0, 0.2, 1) */
```

### Element Animations

```css
/* Staggered Fly-in */
.stagger-item {
  animation: fadeInUp 0.5s ease backwards;
}
.stagger-item:nth-child(1) { animation-delay: 0.1s; }
.stagger-item:nth-child(2) { animation-delay: 0.2s; }
.stagger-item:nth-child(3) { animation-delay: 0.3s; }
```

### Accent Animations

```css
/* Data Count Up */
@keyframes countUp {
  from { opacity: 0; transform: scale(0.5); }
  to { opacity: 1; transform: scale(1); }
}

/* Pulse Highlight */
@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(99, 91, 255, 0.4); }
  50% { box-shadow: 0 0 20px 10px rgba(99, 91, 255, 0); }
}
```

---

## Component Specifications

### Title Slide

```
┌─────────────────────────────┐
│                             │
│                             │
│     [Main Title]            │
│     H1 - 48-72px            │
│                             │
│     [Subtitle]              │
│     H2 - 24-32px            │
│                             │
│              [Speaker Info] │
│                             │
└─────────────────────────────┘
```

### Content Slide

```
┌─────────────────────────────┐
│  [Page Title]               │
│  H2 - 36px                  │
├─────────────────────────────┤
│                             │
│  ┌────────┐  ┌────────┐    │
│  │ Point 1│  │ Point 2│    │
│  └────────┘  └────────┘    │
│                             │
│  ┌────────────────────┐    │
│  │    Description     │    │
│  └────────────────────┘    │
│                             │
└─────────────────────────────┘
```

### Data Slide

```
┌─────────────────────────────┐
│  [Data Title]               │
├─────────────────────────────┤
│                             │
│     ┌───┐                   │
│     │   │   Metric 1        │
│     │   │   98%             │
│     └───┘                   │
│                             │
│  ┌───┐ ┌───┐ ┌───┐         │
│  │   │ │   │ │   │         │
│  └───┘ └───┘ └───┘         │
│   M2   M3   M4             │
│                             │
└─────────────────────────────┘
```
