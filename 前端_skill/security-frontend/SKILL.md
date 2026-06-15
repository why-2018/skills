---
name: security-frontend
description: 检查和修复前端 XSS、开放跳转、敏感信息暴露、Token 存储和上传安全问题。Use when reviewing frontend security, handling auth tokens, rendering rich text, sanitizing URLs, validating uploads, or preventing sensitive data exposure.
---

# Security Frontend

## Quick Start

处理前端安全问题时：

1. 先确认风险入口：用户输入展示、富文本、URL 跳转、鉴权信息、文件上传、日志和第三方脚本。
2. 查项目已有鉴权、请求拦截、上传校验、富文本净化和路由白名单实现。
3. 先修可被用户触发或可泄露数据的路径，再整理辅助防护。
4. 安全修复要保持正常业务流程可用，并提供失败反馈。

## Must Do

- 禁止直接渲染未经净化的 HTML；必须使用可信来源或明确的 sanitizer。
- 跳转地址必须校验白名单或同源路径，避免开放跳转。
- Token、用户信息和权限数据不要写入日志、URL、错误提示或可被第三方读取的位置。
- 上传前校验类型、大小、数量和后缀；不要只依赖前端校验作为最终安全边界。
- 下载、预览和外链打开要处理文件名、MIME 类型和危险协议。
- 权限按钮隐藏只是体验优化，关键接口仍要依赖后端鉴权。

## Verification

- 检查正常输入、恶意输入、空值、超长值和危险 URL。
- 检查登录失效、无权限、上传失败和富文本回显。
- 运行项目约定的类型检查、测试或构建命令。
