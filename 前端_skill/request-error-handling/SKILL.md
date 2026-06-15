---
name: request-error-handling
description: 统一处理接口失败、业务错误码、登录失效、重试、用户提示和日志。Use when improving API error handling, business code mapping, auth expiration, request retry, toast messages, or frontend request diagnostics.
---

# Request Error Handling

## Quick Start

处理请求错误时：

1. 先查请求客户端、拦截器、业务错误码约定、登录失效流程和消息提示组件。
2. 区分网络错误、HTTP 错误、业务错误码、超时、取消请求和解析错误。
3. 能在请求层统一处理的放请求层，页面特有业务反馈留在页面层。
4. 改动错误处理时同步检查正常响应解包和 TypeScript 类型。

## Must Do

- 登录失效只触发一次统一清理和跳转，避免多个并发请求重复弹窗。
- 业务错误码要有集中映射，并允许页面覆盖特殊提示。
- 列表、表单、导入导出等场景要正确关闭 loading。
- 可重试请求要明确重试条件、次数、间隔和幂等风险。
- 错误日志不要包含 Token、密码、敏感参数或完整个人信息。
- 不要在每个页面复制同一套 try/catch 提示逻辑。

## Verification

- 模拟 401、403、500、超时、网络断开和业务错误码。
- 检查 loading 关闭、消息提示、登录跳转和页面重试。
- 运行项目约定的类型检查或构建命令。
