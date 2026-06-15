---
name: e2e-user-flow
description: 为登录、CRUD、表单提交、权限跳转等关键前端链路补充端到端测试。Use when adding Playwright/Cypress e2e tests, user-flow regression tests, mocked backend flows, permission navigation checks, or release smoke tests.
---

# E2E User Flow

## Quick Start

补充端到端测试时：

1. 先查项目使用 Playwright、Cypress 还是其他工具，以及启动命令、测试账号和 mock 方案。
2. 明确用户链路的入口、关键操作、成功结果、失败结果和可等待的稳定信号。
3. 优先覆盖高价值冒烟链路：登录、列表查询、新增编辑、删除确认、权限跳转和表单提交。
4. 测试选择器优先使用可访问名称、角色或项目已有 `data-testid` 约定。

## Must Do

- 每条用例要有清晰前置状态，避免依赖上一条测试产生的数据。
- 等待接口、URL、文本或状态变化，不使用固定 sleep 作为主要同步方式。
- 对 CRUD 流程要覆盖成功提示、列表刷新、分页变化和失败反馈。
- 对权限流程要覆盖无权限菜单隐藏、直接访问回退和按钮不可见或禁用。
- 使用 mock 数据时保持接口契约真实，避免只 mock 页面需要的一小段假结构。
- 测试数据要可清理、可重复运行，不能污染共享环境。

## Verification

- 运行相关 e2e 用例或项目冒烟命令。
- 检查桌面和必要移动视口下的关键链路。
- 失败时保留截图、trace 或错误日志入口，便于复现。
