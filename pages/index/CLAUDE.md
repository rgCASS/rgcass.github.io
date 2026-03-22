# CLAUDE.md - 实验室主页模块

[根目录](../../CLAUDE.md) > **index.html (实验室主页)**

---

## 模块职责

`index.html` 是 rgCASS 实验室网站的唯一门面页，承担以下职责：

- **品牌展示**：实验室名称、口号、定位
- **研究方向介绍**：4 个研究方向卡片（认知解码、类人智能体、社会传播模拟器、认知塑造）
- **业务合作展示**：面向公众（灵境社会 2C）和机构（课题合作 2B）
- **团队展示**：5 名核心成员简介
- **招募信息**：实习生/硕士/博士招募，邮件联系入口

---

## 入口与启动

文件路径：`/index.html`（项目根目录）

访问方式：
- 生产环境：`https://rgcass.github.io/`
- 本地预览：`python3 -m http.server 8080` 后访问 `http://localhost:8080`

---

## 页面结构（Sections）

| Section ID | 功能 | 技术要点 |
|------------|------|----------|
| `#hero` | 全屏 Hero，粒子动画背景 | Canvas API 粒子系统 |
| `#research` | 4 列研究方向卡片网格 | `.tech-bg` 点阵背景；第 3 张卡片链接到 `casevo.html` |
| `#cooperation` | 2C/2B 业务合作 | 2 列响应式网格；占位图待替换 |
| `#team` | 团队成员圆形头像 | 5 名成员；占位图待替换 |
| `#recruitment` | 招募联系区 | 邮件链接 `rgcass@cuc.edu.cn` |

---

## 对外接口（出站链接）

| 链接目标 | 说明 |
|----------|------|
| `casevo.html` | 社会传播模拟器专题页（研究方向第 3 个卡片） |
| `mailto:rgcass@cuc.edu.cn` | 招募/联系邮件 |
| `mailto:contact@agent-social-lab.org` | Footer 联系邮件（待统一） |
| `#` | Twitter / LinkedIn 占位链接（待填写真实地址） |

---

## 关键依赖与配置

```html
<!-- Tailwind CSS（CDN，无本地安装） -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Google Fonts（当前已注释，降级系统字体） -->
<!-- <link href="https://fonts.googleapis.com/...Noto+Sans+SC..."> -->
```

**CSS 变量（`:root`）**

| 变量名 | 值 | 用途 |
|--------|----|------|
| `--primary-blue` | `#0077ff` | 主色调，按钮渐变起点 |
| `--light-blue` | `#00aaff` | 辅助蓝，按钮渐变终点 |
| `--text-primary` | `#212529` | 主标题文字色 |
| `--text-secondary` | `#5a6470` | 正文文字色 |
| `--bg-off-white` | `#f8f9fa` | 页面背景色 |
| `--border-color` | `#dee2e6` | 边框 / 点阵背景色 |

---

## 数据模型

本页面无后端数据，所有内容硬编码在 HTML 中：

- **团队成员**（硬编码，5 条）：肖红江、姜泽勋、秦云霄、王晔、张靓菲
- **研究方向卡片**（硬编码，4 条）
- **合作伙伴 Logo**（占位图，4 个 placehold.co 链接，需替换）

---

## JavaScript 功能模块

### 移动端菜单（约第 322 行）
```javascript
// 汉堡按钮开合 #mobile-menu
mobileMenuButton.addEventListener('click', () => {
    mobileMenu.classList.toggle('hidden');
});
```

### Hero 粒子动画（约第 334 行）
- Canvas 全屏铺满
- 粒子数量 = 视口面积 / 11000
- 粒子间距离 < 140px 时绘制连线（蓝色渐变）
- `window.resize` 时重新计算粒子数

### 滚动淡入（约第 419 行）
- `IntersectionObserver` 监听 `.fade-in-section` 元素
- 进入视口时添加 `.is-visible` 类，触发 opacity + translateY 动画

---

## 测试与质量

**当前无自动化测试**。手工验证要点：

- [ ] 1440px / 768px / 375px 三档宽度布局正常
- [ ] 粒子动画窗口缩放后正常重绘
- [ ] 移动菜单点击任意锚点后自动关闭
- [ ] `casevo.html` 跳转链接有效

---

## 常见问题 (FAQ)

**Q: 字体看起来不是 Noto Sans SC？**
A: Google Fonts 引用已被注释（第 11 行），降级使用系统字体。取消注释即可恢复。

**Q: 团队头像如何替换？**
A: 将 `<img src="https://placehold.co/150x150/...">` 替换为真实图片路径，建议放在 `/assets/images/team/` 目录下。

**Q: 如何添加第 5 个研究方向卡片？**
A: 在 `#research` section 的 4 列网格中增加一个 `.card` div，注意同步修改 `lg:grid-cols-4` 为 `lg:grid-cols-5`（或保持 4 列换行展示）。

---

## 相关文件清单

| 文件 | 说明 |
|------|------|
| `/index.html` | 本模块全部源码（自包含，438 行） |
| `/casevo.html` | 研究方向第 3 卡片的链接目标 |

---

## 变更记录 (Changelog)

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.0 | 2026-03-22 | 初始化模块文档 |
