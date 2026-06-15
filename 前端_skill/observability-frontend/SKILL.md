---
name: observability-frontend
description: 接入和维护前端错误监控、性能指标、用户行为日志和接口失败追踪。Use when adding frontend observability, error reporting, performance metrics, request tracing, user action logs, or production diagnostics.
---

# Observability Frontend

## Quick Start

接入前端可观测能力时：

1. 先查项目是否已有监控 SDK、日志工具、请求拦截器、错误边界和环境开关。
2. 明确要采集的事件：运行时错误、资源加载失败、接口失败、性能指标、关键用户操作。
3. 设计最小字段集，优先保证可定位问题，不采集不必要的隐私数据。
4. 监控逻辑应集中封装，通过环境变量控制开启、采样和上报地址。

## Must Do

- 捕获 `error`、`unhandledrejection`、资源加载失败和框架级错误。
- 接口失败日志要包含请求标识、状态码、业务码、耗时和页面来源，避免记录敏感参数。
- 性能指标优先关注首屏、路由切换、接口耗时、长任务和资源加载。
- 用户行为日志只记录诊断必要动作，不记录密码、Token、身份证号等敏感信息。
- 上报失败不能影响主流程；必须降级为静默失败或本地调试输出。
- 在开发、测试、生产环境中区分采样率和日志详细程度。

## Verification

- 手动触发运行时错误、接口失败和资源失败，确认上报或调试输出。
- 检查日志字段脱敏和环境开关。
- 运行项目约定的类型检查或构建命令。
