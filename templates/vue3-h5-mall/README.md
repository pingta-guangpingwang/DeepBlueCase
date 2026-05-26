---
id: template-mall-001
name: Vue3 H5 Mall
type: template
category: ecommerce
tech_stack:
  - Vue 3
  - Vite
  - TypeScript
  - Vant UI
  - Pinia
  - Vue Router
style_tags:
  - H5
  - mobile-first
  - responsive
  - ecommerce
  - shopping
  - mini-program
use_cases:
  - mobile-mall
  - H5-store
  - mini-program
  - rapid-prototyping
  - ecommerce-app
score: 8
source_url: https://github.com/jdf2e/nutui
summary: 基于 Vue 3 + Vite + Vant UI 的完整 H5 移动端商城模板，包含商品列表、购物车、结算和用户中心等核心电商模块。
summary_en: Complete H5 mobile mall with Vue 3, Vite, and Vant UI — product listing, cart, checkout, and user center modules.
---



# Vue3 H5 Mall

## Overview

This is a production-grade H5 mobile mall (ecommerce storefront) built with Vue 3 Composition API, Vite, and Vant UI. It covers the full shopping flow from product browsing to checkout, making it an ideal reference for any mobile-first ecommerce project.

## Source Repository

- **URL:** [newbee-ltd/vue3-xin-h5](https://github.com/newbee-ltd/vue3-xin-h5)
- **Stars:** ~3k
- **License:** MIT
- **Last Active:** 2024

## Highlights

- **Architecture Pattern:** Modular Vue 3 Composition API with `<script setup>` syntax. Each business domain (home, category, cart, user) is a self-contained view module.
- **Key Dependencies:** Vant 4 (mobile UI), Pinia (state), Vue Router 4 (routing), Axios (HTTP), Vite (build).
- **State Management:** Pinia stores for cart state, user session, and address management. <script setup> composables for reusable logic like lazy-loading and page scrolling.
- **Styling Approach:** Vant's design system with CSS variables for theming. Mobile-first responsive with viewport units (vw/vh) and safe-area padding for notched devices.
- **Testing Strategy:** Manual testing focused. The code is structured to easily add Vitest + Vue Test Utils.
- **Notable Features:** Product search with history, SKU selection modal, cart with batch operations, address management, order creation flow, and toast/loading feedback states.

## How to Use as Reference

1. **Study the folder structure:** `src/views/` contains page-level components for home, category, cart, product detail, order, and user center.
2. **Key files to examine:** `src/router/index.ts` (route config), `src/store/` (Pinia stores), `src/service/` (API layer), `src/components/` (reusable UI).
3. **Copy-paste patterns:** The SKU selector component, cart state management in Pinia, and the lazy-image wrapper are excellent for reuse.
4. **Combine with:** uniapp-mini-tool (template) if you need to also build a WeChat mini-program version of the same store.

## Code Snippets

The cart store pattern showcases clean Pinia + Composition API:

```ts
// src/store/cart.ts
export const useCartStore = defineStore('cart', () => {
  const items = ref<CartItem[]>([]);
  const totalPrice = computed(() => items.value.reduce((sum, i) => sum + i.price * i.count, 0));
  function addItem(product: Product) { /* ... */ }
  return { items, totalPrice, addItem };
});
```

## Notes

This template targets H5 mobile web. For native-like mobile apps, consider pairing it with Capacitor. For WeChat mini-programs, see the uniapp-mini-tool template. The backend API is mocked — swap the base URL in `src/service/axios.ts` to connect to your own API.
