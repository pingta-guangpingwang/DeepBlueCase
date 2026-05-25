# DeepBlueCase · 深蓝案例坊

深蓝工坊生态 — 开源项目模板与生产级案例参考库。为 AI 辅助开发提供高质量的项目架构参考，每个条目包含真实的 GitHub 源地址、YAML 结构化元数据和实践要点分析。

## 为什么需要它

AI 生成代码时，有高质量参考项目可大幅提升架构准确度和代码质量。本仓库收录两类参考资源：

- **模板（Templates）** — 可直接使用的项目脚手架，启动新项目时的起点
- **案例（Cases）** — 完整的生产项目，用于学习架构模式、组件设计和最佳实践

## 使用方式

### 面向 AI 开发
1. 浏览 `templates/` 或 `cases/` 找到匹配你需求的项目
2. 将 YAML Frontmatter 复制粘贴到 AI 对话中作为上下文
3. AI 会根据源仓库的代码和模式生成高质量结果

### 面向开发者
1. **Clone 源仓库** 深入研究完整代码
2. **阅读 README** 了解项目亮点和架构决策
3. **组合多个参考** — 用模板搭建框架 + 用案例指导细节

## 目录结构

```
DeepBlueCase/
├── README.md
├── _TEMPLATE.md               ← 贡献模板
├── manifest.json               ← 完整索引
├── manifest.ai.json            ← AI 精简索引
├── templates/                  ← 可直接使用的项目脚手架
│   ├── react-vite-admin/       ← React + Vite + Ant Design 后台模板
│   ├── vue3-h5-mall/           ← Vue3 + Vant H5 移动商城模板
│   └── uniapp-mini-tool/       ← UniApp 跨平台小程序模板
├── cases/                      ← 生产级参考案例
│   ├── dashboard-analytics/    ← Apache Superset — 数据可视化平台
│   ├── ecommerce-platform/     ← Medusa.js — 无头电商平台
│   └── form-builder-tool/      ← Alibaba Formily — 表单搭建器
└── .github/workflows/          ← CI 自动化
```

## 文件格式规范

```yaml
---
id: case-xxx-001
name: 项目名称
type: template | case
category: 分类
tech_stack: [Next.js, TypeScript, Prisma]
style_tags: [fullstack, ecommerce]
use_cases: [场景1, 场景2]
score: 9
source_url: https://github.com/real/repo
summary: 一句话描述项目亮点
---

# 项目名称

## 概述
...

## 架构亮点
...

## 为什么值得参考
...
```

## 当前种子资源

| 名称 | 类型 | 技术栈 | 评分 |
|------|------|--------|------|
| React Vite Admin | 模板 | React, Vite, Ant Design, Redux | 9 |
| Vue3 H5 Mall | 模板 | Vue 3, Vite, Vant, Pinia | 8 |
| UniApp Mini Tool | 模板 | UniApp, Vue 3, uView | 7 |
| Dashboard Analytics | 案例 | React, D3.js, Recharts, Ant Design | 9 |
| Ecommerce Platform | 案例 | Next.js, Prisma, Stripe, tRPC | 9 |
| Form Builder Tool | 案例 | React, Formily, JSON Schema | 8 |

## 贡献指南

1. 从 GitHub 挑选一个**真实、活跃、高质量**的开源项目
2. 复制 `_TEMPLATE.md` 到对应目录（`templates/` 或 `cases/`）
3. 填写完整的 YAML Frontmatter 和分析内容
4. **提交 PR** → CI 自动按分类打标签 → 合并后 DeepBlueBuilder 更新索引

## License

本仓库内容 MIT 协议。每个引用项目保留其原始 License，使用前请检查源仓库。
