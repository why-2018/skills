---
name: lint-format-build
description: 处理 ESLint、Prettier、Stylelint、构建失败和格式化规则冲突。Use when fixing lint errors, formatting conflicts, build failures, CI frontend checks, ESLint/Prettier/Stylelint setup, or code-quality scripts.
---

# Lint Format Build

## Quick Start

处理代码质量和构建问题时：

1. 先查 `package.json` 脚本、lint 配置、格式化配置、构建配置和 CI 命令。
2. 区分语法错误、类型错误、lint 规则、格式化差异、依赖缺失和环境问题。
3. 优先修源码问题；只有规则明显不适合项目时才调整配置。
4. 修改配置后验证至少一个真实文件和完整命令。

## Must Do

- 不要通过大范围禁用规则掩盖真实缺陷。
- 自动格式化前确认作用范围，避免无关文件产生大量噪声。
- ESLint、Prettier、Stylelint 的职责要分清，避免规则互相打架。
- 构建失败要定位到入口、类型、依赖、环境变量或资源路径，不只看最后一行错误。
- CI 命令和本地命令要尽量一致，必要差异写清楚原因。
- 修复未使用变量、隐式 any、缺失 import 等问题时保持业务行为不变。

## Verification

- 运行相关 lint、format check、type check 或 build 命令。
- 检查改动文件没有无关格式化风暴。
- 如果命令不可用，说明缺失依赖、脚本或环境限制。
