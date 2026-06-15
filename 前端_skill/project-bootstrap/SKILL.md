---
name: project-bootstrap
description: 初始化前端项目结构、基础目录、入口文件、全局样式和默认配置。Use when bootstrapping a Vue/Vite frontend project, creating base folders, wiring app entry, global styles, router/store setup, or first-page scaffolding.
---

# Project Bootstrap

## Quick Start

初始化项目结构时：

1. 先检查包管理器、框架版本、`package.json`、入口文件、构建配置和已有目录。
2. 明确项目类型：后台管理、业务门户、组件库、活动页或嵌入式页面。
3. 按项目技术栈补齐最小可运行结构，不一次性塞入暂时不用的复杂目录。
4. 初始化后确保页面能启动、路由能访问、样式能加载、类型检查能跑。

## Must Do

- 基础目录要围绕真实工作流组织，例如 `pages`、`components`、`api`、`stores`、`router`、`styles`。
- 入口文件只注册必要插件和全局资源，避免写业务逻辑。
- 全局样式要区分 reset、变量、布局工具和组件库覆盖。
- 默认路由要提供可访问页面和异常兜底，避免空白首屏。
- 初始化脚本、环境变量和路径别名要与 Vite、TypeScript、IDE 保持一致。
- 不要提前引入大型依赖、复杂状态管理或过度抽象模板。

## Verification

- 运行安装、启动、类型检查或构建命令中的可用项。
- 检查首屏、路由跳转、全局样式和基础布局。
- 确认新增目录和命名与项目约定一致。
