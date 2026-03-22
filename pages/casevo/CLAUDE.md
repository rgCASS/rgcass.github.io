# CLAUDE.md - Casevo 专题页模块

[根目录](../../CLAUDE.md) > **casevo.html (Casevo 专题页)**

---

## 模块职责

`casevo.html` 是 Casevo 多智能体认知主体与社会演化模拟器的产品介绍专题页，承担以下职责：

- **产品定位**：向学术界与产业界展示 Casevo 工具的核心价值
- **特性展示**：系统性呈现 Casevo 的主要功能特性
- **技术原理**：阐述认知主体建模与社会演化仿真的核心原理
- **操作引导**：展示工具的标准操作流程
- **应用场景**：列举典型研究与应用场景，促进合作与推广

---

## 入口与启动

文件路径：`/casevo.html`（项目根目录）

访问方式：
- 生产环境：`https://rgcass.github.io/casevo.html`
- 本地预览：`python3 -m http.server 8080` 后访问 `http://localhost:8080/casevo.html`
- 来源入口：`index.html` 的 `#research` 区第 3 个研究方向卡片

---

## 页面结构（Sections）

| Section ID | 功能 | 技术要点 |
|------------|------|----------|
| `#hero` | 全屏产品 Hero，标题 + 副标题 + 入口按钮 | 白色背景，无 Canvas 动画 |
| `#features` | 产品特性卡片网格 | `.tech-bg` 点阵背景；多列卡片 `.card` |
| `#functions` | 功能详情区 | 白色背景，图文混排 |
| `#principles` | 技术原理区 | `.tech-bg` 点阵背景 |
| `#operation` | 操作流程区（步骤说明） | 白色背景，步骤编号样式 |
| `#important-features` | 重要特性补充 | `.tech-bg` 点阵背景，附加功能列表 |
| `#applications` | 应用场景 | 白色背景，场景卡片 |
| `#cta` | 行动号召区 | 蓝色渐变背景，联系/合作入口 |

---

## 导航结构

```
Header (fixed, light-nav)
  ├── Logo → index.html
  └── Nav Links
       ├── 特性 → #features
       ├── 功能 → #functions
       ├── 原理 → #principles
       ├── 操作 → #operation
       └── 应用 → #applications
```

---

## 对外接口（出站链接）

| 链接目标 | 说明 |
|----------|------|
| `index.html` | 返回实验室主页（导航 Logo 及 Header 返回按钮） |
| `index.html#research` | 返回主页研究方向区 |
| `mailto:rgcass@cuc.edu.cn` | CTA 区合作/联系邮件 |

---

## 关键依赖与配置

```html
<!-- Tailwind CSS（CDN，无本地安装） -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Google Fonts（当前已注释，降级系统字体） -->
<!-- <link href="https://fonts.googleapis.com/...Noto+Sans+SC..."> -->
```

**CSS 变量（`:root`）与主页一致**

| 变量名 | 值 | 用途 |
|--------|----|------|
| `--primary-blue` | `#0077ff` | 主色调 |
| `--light-blue` | `#00aaff` | 辅助蓝 |
| `--text-primary` | `#212529` | 主标题色 |
| `--text-secondary` | `#5a6470` | 正文色 |
| `--bg-light` | `#ffffff` | 白色背景区 |
| `--bg-off-white` | `#f8f9fa` | 页面底色 |
| `--border-color` | `#dee2e6` | 边框/点阵色 |

---

## JavaScript 功能模块

### 移动端菜单（文件底部 `<script>` 块）
- 汉堡按钮开合 `#mobile-menu`，逻辑与 `index.html` 相同

### 滚动淡入
- `IntersectionObserver` 监听 `.fade-in-section` 元素
- 进入视口后添加 `.is-visible` 类，触发 opacity + translateY 动画

> `casevo.html` **无** Hero Canvas 粒子动画（与 `index.html` 的主要差异）

---

## 与主页的差异对比

| 特性 | index.html | casevo.html |
|------|-----------|-------------|
| Hero 动画 | Canvas 粒子连线 | 无动画，纯文字+按钮 |
| 导航定位 | 单页锚点 | 产品功能锚点 |
| 页面用途 | 实验室门面 | 产品专题介绍 |
| 内容来源 | 主页→`casevo.html` | 独立页，返回主页 |

---

## 测试与质量

**当前无自动化测试**。手工验证要点：

- [ ] 导航返回 `index.html` 链接有效
- [ ] 所有 Section 内锚点跳转正常
- [ ] 移动菜单在各 Section 正常开合
- [ ] 1440px / 768px / 375px 三档宽度布局正常
- [ ] CTA 区邮件链接有效

---

## 相关文件清单

| 文件 | 说明 |
|------|------|
| `/casevo.html` | 本模块全部源码（自包含，约 490 行） |
| `/index.html` | 来源页面，研究方向第 3 卡片链接到此页 |

---

## 变更记录 (Changelog)

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.0 | 2026-03-22 | 初始化模块文档 |
