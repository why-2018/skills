---
name: code-splitting
description: 处理路由懒加载、组件懒加载、依赖拆包、预加载和构建产物分析。Use when optimizing bundle chunks, lazy loading routes/components, dynamic imports, manualChunks, or build output analysis.
---

# Code Splitting

## Quick Start

处理代码拆包时：

1. 先查看构建配置、路由懒加载、现有动态 import 和产物分析方式。
2. 明确目标：降低首屏体积、拆分重依赖、优化缓存或延迟加载低频页面。
3. 优先从路由级懒加载和大型依赖入手，避免过度碎片化。
4. 拆包后验证真实加载路径，而不只看构建成功。

## Must Do

- 业务页面默认使用路由懒加载，核心布局和首屏必要组件保持稳定。
- 大型编辑器、图表、地图、导入导出等低频能力可动态加载。
- `manualChunks` 要按依赖稳定性和访问路径设计，不随意按文件名拆。
- 懒加载组件要有 loading、错误兜底和重试策略。
- 拆包不能破坏 CSS 加载顺序、组件注册和权限路由。
- 不要把 chunk 拆得过碎导致请求数量反而拖慢页面。

## Verification

- 检查构建产物、首屏访问、懒加载页面、刷新和部署子路径。
- 检查低速网络下 loading、失败重试和缓存命中。
- 运行项目约定的构建命令。
