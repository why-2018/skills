---
name: performance-optimization
description: 排查和优化前端首屏、渲染、请求、列表和构建体积性能问题。Use when fixing slow page load, repeated renders, large-list jank, request waterfalls, bundle size, or Vue frontend performance regressions.
---

# Performance Optimization

## Quick Start

处理性能问题时：

1. 先确认问题类型：首屏加载慢、交互卡顿、重复渲染、接口瀑布、大列表卡顿或 bundle 过大。
2. 查已有性能工具、构建分析脚本、懒加载约定、请求缓存和列表虚拟滚动实现。
3. 先用可观测证据定位瓶颈，再做最小改动；不要只凭直觉重构大块代码。
4. 性能改动后保留功能行为不变，并检查 loading、错误态和权限态没有退化。

## Must Do

- 首屏慢优先检查路由懒加载、依赖体积、图片资源、首屏接口数量和阻塞脚本。
- 渲染卡顿优先检查模板复杂表达式、深层 watch、大对象响应式、无 key 列表和重复 computed。
- 大列表优先考虑分页、虚拟列表、懒渲染、局部更新和批量 DOM 操作拆分。
- 请求瀑布要区分必须串行和可并行请求，避免同一参数重复请求。
- 优化 bundle 时先查看构建产物，再处理按需引入、动态 import、依赖替换和重复包。
- 不要为了微优化牺牲类型清晰度、错误处理和业务可读性。

## Verification

- 记录优化前后的关键指标或可复现场景。
- 检查首屏、刷新、分页、筛选、切换路由和返回页面。
- 运行项目约定的类型检查、测试或构建命令。
