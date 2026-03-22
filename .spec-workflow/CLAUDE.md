# CLAUDE.md - .spec-workflow 规范文档工作流模块

[根目录](../../CLAUDE.md) > **.spec-workflow (规范文档工作流)**

---

## 模块职责

`.spec-workflow/` 是 AI 辅助规范文档流程的配置目录，**不影响网站运行**，仅为开发辅助工具。它提供：

- **文档模板**：结构化的需求/设计/任务/项目文档模板，供 AI 工具（如 Claude Code 的 spec-workflow MCP）使用
- **自定义覆盖**：允许项目团队通过 `user-templates/` 覆盖默认模板，无需修改原始模板

---

## 目录结构

```
.spec-workflow/
├── templates/               # 默认文档模板（只读，不应直接修改）
│   ├── requirements-template.md   # 功能需求文档模板（用户故事+验收准则）
│   ├── design-template.md         # 设计方案文档模板
│   ├── tasks-template.md          # 任务拆分清单模板
│   ├── product-template.md        # 产品愿景文档模板
│   ├── tech-template.md           # 技术选型/架构文档模板
│   └── structure-template.md      # 项目结构文档模板
└── user-templates/          # 用户自定义模板（优先级高于 templates/）
    └── README.md            # 自定义模板使用说明
```

---

## 各模板用途

| 模板文件 | 用途 | 典型使用场景 |
|----------|------|-------------|
| `requirements-template.md` | 功能需求文档，用户故事 + WHEN/THEN 验收准则 | 新功能立项前 |
| `design-template.md` | 设计方案，包含架构决策与接口设计 | 需求确认后，编码前 |
| `tasks-template.md` | 任务清单，可追踪的开发子任务 | 设计方案完成后 |
| `product-template.md` | 产品愿景与目标用户定义 | 项目初期 |
| `tech-template.md` | 技术选型说明，技术栈与架构约束 | 项目初期或技术转型时 |
| `structure-template.md` | 项目目录结构与模块划分说明 | 项目初期或重构时 |

---

## 工作流程（Spec Workflow）

```
需求 (requirements) → 设计 (design) → 任务拆分 (tasks) → 实现 → 审批
```

每个功能点（如 B004-cognitive-decoding）应在 `.spec-workflow/` 或专属目录下维护对应文档。

---

## 使用规范

### 创建自定义模板
- 将修改后的模板放入 `user-templates/` 目录
- 文件名与 `templates/` 中对应文件保持一致
- AI 工具会优先读取 `user-templates/` 中的版本

### 不要做的事
- **不要修改** `templates/` 目录下的默认模板
- 不要将此目录的文件发布到网站（已由 `.gitignore` 或 GitHub Pages 排除）

---

## 关键约束

- 本模块为纯 Markdown 文档，无代码执行
- 与 Claude Code 的 `spec-workflow` MCP Server 配合使用
- 不影响 `index.html`、`casevo.html` 等网站文件的构建或发布

---

## 相关文件清单

| 文件 | 说明 |
|------|------|
| `.spec-workflow/templates/requirements-template.md` | 需求文档默认模板 |
| `.spec-workflow/templates/design-template.md` | 设计方案默认模板 |
| `.spec-workflow/templates/tasks-template.md` | 任务清单默认模板 |
| `.spec-workflow/templates/product-template.md` | 产品文档默认模板 |
| `.spec-workflow/templates/tech-template.md` | 技术文档默认模板 |
| `.spec-workflow/templates/structure-template.md` | 结构文档默认模板 |
| `.spec-workflow/user-templates/README.md` | 自定义模板说明 |

---

## 变更记录 (Changelog)

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.0 | 2026-03-22 | 初始化模块文档 |
