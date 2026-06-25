---
name: websocket-sse
description: 接入 WebSocket 或 SSE，处理连接、重连、心跳、消息分发和页面卸载。Use when adding real-time updates, WebSocket clients, Server-Sent Events, reconnect logic, heartbeat, or live notification streams.
---

# WebSocket SSE

## Quick Start

接入实时连接时：

1. 先查项目鉴权、请求客户端、事件总线、Store 和已有轮询或消息通知方案。
2. 明确使用 WebSocket 还是 SSE，以及服务端协议、鉴权方式和消息类型。
3. 连接逻辑集中封装，页面只订阅自己需要的事件。
4. 先实现连接、消息分发、关闭和错误处理，再补重连和心跳。

## Must Do

- 连接地址、鉴权参数和环境变量要集中管理，不能散落页面。
- 页面卸载或用户退出时必须取消订阅或关闭连接。
- 重连要有退避策略和最大次数，避免网络异常时疯狂重连。
- 心跳、超时和服务端断开要有明确处理。
- 消息类型要有类型定义和兜底分支，未知消息不能打崩页面。
- 实时更新要和列表缓存、详情状态、通知计数保持一致。

## Verification

- 检查连接成功、断开、重连、鉴权失效、页面卸载和消息分发。
- 检查重复订阅、网络切换、未知消息和退出登录。
- 运行项目约定的类型检查或构建命令。
