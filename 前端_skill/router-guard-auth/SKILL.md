---
name: router-guard-auth
description: 实现和维护前端登录态校验、路由守卫、Token 过期、白名单路由和跳转回源页面。Use when editing Vue Router guards, auth redirects, login route flows, token validation, route meta auth, or 401 navigation behavior.
---

# Router Guard Auth

## Quick Start

处理路由鉴权时：

1. 先查 `src/router/`、`src/stores/`、`src/api/request.ts`、登录页和已有 token 存储方式。
2. 明确公开路由、登录页、受保护路由、默认首页和无权限页。
3. 全局 guard 只处理登录态、基础权限入口、标题等通用逻辑；页面数据加载留在页面或 Store。
4. 登录失效跳转要和请求拦截器里的 401 处理保持一致，避免重复清理和重复跳转。

## Must Do

- 白名单路由必须集中定义，至少覆盖登录页、错误页和无需登录的公开页。
- 已登录用户访问登录页时，应跳转到首页或原始目标页。
- 未登录访问受保护路由时，应跳转登录页并保留来源地址。
- Token 过期或用户信息失效时，要清理本地状态、取消敏感缓存并跳转登录。
- 避免在 guard 中直接发起多个重复请求；需要拉取用户信息时要有并发保护。
- 路由 meta 字段要有明确读取方，不添加无人使用的配置。

## Verification

- 检查未登录访问受保护页、已登录访问登录页、刷新页面、Token 失效和回源跳转。
- 检查 401 请求处理与路由 guard 不会造成循环跳转。
- 修改路由或鉴权状态后运行项目约定的类型检查或构建命令。
