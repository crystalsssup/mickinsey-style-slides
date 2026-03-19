# Mickinsy Style Presets

Mickinsy 风格的视觉预设，用于生成统一美观的幻灯片。

---

## Mickinsy Pure

**适用场景：** 商务汇报、产品发布、企业介绍

### 配色方案

```css
--primary: #0A2540;        /* 深海蓝 */
--secondary: #00D4AA;      /* 薄荷绿 */
--background: #FFFFFF;     /* 纯白 */
--text-primary: #1A1A2E;   /* 深黑 */
--text-secondary: #6B7280; /* 灰色 */
--accent: #635BFF;         /* 紫色点缀 */
```

### 字体搭配

- **标题：** "Noto Sans SC", "PingFang SC", sans-serif
- **正文：** "Noto Sans SC", "Microsoft YaHei", sans-serif
- **数据：** "DIN Alternate", "Roboto Mono", monospace

### 布局特征

- 大量留白（padding: 60px-120px）
- 左侧标题，右侧内容
- 圆形数据展示
- 细线分隔

---

## Mickinsy Dark

**适用场景：** 科技发布、创意提案、高端路演

### 配色方案

```css
--primary: #FFD700;        /* 金色 */
--secondary: #00CED1;      /* 深青 */
--background: #0D1117;     /* 深黑 */
--surface: #161B22;        /* 卡片背景 */
--text-primary: #E6EDF3;   /* 亮白 */
--text-secondary: #8B949E; /* 灰白 */
```

### 字体搭配

- **标题：** "Noto Sans SC", "Source Han Sans", sans-serif
- **正文：** "Noto Sans SC", sans-serif
- **强调：** "Playfair Display", serif（英文装饰）

### 布局特征

- 深色沉浸式背景
- 渐变光效装饰
- 卡片式内容组织
- 霓虹色强调元素

---

## Mickinsy Warm

**适用场景：** 教育培训、团队分享、非正式演讲

### 配色方案

```css
--primary: #FF6B6B;        /* 珊瑚红 */
--secondary: #FFE66D;      /* 暖黄 */
--background: #FFFDF8;     /* 米白 */
--surface: #FFFFFF;        /* 纯白卡片 */
--text-primary: #2D3436;   /* 深灰 */
--text-secondary: #636E72; /* 中灰 */
--accent: #A29BFE;         /* 淡紫 */
```

### 字体搭配

- **标题：** "Noto Sans SC", "ZCOOL XiaoWei", serif
- **正文：** "Noto Sans SC", "Microsoft YaHei", sans-serif
- **手写体：** 用于引用和装饰

### 布局特征

- 圆角元素（border-radius: 16px-24px）
- 柔和阴影
- 图标点缀
- 图文并茂

---

## 动画模式

### 页面过渡

```css
/* 淡入 + 上滑 */
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

/* 持续时间：600ms */
/* 缓动函数：cubic-bezier(0.4, 0, 0.2, 1) */
```

### 元素动画

```css
/* 依次飞入 */
.stagger-item {
  animation: fadeInUp 0.5s ease backwards;
}
.stagger-item:nth-child(1) { animation-delay: 0.1s; }
.stagger-item:nth-child(2) { animation-delay: 0.2s; }
.stagger-item:nth-child(3) { animation-delay: 0.3s; }
```

### 强调动画

```css
/* 数据增长 */
@keyframes countUp {
  from { opacity: 0; transform: scale(0.5); }
  to { opacity: 1; transform: scale(1); }
}

/* 脉冲高亮 */
@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(99, 91, 255, 0.4); }
  50% { box-shadow: 0 0 20px 10px rgba(99, 91, 255, 0); }
}
```

---

## 组件规范

### 标题页

```
┌─────────────────────────────┐
│                             │
│                             │
│     [主标题]                │
│     H1 - 48-72px            │
│                             │
│     [副标题]                │
│     H2 - 24-32px            │
│                             │
│              [演讲者信息]   │
│                             │
└─────────────────────────────┘
```

### 内容页

```
┌─────────────────────────────┐
│  [页面标题]                 │
│  H2 - 36px                  │
├─────────────────────────────┤
│                             │
│  ┌────────┐  ┌────────┐    │
│  │ 要点 1 │  │ 要点 2 │    │
│  └────────┘  └────────┘    │
│                             │
│  ┌────────────────────┐    │
│  │    详细说明        │    │
│  └────────────────────┘    │
│                             │
└─────────────────────────────┘
```

### 数据展示页

```
┌─────────────────────────────┐
│  [数据标题]                 │
├─────────────────────────────┤
│                             │
│     ┌───┐                   │
│     │   │   指标 1          │
│     │   │   98%             │
│     └───┘                   │
│                             │
│  ┌───┐ ┌───┐ ┌───┐         │
│  │   │ │   │ │   │         │
│  └───┘ └───┘ └───┘         │
│   指标2  指标3  指标4       │
│                             │
└─────────────────────────────┘
```
