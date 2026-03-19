# Mickinsey Style Slides

一个用于 Claude Code 的 Skill，帮助你创建精美、动画丰富的 HTML 幻灯片演示文稿。

**无需设计经验，无需 CSS/JavaScript 知识。**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Claude Code](https://img.shields.io/badge/claude--code-compatible-green.svg)

---

## ✨ 功能特性

- **🎨 视觉风格探索** —— 无法描述你的审美偏好？没关系，直接生成预览供你选择
- **📊 PPT 转换** —— 将现有 PowerPoint 转换为网页幻灯片，保留所有图片和内容
- **🚀 零依赖** —— 单个 HTML 文件，内联所有 CSS/JS，无需 npm、构建工具或框架
- **📱 响应式设计** —— 自适应各种屏幕尺寸
- **🎯 Mickinsey 风格** —— 独特的极简优雅设计，专业商务风格

---

## 🎬 演示

> 生成的幻灯片包含流畅的页面过渡、元素动画和交互效果。

---

## 📦 安装

### Claude Code 用户

将 skill 复制到你的 Claude Code skills 目录：

```bash
# 创建 skills 目录（如果不存在）
mkdir -p ~/.claude/skills

# 克隆仓库
git clone https://github.com/crystalsssup/mickinsy-style-slides.git ~/.claude/skills/mickinsy-style-slides

# 安装 skill
cp -r ~/.claude/skills/mickinsy-style-slides/skills/mickinsy-slides ~/.claude/skills/
```

或者只下载 SKILL.md：

```bash
mkdir -p ~/.claude/skills/mickinsy-slides
curl -o ~/.claude/skills/mickinsy-slides/SKILL.md \
  https://raw.githubusercontent.com/crystalsssup/mickinsy-style-slides/main/skills/mickinsy-slides/SKILL.md
```

---

## 🎯 使用方法

### 创建新演示文稿

```
/mickinsy-slides

> "我想为我的创业项目创建一个路演 PPT"
```

Skill 会：
1. 询问你的内容（页数、文案、图片）
2. 了解你想传达的感觉（专业？活泼？高端？）
3. 生成 3 种 Mickinsey 风格预览供你选择
4. 创建完整的 HTML 演示文稿
5. 自动在浏览器中打开

### 转换 PowerPoint

```
/mickinsy-slides

> "把我的 presentation.pptx 转换成网页幻灯片"
```

Skill 会：
1. 提取 PPT 中的所有文字、图片和备注
2. 展示提取的内容供你确认
3. 让你选择 Mickinsey 风格变体
4. 生成包含原始素材的 HTML 演示文稿

---

## 🎨 内置风格

### Mickinsey Pure（纯白商务）
- 纯白底色，深海蓝点缀
- 适合：商务汇报、产品发布、企业介绍

### Mickinsey Dark（深色高端）
- 深色背景，金色强调
- 适合：科技发布、高端路演、创意提案

### Mickinsey Warm（暖色亲和）
- 暖色调，圆角设计
- 适合：教育培训、团队分享、非正式演讲

---

## 🏗️ 架构设计

采用**渐进式披露**设计 —— 主 SKILL.md 是简洁的工作流地图，支持文件按需加载：

| 文件 | 用途 | 加载时机 |
|------|------|----------|
| `SKILL.md` | 核心工作流程和规则 | Skill 调用时 |
| `STYLE_PRESETS.md` | 视觉预设和配色方案 | 风格选择阶段 |
| `HTML_TEMPLATE.md` | HTML/CSS/JS 模板 | 生成阶段 |

这种设计遵循"给 agent 一张地图，而非千页说明书"的原则。

---

## 📁 项目结构

```
mickinsy-style-slides/
├── README.md                           # 项目说明
├── .gitignore                         # Git 忽略配置
└── skills/
    └── mickinsy-slides/
        ├── SKILL.md                   # Skill 定义（主入口）
        ├── STYLE_PRESETS.md           # 视觉预设
        └── HTML_TEMPLATE.md           # HTML 模板
```

---

## 💡 设计理念

1. **无需设计也能做出精美幻灯片** —— 你只需要对看到的画面做出反应
2. **依赖就是债务** —— 单个 HTML 文件十年后依然可用
3. **代码即文档** —— 详细的中文注释，让未来你能看懂每一行代码
4. **专业但不做作** —— 适合商务场景，不过度设计

---

## ⚙️ 技术要求

- Claude Code CLI
- 现代浏览器（Chrome、Safari、Firefox、Edge）
- （可选）Python + python-pptx（用于 PPT 转换）

---

## 🖼️ 导出选项

生成的幻灯片支持多种导出方式：

- **直接打开** —— 双击 HTML 文件在浏览器中查看
- **部署网站** —— 上传到任意静态托管服务（GitHub Pages、Vercel 等）
- **导出 PDF** —— 浏览器打印 → 另存为 PDF
- **演示模式** —— 按 `F11` 进入全屏，使用方向键或空格切换

---

## 🤝 贡献

欢迎提交 Issue 和 PR！如果你有：
- 新的风格想法
- 功能改进建议
- Bug 报告

请随时联系！

---

## 📄 许可证

MIT License — 自由使用、修改和分享。

---

## 🙏 致谢

由 [crystalsssup](https://github.com/crystalsssup) 使用 Claude Code 创建。

灵感来源于 "Vibe Coding" 理念 —— 无需成为传统软件工程师，也能构建美好的事物。

---

## 🔗 相关链接

- [Claude Code 文档](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview)
- [Agent Skills 标准](https://agentskills.io/)
- [Anthropic Skills 仓库](https://github.com/anthropics/skills)
