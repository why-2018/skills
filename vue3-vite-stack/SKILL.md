---
name: vue3-vite-stack
description: 为 Vue3 + Vite + TypeScript 前端项目提供实现约定。Use when editing Vue SFCs, Vite config, TypeScript frontend code, Element Plus UI, Pinia state, Vue Router pages, or project structure.
---

# Vue3 Vite Stack

## Quick Start

处理该项目的前端代码时：

1. 先查看 `package.json`、`vite.config.ts`、`tsconfig*.json`、`src/main.ts`、`src/router/index.ts` 和相关已有文件。
2. 优先沿用项目现有目录和写法；缺目录时按下面约定补齐。
3. 修改 Vue/TS/路由/API 后，优先运行 `npm run build` 验证类型和构建。

## Project Conventions

- 页面放在 `src/pages/`，可复用组件放在 `src/components/`。
- API 二次封装放在 `src/api/request.ts`，业务接口模块放在 `src/api/modules/`。
- Pinia Store 放在 `src/stores/`，命名为 `useXxxStore.ts`。
- 全局样式放在 `src/styles/`，组件样式默认使用 `scoped`。
- 没有配置路径别名时，不要假设 `@/` 可用；先检查 `vite.config.ts` 和 `tsconfig`。

## Vue SFC

- 新组件默认使用 `<script setup lang="ts">`。
- `props`、`emits`、表单模型、接口响应都要有明确类型。
- 派生数据用 `computed`，副作用用 `watch` 或生命周期钩子，避免在模板中写复杂表达式。
- 组件内只保留展示和交互逻辑；跨页面状态进入 Pinia，接口请求优先进入 API 模块或 Store action。
- 不要引入未使用变量；项目启用了 `noUnusedLocals` 和 `noUnusedParameters`。

## Dependencies

- 使用 Element Plus 或 Pinia 前，先确认依赖已安装并在 `src/main.ts` 正确注册。
- 如果依赖缺失，使用项目包管理器添加依赖，并保持改动最小。
- 不要为了单个页面引入新的大型库；优先使用 Vue、Element Plus、现有工具和浏览器 API。

## Styling

- 页面级布局优先写在页面 SFC 的 `scoped` 样式中。
- 公共变量、reset、基础工具类放在 `src/styles/`。
- Element Plus 样式定制应集中处理，避免在多个页面散落深层选择器。
