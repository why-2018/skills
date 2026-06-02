---
name: vue-api-module
description: 规范 Vue 项目的 Axios 二次封装和业务 API 模块。Use when creating or editing src/api/request.ts, src/api/modules/*, request interceptors, response typing, login APIs, list APIs, or BFF calls.
---

# Vue API Module

## Quick Start

创建或修改接口时：

1. 先读 `src/api/request.ts`，确认拦截器返回的数据形状。
2. 在 `src/api/modules/` 下按业务域建模块，例如 `user.ts`、`order.ts`。
3. 导出 TypeScript interface/type 和语义化函数，不要在组件里拼散落的 URL。

## Request Wrapper

- `baseURL` 使用 `import.meta.env.VITE_API_BASE_URL`。
- 请求拦截器只处理通用逻辑，如 token、公共 header、trace id。
- 响应拦截器统一处理业务错误码、HTTP 错误和登录失效。
- 业务接口函数应拿到已经解包后的数据；不要让每个页面重复判断 `code`。
- 避免保留调试 `console.log`，错误日志要有上下文。

## API Module Pattern

每个模块遵循：

```ts
import request from '../request';

export interface UserListQuery {
  page: number;
  pageSize: number;
  keyword?: string;
}

export interface UserListItem {
  id: string;
  name: string;
}

export const getUserList = (params: UserListQuery) => {
  return request.get<any, UserListItem[]>('/users', { params });
};
```

## Guidelines

- 请求参数、响应数据、枚举值都要建类型；避免把 `any` 传到页面层。
- GET 查询用 `params`，POST/PUT/PATCH 请求体用对象字面量或已命名类型。
- 删除、启停、重置密码等副作用接口要用动词清晰的函数名。
- API 模块不持有 UI 状态；loading、dialog、pagination 放在页面或 Store。
- 如果多个接口共享分页结构，提取 `PageQuery`、`PageResult<T>` 等类型到合适的公共文件。
