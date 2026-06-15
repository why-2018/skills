---
name: vite-config
description: 维护 Vite 插件、代理、构建配置、静态资源路径和开发服务器配置。Use when editing vite.config.ts, dev server proxy, build output, plugin setup, asset base path, optimizeDeps, or Vite troubleshooting.
---

# Vite Config

## Quick Start

维护 Vite 配置时：

1. 先查 `vite.config.ts`、`package.json` 脚本、`tsconfig`、环境变量和部署路径。
2. 明确改动目标：代理、别名、插件、构建输出、静态资源路径、依赖预构建或 sourcemap。
3. 优先沿用当前插件顺序和配置风格，只补必要字段。
4. 配置变更后运行开发启动或构建验证。

## Must Do

- 路径别名要同步 TypeScript 配置和 IDE 解析。
- 代理只用于开发联调，不要把生产接口规则藏在 dev server 配置里。
- `base` 要结合部署子路径、静态资源路径和路由模式一起验证。
- 插件新增前确认依赖已安装、版本兼容和引入成本。
- 构建优化要有目标，例如 sourcemap、chunk 拆分、压缩、兼容性或体积分析。
- 不要在配置里写业务常量、账号信息或敏感地址。

## Verification

- 检查 dev server、代理、别名导入、静态资源和生产构建。
- 如果修改构建输出，检查部署路径和刷新访问。
- 运行项目约定的类型检查或构建命令。
