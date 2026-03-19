# Mickinsey Style Slides

A Claude Code Skill that helps you create beautiful, animation-rich HTML slide presentations.

**No design experience needed, no CSS/JavaScript knowledge required.**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Claude Code](https://img.shields.io/badge/claude--code-compatible-green.svg)

---

## ✨ Features

- **🎨 Visual Style Exploration** — Can't articulate your aesthetic preferences? No problem. Generate previews and pick what you like
- **📊 PPT Conversion** — Convert existing PowerPoint files to web slides, preserving all images and content
- **🚀 Zero Dependencies** — Single HTML file with inline CSS/JS. No npm, no build tools, no frameworks
- **📱 Responsive Design** — Adapts to all screen sizes
- **🎯 Mickinsey Style** — Unique minimalist and elegant design with professional business aesthetics

---

## 🎬 Demo

> Generated slides include smooth page transitions, element animations, and interactive effects.

---

## 📦 Installation

### For Claude Code Users

Copy the skill to your Claude Code skills directory:

```bash
# Create skills directory (if it doesn't exist)
mkdir -p ~/.claude/skills

# Clone the repository
git clone https://github.com/crystalsssup/mickinsy-style-slides.git ~/.claude/skills/mickinsy-style-slides

# Install the skill
cp -r ~/.claude/skills/mickinsy-style-slides/skills/mickinsy-slides ~/.claude/skills/
```

Or download just the SKILL.md:

```bash
mkdir -p ~/.claude/skills/mickinsy-slides
curl -o ~/.claude/skills/mickinsy-slides/SKILL.md \
  https://raw.githubusercontent.com/crystalsssup/mickinsy-style-slides/main/skills/mickinsy-slides/SKILL.md
```

---

## 🎯 Usage

### Create New Presentation

```
/mickinsy-slides

> "I want to create a pitch deck for my AI startup"
```

The Skill will:
1. Ask about your content (number of slides, copy, images)
2. Understand the feeling you want to convey (professional? lively? premium?)
3. Generate 3 Mickinsey style previews for you to choose from
4. Create the complete HTML presentation
5. Open automatically in your browser

### Convert PowerPoint

```
/mickinsy-slides

> "Convert my presentation.pptx to web slides"
```

The Skill will:
1. Extract all text, images, and notes from your PPT
2. Show you the extracted content for confirmation
3. Let you choose a Mickinsey style variant
4. Generate an HTML presentation with your original assets

---

## 🎨 Built-in Styles

### Mickinsey Pure (Pure White Business)
- Pure white base, deep sea blue accents
- Best for: Business reports, product launches, corporate introductions

### Mickinsey Dark (Dark Premium)
- Dark background, gold highlights
- Best for: Tech launches, premium roadshows, creative proposals

### Mickinsey Warm (Warm & Approachable)
- Warm tones, rounded design
- Best for: Education & training, team sharing, informal presentations

---

## 🏗️ Architecture

Uses **progressive disclosure** design — the main SKILL.md is a concise workflow map, with supporting files loaded on-demand:

| File | Purpose | Loaded When |
|------|---------|-------------|
| `SKILL.md` | Core workflow and rules | Skill invocation |
| `STYLE_PRESETS.md` | Visual presets and color schemes | Style selection phase |
| `HTML_TEMPLATE.md` | HTML/CSS/JS templates | Generation phase |

This design follows the principle: "Give the agent a map, not a 1,000-page manual."

---

## 📁 Project Structure

```
mickinsy-style-slides/
├── README.md                           # Project documentation
├── .gitignore                         # Git ignore config
└── skills/
    └── mickinsy-slides/
        ├── SKILL.md                   # Skill definition (main entry)
        ├── STYLE_PRESETS.md           # Visual presets
        └── HTML_TEMPLATE.md           # HTML templates
```

---

## 💡 Design Philosophy

1. **You don't need to be a designer to make beautiful slides** — Just react to what you see
2. **Dependencies are debt** — A single HTML file will work in 10 years
3. **Code is documentation** — Detailed English comments so future-you understands every line
4. **Professional but not pretentious** — Suitable for business without over-designing

---

## ⚙️ Requirements

- Claude Code CLI
- Modern browser (Chrome, Safari, Firefox, Edge)
- (Optional) Python + python-pptx for PPT conversion

---

## 🖼️ Export Options

Generated slides support multiple export methods:

- **Open Directly** — Double-click HTML file to view in browser
- **Deploy as Website** — Upload to any static hosting (GitHub Pages, Vercel, etc.)
- **Export to PDF** — Browser Print → Save as PDF
- **Presentation Mode** — Press `F11` for fullscreen, use arrow keys or space to navigate

---

## 🤝 Contributing

Issues and PRs welcome! If you have:
- New style ideas
- Feature improvement suggestions
- Bug reports

Please reach out!

---

## 📄 License

MIT License — Use freely, modify, and share.

---

## 🙏 Credits

Created by [crystalsssup](https://github.com/crystalsssup) with Claude Code.

Inspired by the "Vibe Coding" philosophy — Building beautiful things without being a traditional software engineer.

---

## 🔗 Related Links

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview)
- [Agent Skills Standard](https://agentskills.io/)
- [Anthropic Skills Repository](https://github.com/anthropics/skills)
