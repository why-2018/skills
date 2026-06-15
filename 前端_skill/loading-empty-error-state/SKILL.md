---
name: loading-empty-error-state
description: 统一前端 loading、空数据、错误重试、骨架屏、局部刷新和用户可见反馈状态。Use when adding loading spinners, empty states, error retry views, skeleton screens, partial refresh states, or API-backed UI state handling.
---

# Loading Empty Error State

## Quick Start

处理页面状态时：

1. 先查项目是否已有 loading、空状态、错误页、骨架屏或结果组件。
2. 明确状态来源：首次加载、局部刷新、搜索无结果、接口失败、权限为空或数据确实为空。
3. 优先让状态跟随请求流程变化，不用多个布尔值表达同一件事。
4. 列表页、详情页、弹窗和局部卡片的 loading 要分开，避免一个请求锁住整个页面。

## Must Do

- 首次加载、刷新中、空数据、错误、成功有数据这些状态不能互相重叠。
- 接口失败必须有用户可见提示，并提供可行的重试入口。
- 搜索无结果要和系统暂无数据区分，文案应能解释当前状态。
- 提交类 loading 要禁用按钮；查询类 loading 要避免重复请求造成数据乱序。
- 骨架屏只用于可预期布局，不能替代错误处理。
- 保留旧数据刷新时，要明确展示局部刷新状态，避免用户误以为数据已更新。

## Verification

- 检查慢请求、失败请求、空结果、重试、刷新和重复点击。
- 检查页面、表格、弹窗、卡片等不同区域的状态不会互相污染。
- 修改状态组件或请求流程后运行项目约定的类型检查或构建命令。
