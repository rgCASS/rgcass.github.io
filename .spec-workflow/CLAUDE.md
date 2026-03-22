[根目录](../../CLAUDE.md) > **.spec-workflow**

# .spec-workflow - 规格工作流模板目录

> 本文件由 Claude Code 自动生成，记录该目录的用途、结构与使用方式。

---

## 模块职责

`.spec-workflow/` 是一个 **AI 辅助规格文档工作流** 的配置目录，与网站本身内容无关。它提供了一套结构化模板，帮助开发者在 AI 工具（如 Claude Code）辅助下，按统一格式创建需求文档、设计文档和任务清单。

该目录在 Git 中尚未被追踪（`??` 状态），属于本地工具配置。

---

## 目录结构

```
.spec-workflow/
├── templates/              # 默认文档模板（随工具版本更新）
│   ├── requirements-template.md   # 需求文档模板（用户故事 + 验收标准）
│   ├── design-template.md         # 设计文档模板（架构 + 组件接口）
│   ├── tasks-template.md          # 任务清单模板（分步实现计划）
│   ├── product-template.md        # 产品概述模板（愿景 + 目标）
│   ├── tech-template.md           # 技术栈文档模板
│   └── structure-template.md      # 项目结构规范模板
└── user-templates/         # 用户自定义模板覆盖目录（优先级高于 templates/）
    └── README.md           # 自定义模板使用说明
```

---

## 入口与启动

此目录无可执行入口，仅作为文档模板存储。AI 工具或开发者手动引用模板来创建新的规格文档。

---

## 对外接口

### 模板加载优先级

1. 首先检查 `user-templates/` 目录中是否有同名文件
2. 若存在，使用自定义版本
3. 若不存在，使用 `templates/` 中的默认版本

### 模板变量（创建文档时可替换）

| 变量 | 含义 |
|---|---|
| `{{projectName}}` | 项目名称 |
| `{{featureName}}` | 功能特性名称 |
| `{{date}}` | 当前日期 |
| `{{author}}` | 文档作者 |

---

## 各模板说明

| 模板文件 | 用途 | 核心结构 |
|---|---|---|
| `requirements-template.md` | 需求文档 | 用户故事、验收标准（WHEN/THEN/SHALL）、非功能需求 |
| `design-template.md` | 设计文档 | 架构概览、组件接口、数据模型、错误处理、测试策略，含 Mermaid 图 |
| `tasks-template.md` | 实现任务清单 | 分步骤任务，每步包含文件路径、依赖、需求引用和 AI 提示词 |
| `product-template.md` | 产品概述 | 产品目的、目标用户、核心功能、业务目标、成功指标 |
| `tech-template.md` | 技术栈文档 | 语言/框架、开发工具链、部署方式、技术决策记录 |
| `structure-template.md` | 项目结构规范 | 目录组织、命名约定、导入模式、代码规范 |

---

## 关键依赖与配置

- 无外部依赖，纯 Markdown 文档
- 需配合 Claude Code 或其他支持工作流的 AI IDE 使用

---

## 数据模型

无（纯文档模板，无数据模型）

---

## 测试与质量

模板本身无自动化测试。使用建议：

- 基于默认模板创建文档后，人工检查必填项是否完整
- 将自定义模板纳入 Git 版本控制以追踪变更

---

## 常见问题 (FAQ)

**Q：如何自定义模板？**
A：在 `user-templates/` 目录中创建与 `templates/` 同名的文件，工具将优先使用自定义版本。

**Q：此目录是否影响网站部署？**
A：不影响。GitHub Pages 仅托管 HTML/CSS/JS 文件，`.spec-workflow/` 目录内容不会被发布。

---

## 相关文件清单

- `.spec-workflow/templates/requirements-template.md`
- `.spec-workflow/templates/design-template.md`
- `.spec-workflow/templates/tasks-template.md`
- `.spec-workflow/templates/product-template.md`
- `.spec-workflow/templates/tech-template.md`
- `.spec-workflow/templates/structure-template.md`
- `.spec-workflow/user-templates/README.md`

---

## 变更记录 (Changelog)

| 日期 | 版本 | 说明 |
|---|---|---|
| 2026-03-22 | v1.0 | 初始化模块文档，由 Claude Code 自动生成 |
