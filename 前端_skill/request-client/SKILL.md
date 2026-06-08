---
name: request-client
description: 维护前端请求客户端、拦截器、鉴权 Header、超时、错误处理和响应解包。Use when creating or editing request clients, Axios instances, fetch wrappers, interceptors, token handling, API base URLs, or unified frontend error responses.
---

# Request Client

## Quick Start

处理请求封装时：

1. 先查 `src/api/`、`src/utils/`、`src/stores/`、登录模块和已有业务 API，确认当前项目使用 Axios、fetch 还是二次封装。
2. 确认环境变量命名、`baseURL`、超时时间、鉴权来源、登录失效跳转和响应数据结构。
3. 请求客户端只放通用传输逻辑；业务 URL、请求参数、loading 和页面提示放到业务 API 或页面层。
4. 修改拦截器后检查所有调用方拿到的是原始响应、解包数据还是分页结构，避免破坏已有 API 契约。

## Must Do

- `baseURL` 优先来自环境变量，例如 `import.meta.env.VITE_API_BASE_URL`。
- 请求拦截器只处理 token、公共 header、trace id、取消信号等通用逻辑。
- 响应拦截器统一处理 HTTP 错误、业务错误码、登录过期和响应解包。
- 登录过期只能触发一次清理和跳转，避免多个并发 401 造成重复弹窗或重复重定向。
- 错误对象要保留状态码、业务码、消息和原始上下文，方便页面提示和日志上报。
- 不在请求客户端里写具体业务提示文案，除非项目已有统一提示规范。

## Verification

- 检查登录态正常、token 失效、网络错误、业务错误码和成功响应的表现。
- 检查 GET `params`、POST body、文件上传、文件下载是否仍能正常工作。
- 修改请求封装后运行项目约定的类型检查或构建命令。
