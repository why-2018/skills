---
name: dependency-management
description: 安装、替换、升级前端依赖，并检查包管理器、版本冲突和引入成本。Use when adding npm dependencies, upgrading packages, replacing libraries, resolving peer dependency conflicts, or auditing frontend dependency cost.
---

# Dependency Management

## Quick Start

处理依赖时：

1. 先查 `package.json`、lockfile、包管理器、Node 版本和现有同类依赖。
2. 明确依赖用途、运行时还是开发时、是否已有轻量替代和引入成本。
3. 优先使用项目当前包管理器，不混用 npm、pnpm、yarn。
4. 添加或升级后检查构建、类型、样式和运行时兼容性。

## Must Do

- 不要为了单个页面引入大型库，先评估组件库、浏览器 API 和已有工具。
- 升级依赖要查看破坏性变更、peer dependencies 和 lockfile 变化。
- 替换依赖要清理旧 import、配置、样式和类型声明。
- 开发依赖和生产依赖要放在正确分组。
- 安全修复不能盲目大版本升级，必要时分步升级并验证。
- 不要手改 lockfile 中不理解的片段。

## Verification

- 运行安装、类型检查、测试或构建命令中的可用项。
- 检查包管理器一致性、lockfile diff 和 bundle 影响。
- 手动验证依赖影响到的页面或组件。
