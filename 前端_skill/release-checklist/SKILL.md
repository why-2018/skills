---
name: release-checklist
description: 上线前检查构建、环境变量、路由访问、权限、接口地址和回滚点。Use when preparing frontend release, production deployment checks, smoke testing, env verification, rollback planning, or release readiness review.
---

# Release Checklist

## Quick Start

准备上线时：

1. 先查发布脚本、构建命令、环境变量、部署路径、回滚方式和冒烟测试清单。
2. 明确发布范围：新增页面、权限变更、接口变更、依赖升级、样式调整或配置变更。
3. 按风险从构建、环境、路由、权限、接口、核心流程和回滚点逐项检查。
4. 发布前只做必要修复，不在最后阶段混入无关重构。

## Must Do

- 构建必须成功，并确认产物路径、base、静态资源和 sourcemap 策略。
- 环境变量要确认开发、测试、生产差异，尤其接口地址和功能开关。
- 路由要检查直接访问、刷新、404、权限拦截和登录回跳。
- 核心流程要冒烟：登录、列表、搜索、详情、表单提交、上传下载和导入导出。
- 明确回滚版本、回滚步骤、影响范围和验证方式。
- 发布说明要包含改动范围、风险点、验证结果和已知问题。

## Verification

- 运行构建、类型检查、测试或项目约定发布前命令。
- 按清单完成核心页面手动冒烟。
- 确认回滚方案和监控观察点。
