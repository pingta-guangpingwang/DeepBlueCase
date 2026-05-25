---
id: template-admin-001
name: React Vite Admin
type: template
category: admin-panel
tech_stack: [React, Vite, TypeScript, Ant Design, Redux Toolkit, React Router]
style_tags: [SPA, dark-mode, responsive, i18n, RBAC, dashboard]
use_cases: [admin-panel, dashboard, internal-tools, rapid-prototyping, enterprise-app]
score: 9
source_url: https://github.com/ant-design/ant-design-pro
summary: >-
  Production-ready enterprise admin dashboard scaffold built with React, Vite, and Ant Design.
  Provides layout, auth, routing, and theming out of the box.
---

# React Vite Admin

## Overview

Ant Design Pro is the most popular enterprise-level admin panel scaffold in the React ecosystem. It provides a complete set of layouts, authentication flows, permission management, and data-fetching patterns used by thousands of production applications across China and globally.

## Source Repository

- **URL:** [ant-design/ant-design-pro](https://github.com/ant-design/ant-design-pro)
- **Stars:** ~36k
- **License:** MIT
- **Last Active:** 2025 (actively maintained)

## Highlights

- **Architecture Pattern:** Feature-first folder structure with shared components, services, and models. Each page is a self-contained module with its own state, API calls, and components.
- **Key Dependencies:** Ant Design (UI library), Redux Toolkit (state), React Router v6 (routing), @umijs/max (framework), ahooks (utility hooks).
- **State Management:** Global state via Redux Toolkit with slices for user, settings, and notifications. Page-level state stays local with useState/useReducer.
- **Styling Approach:** Ant Design's built-in Less/CSS-in-JS theming system with dark mode support and customizable design tokens.
- **Testing Strategy:** Jest + React Testing Library for unit/integration tests. Playwright for E2E.
- **Notable Features:** RBAC permission system, i18n with dynamic locale switching, breadcrumb auto-generation, responsive sidebar, multi-tab page management, and built-in mock API server.

## How to Use as Reference

1. **Study the folder structure:** Start with `src/pages` to see how feature modules are organized. Each page typically has `components/`, `model.ts` (state), `service.ts` (API), and `index.tsx`.
2. **Key files to examine:** `config/routes.ts` (routing + permissions), `src/app.tsx` (app entry + layout), `src/models/` (Redux slices), `src/services/` (API layer).
3. **Copy-paste patterns:** The layout system (header, sidebar, footer), auth flow (login -> token -> refresh), and permission directive are all mature patterns ready for reuse.
4. **Combine with:** dashboard-analytics (case) for chart integration and real-time data patterns.

## Code Snippets

The permission-based routing pattern is one of its most valuable exports:

```tsx
// config/routes.ts — declarative route + permission config
export default [
  {
    path: '/admin',
    component: '@/layouts/BasicLayout',
    routes: [
      { path: '/admin/dashboard', component: '@/pages/dashboard' },
      { path: '/admin/users', component: '@/pages/users', access: 'canAdmin' },
    ],
  },
];
```

## Notes

This repo uses UmiJS as the build framework. If you prefer pure Vite without Umi, you can extract the layout, auth, and permission patterns and apply them to a plain Vite + React setup. The component design patterns are framework-agnostic within the React ecosystem.
