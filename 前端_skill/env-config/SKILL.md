---
name: env-config
description: 维护前端 `.env`、构建环境变量、接口地址和开发/测试/生产环境差异。Use when configuring Vite env files, API base URLs, feature flags, build modes, environment-specific behavior, or deployment variables.
---

# Env Config

## Quick Start

处理环境配置时：

1. 先查 `.env*`、`vite.config.ts`、请求客户端、部署文档和现有环境变量命名。
2. 区分构建时变量、运行时配置、接口地址、功能开关和敏感配置。
3. Vite 暴露给前端的变量应使用项目约定前缀，通常是 `VITE_`。
4. 修改环境变量后同步类型声明、示例文件和读取位置。

## Must Do

- 不要把密码、私钥、生产 Token 等敏感信息放进前端环境变量。
- 接口 base URL 要集中读取，避免页面里硬编码环境地址。
- 开发、测试、预发、生产的变量差异要可追踪，不靠临时改代码切环境。
- 缺失必要变量时应在启动或构建阶段尽早暴露问题。
- 布尔和数字变量要显式转换类型，避免字符串 `"false"` 被当作真值。
- 更新 `.env.example` 或项目等价示例，说明必填和可选变量。

## Verification

- 检查不同 mode 下变量读取、接口地址、功能开关和构建结果。
- 运行项目约定的类型检查或构建命令。
- 确认没有敏感值进入仓库、日志或打包产物。
