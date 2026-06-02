---
name: vue-pinia-store
description: 规范 Vue3 项目的 Pinia 状态管理。Use when adding Pinia, creating stores, moving shared page state, implementing auth/user/session state, caching API data, or coordinating state across routes.
---

# Vue Pinia Store

## Quick Start

使用 Pinia 前：

1. 检查 `package.json` 是否安装 `pinia`。
2. 检查 `src/main.ts` 是否 `createPinia()` 并 `.use(pinia)`。
3. Store 放在 `src/stores/useXxxStore.ts`。

## Store Pattern

优先使用 setup store：

```ts
import { computed, ref } from 'vue';
import { defineStore } from 'pinia';

export const useUserStore = defineStore('user', () => {
  const token = ref('');
  const isLoggedIn = computed(() => Boolean(token.value));

  const setToken = (nextToken: string) => {
    token.value = nextToken;
  };

  return {
    token,
    isLoggedIn,
    setToken,
  };
});
```

## What Belongs In Store

- 登录态、当前用户、权限、跨页面筛选条件、需要复用或缓存的数据。
- 多个页面共享的加载流程和业务 action。
- 不适合放在单个组件里的长期状态。

## What Stays Local

- 弹窗开关、单个表单的临时输入、单页表格 loading。
- 只在一个组件使用且无需跨路由保留的 UI 状态。
- 可以通过 `computed` 从已有 state 推导出的重复数据。

## Guidelines

- action 可以调用 `src/api/modules/` 中的接口函数，但不要直接写 axios URL。
- 异步 action 要维护清晰的 `loading` 和错误处理策略。
- Store id 使用稳定的小写业务名，如 `user`、`permission`、`orderList`。
- 持久化 token 等敏感信息时，先确认项目已有约定；不要随意散落 `localStorage` key。
- 组件中通过 store 暴露的 action 修改状态，避免直接在多个组件里改同一批字段。
