---
name: batch-actions
description: 实现批量删除、批量启停、批量导出、选择校验和二次确认。Use when adding batch operations to admin tables, multi-select actions, bulk delete/enable/export, selection validation, or batch confirmation flows.
---

# Batch Actions

## Quick Start

处理批量操作时：

1. 先查表格选择列、权限按钮、确认弹窗、批量 API 和刷新分页写法。
2. 明确选择规则、最多数量、跨页选择、禁选条件、操作结果和失败明细。
3. 批量操作入口放在表格工具栏或项目既有位置，不打断单条操作流。
4. 操作完成后同步选择状态、列表数据、分页 total 和用户反馈。

## Must Do

- 没有选择数据时要禁用操作或给出明确提示。
- 选择项要按业务状态过滤，不能把不可操作行悄悄提交给接口。
- 危险操作必须二次确认，并展示影响数量或关键对象名称。
- 批量请求要设置 loading，防止重复提交。
- 部分成功时要展示成功数量、失败数量和失败原因入口。
- 操作后要清空已失效选择，并处理当前页删除后页码回退。

## Verification

- 检查未选择、单选、多选、禁选、跨页和部分失败。
- 检查权限差异、二次确认、loading 和列表刷新。
- 运行项目约定的类型检查或构建命令。
