---
id: template-mini-001
name: UniApp Mini Tool
type: template
category: mobile-app
tech_stack: [UniApp, Vue 3, uView UI, SCSS, WeChat Mini-Program, H5]
style_tags: [cross-platform, mini-program, H5, toolkit, mobile]
use_cases: [mini-program, cross-platform-app, utility-tool, rapid-prototyping, mobile-app]
score: 7
source_url: https://github.com/YanxinNet/uView
summary: >-
  Cross-platform UniApp scaffold with uView UI library. Build once and deploy
  to WeChat mini-programs, H5, iOS, and Android from a single codebase.
---

# UniApp Mini Tool

## Overview

uView is the most popular UI framework for UniApp, providing a rich set of cross-platform components and utilities. This entry references the uView ecosystem as a template for building UniApp-based tools and mini-programs that run on WeChat, Alipay, H5, iOS, and Android.

## Source Repository

- **URL:** [YanxinNet/uView](https://github.com/YanxinNet/uView)
- **Stars:** ~8k
- **License:** MIT
- **Last Active:** 2024

## Highlights

- **Architecture Pattern:** UniApp's pages-based structure with platform-conditional compilation (`#ifdef` directives). Components and utilities in `components/` and `uni_modules/`.
- **Key Dependencies:** uView UI (component library), Vue 3 (framework), UniApp (cross-platform engine), SCSS (styling).
- **State Management:** Vue 3 reactive system with `provide/inject` and Pinia for global state. Each page manages its own local state.
- **Styling Approach:** uView's SCSS variable system with easy theme customization. Responsive using rpx units that scale across all device widths.
- **Testing Strategy:** Primarily manual testing across platforms. HBuilderX provides built-in simulator for each target platform.
- **Notable Features:** 60+ cross-platform components (form, navigation, feedback, display), easy theme customization, platform-conditional code blocks, built-in utilities for date, storage, and HTTP.

## How to Use as Reference

1. **Study the folder structure:** `pages/` for page components, `components/` for reusable UI, `uni_modules/` for pluggable modules, `common/` for utilities and API.
2. **Key files to examine:** `pages.json` (route + tabBar config), `manifest.json` (app config), `App.vue` (app lifecycle), `uni.scss` (theme variables).
3. **Copy-paste patterns:** The platform-conditional component pattern, uni.request wrapper with interceptor, upload-file workflow with progress, and the navigation-bar customization.
4. **Combine with:** vue3-h5-mall (template) if building a mini-program storefront with UniApp.

## Code Snippets

Platform-conditional compilation is uniquely valuable for AI generation:

```vue
<template>
  <!-- #ifdef MP-WEIXIN -->
  <button open-type="getUserInfo" @getuserinfo="onLogin">WeChat Login</button>
  <!-- #endif -->
  <!-- #ifdef H5 -->
  <button @click="onH5Login">Phone Login</button>
  <!-- #endif -->
</template>
```

## Notes

UniApp has a learning curve for its platform-specific APIs and conditional compilation syntax. Use the official UniApp docs alongside this template for best results. HBuilderX IDE is recommended for development but the CLI (`@dcloudio/uni-cli`) works with VS Code as well.
