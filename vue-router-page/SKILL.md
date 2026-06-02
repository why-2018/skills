---
name: vue-router-page
description: 规范 Vue Router 页面和路由配置。Use when creating pages, editing src/router/index.ts, adding route records, reading route params/query, navigation guards, nested routes, or route-driven UI.
---

# Vue Router Page

## Quick Start

添加页面或路由时：

1. 页面组件放在 `src/pages/`，文件名使用 `PascalCase.vue`。
2. 路由记录集中维护在 `src/router/index.ts`，命名保持稳定。
3. 路由路径使用 kebab-case，路由 name 使用清晰业务名。

## Route Record

优先沿用现有路由风格。新增较大页面或独立功能页时可使用懒加载：

```ts
{
  path: '/users',
  name: 'users',
  component: () => import('../pages/UserList.vue'),
}
```

## Page Component

- 默认使用 `<script setup lang="ts">`。
- 读取 query/params 时要做类型收敛，不要假设一定存在。
- 导航优先使用 `router.push({ name: 'route-name', query })`，减少硬编码路径。
- 页面需要保留筛选、分页、tab 时，可以同步到 route query。
- 不要为未实现的鉴权或权限系统提前添加复杂 guard；先确认项目已有约定。

## Guard Guidelines

- 全局 guard 只放通用逻辑，如登录态、标题、权限入口。
- 页面级加载和错误状态留在页面或 Store。
- 登录失效跳转要与 `src/api/request.ts` 的 401 处理保持一致。
- route meta 要有明确用途；不要添加没人读取的 meta 字段。
