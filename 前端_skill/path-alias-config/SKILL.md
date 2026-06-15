---
name: path-alias-config
description: 配置和排查前端路径别名，保持 Vite、TypeScript 和 IDE 解析一致。Use when setting up @ aliases, fixing import resolution, syncing vite and tsconfig paths, or refactoring relative imports.
---

# Path Alias Config

## Quick Start

处理路径别名时：

1. 先查 `vite.config.ts`、`tsconfig*.json`、IDE 配置、测试配置和已有 import 风格。
2. 确认别名目标目录、使用范围、是否影响测试和构建工具。
3. 新增或修改别名时同步所有解析入口，不只改 Vite。
4. 批量替换相对路径前先确认不会跨越模块边界或形成循环依赖。

## Must Do

- Vite `resolve.alias` 和 TypeScript `compilerOptions.paths` 必须保持一致。
- 测试工具、lint 工具或 Storybook 等额外环境也要同步解析规则。
- 别名命名要少而稳定，优先保留 `@` 指向 `src` 的常见约定。
- 不要用别名隐藏不合理的跨层依赖，例如页面直接引用另一个页面内部组件。
- 修改别名后检查大小写、Windows/Linux 路径差异和构建产物。
- 不要在没有配置的项目中假设 `@/` 一定可用。

## Verification

- 检查开发启动、构建、测试和 IDE 跳转。
- 抽查 API、组件、页面、Store 的别名导入。
- 运行项目约定的类型检查或构建命令。
