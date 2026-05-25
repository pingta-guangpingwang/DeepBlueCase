# Template Case Store

A curated repository of open-source project templates and real-world case studies, designed as reference material for AI-assisted software development.

## Purpose

When generating code with AI, having high-quality reference projects dramatically improves output accuracy and architecture quality. This repository organizes two types of references:

- **Templates** — Directly reusable project scaffolds. Use these as starting points when bootstrapping a new project.
- **Cases** — Complete production projects. Study these for architecture patterns, component design, and best practices.

## Repository Structure

```
template-case-store/
├── README.md              # This file
├── _TEMPLATE.md           # Contribution template for new entries
├── templates/             # Reusable project scaffolds
│   ├── react-vite-admin/
│   ├── vue3-h5-mall/
│   └── uniapp-mini-tool/
├── cases/                 # Reference production projects
│   ├── dashboard-analytics/
│   ├── ecommerce-platform/
│   └── form-builder-tool/
└── .github/workflows/     # CI automation
```

## Metadata Format

Every entry follows a standard YAML frontmatter format at the top of its README.md:

```yaml
---
type: template | case
category: <project-category>
tech_stack: [list, of, technologies]
style_tags: [keywords, for, searching]
use_cases: [when, to, use, this]
score: 1-10
source_url: <real-github-repo-url>
summary: <one-line description>
---
```

## How to Use

### As an AI reference

1. **Browse** the templates or cases folders to find a project matching your needs.
2. **Copy the YAML frontmatter** and paste it into your AI prompt as context.
3. **Include the source URL** so the AI can reference the real repository's code and patterns.

### As a developer

1. **Clone the referenced source repository** to study the full codebase.
2. **Use the README** to understand what makes the project valuable.
3. **Combine multiple references** — mix a template with a case study for best results.

## Contribution Guide

1. Pick a real, popular, well-maintained open-source project from GitHub.
2. Copy `_TEMPLATE.md` to the appropriate directory (`templates/` or `cases/`).
3. Fill in all frontmatter fields with accurate information.
4. Write a clear README describing the project highlights, architecture, and how to use it as a reference.
5. Open a PR — the CI workflow will auto-label it by category.

## Current Entries

| Name | Type | Tech Stack | Score |
|------|------|------------|-------|
| react-vite-admin | template | React, Vite, Ant Design | 9 |
| vue3-h5-mall | template | Vue 3, Vant, Pinia | 8 |
| uniapp-mini-tool | template | UniApp, uView | 7 |
| dashboard-analytics | case | React, D3, Recharts | 9 |
| ecommerce-platform | case | Next.js, Prisma, Stripe | 9 |
| form-builder-tool | case | React, Formily, Ant Design | 8 |

## License

This repository itself is MIT licensed. Each referenced project retains its own license — always check the source repository before use.
