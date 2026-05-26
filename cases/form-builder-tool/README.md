---
id: case-form-001
name: Form Builder Tool
type: case
category: low-code-tool
tech_stack:
  - React
  - TypeScript
  - Formily
  - Ant Design
  - JSON Schema
  - Zustand
style_tags:
  - form-builder
  - low-code
  - drag-and-drop
  - schema-driven
  - dynamic-form
use_cases:
  - form-builder
  - low-code-platform
  - survey-tool
  - workflow-designer
  - dynamic-form-engine
score: 8
source_url: https://github.com/alibaba/formily
summary: 阿里巴巴 Formily 复杂场景表单解决方案，拖拽式表单构建器与 JSON Schema 驱动的表单渲染引擎，低代码 UI 构建器的理想参考。
summary_en: Drag-and-drop form builder with JSON Schema output — ideal reference for low-code UI builders and dynamic form rendering engines.
---



# Form Builder Tool

## Overview

Formily is Alibaba's enterprise-grade form solution, and its Designable component is a full drag-and-drop form builder. It handles the hardest problems in form engineering: complex field linkage, dynamic validation, cross-field dependencies, and distributed state in large forms. This is the go-to reference for any form builder or low-code designer project.

## Source Repository

- **URL:** [alibaba/formily](https://github.com/alibaba/formily)
- **Stars:** ~12k
- **License:** MIT
- **Last Active:** 2025 (actively maintained)

## Highlights

- **Architecture Pattern:** Schema-driven rendering with a three-layer architecture: Core (state engine, reactive model), React (connector layer), and Ant Design (render layer). The form builder adds a drag-and-drop designer layer on top.
- **Key Dependencies:** @formily/core (reactive form state engine), @formily/react (React bindings), @formily/antd (Ant Design field adapters), @designable/core (drag-and-drop engine), JSON Schema (config format).
- **State Management:** Custom reactive state engine with observable form fields, path-based state tracking, and batched updates. Much more sophisticated than standard form libraries — handles 200+ field forms efficiently.
- **Styling Approach:** Ant Design component library with theming. The designer uses a custom drag-and-drop canvas with a Material-like properties panel on the right.
- **Testing Strategy:** Extensive unit tests for the core reactivity engine. Integration tests for field interactions. E2E tests for the designer drag-and-drop behavior.
- **Notable Features:** JSON Schema-to-form rendering, visual form designer with drag-and-drop, real-time preview, field linkage rules (show/hide/disable based on other fields), custom component registration, field validation with async support, and form data transformation pipeline.

## How to Use as Reference

1. **Study the folder structure:** `packages/core/` for the reactive state engine, `packages/react/` for the connector layer, `packages/antd/` for UI adapters, `designable/` for the form builder (drag-and-drop designer).
2. **Key files to examine:** `packages/core/src/models/Form.ts` (form state model), `packages/core/src/models/Field.ts` (field reactive model), `designable/formily/src/` (the form designer), `packages/react/src/hooks/useField.ts` (React integration).
3. **Copy-paste patterns:** The schema-driven rendering pattern, the field-reactivity model (observe specific field paths), the custom component registry pattern, and the drag-and-drop designer canvas architecture.
4. **Combine with:** react-vite-admin (template) for the admin shell, or dashboard-analytics (case) if your form builder needs to include chart/report components.

## Code Snippets

The schema-driven rendering pattern is the most valuable takeaway:

```tsx
// Define form as JSON Schema, render declaratively
const schema: ISchema = {
  type: 'object',
  properties: {
    name: {
      type: 'string',
      title: 'Name',
      'x-decorator': 'FormItem',
      'x-component': 'Input',
      'x-validator': [{ required: true }],
    },
    age: {
      type: 'number',
      title: 'Age',
      'x-component': 'NumberPicker',
      'x-reactions': {
        dependencies: ['name'],
        fulfill: {
          state: { visible: '{{$deps[0] !== undefined}}' },
        },
      },
    },
  },
};

// SchemaField auto-renders the whole form
<SchemaField schema={schema} />
```

## Notes

Formily is a deep library with a learning curve. Start by understanding the core concepts: Form state model, Field reactivity, and the Schema protocol. The designer (Designable) is the visual form builder — study it for drag-and-drop UI patterns. The core engine can be used independently of the designer for complex forms that need advanced field linkage without a visual builder.
