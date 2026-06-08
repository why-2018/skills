---
name: admin-list-page
description: 生成和维护后台列表页，包括搜索区、表格、分页、loading、刷新和基础操作。Use when building admin list pages, management tables, query forms, paginated API lists, refresh flows, or list views backed by frontend API modules.
---

# Admin List Page

## Quick Start

生成后台列表页时：

1. 先查 `src/pages/` 中已有相似列表页，沿用目录、命名、组件库、权限按钮和状态管理方式。
2. 确认列表接口、查询参数、分页字段、表格列、操作按钮和默认排序。
3. 页面状态至少包含搜索模型、表格数据、table loading、分页状态和刷新方法。
4. 如果涉及新增、编辑、删除等复杂操作，优先复用已有弹窗、表单和 API 模块约定。

## Must Do

- 初次进入页面要自动加载列表，失败时给出用户可见反馈。
- 搜索必须回到第一页；重置必须恢复默认查询条件并重新请求。
- 表格请求必须设置 loading，避免重复点击刷新造成状态混乱。
- 删除当前页最后一条后要处理页码回退，不能停留在空的越界页。
- 操作列按钮必须根据权限、状态或业务规则控制显隐和禁用。
- 列表页不要直接拼 URL；通过业务 API 模块调用接口。

## Verification

- 检查进入页面、搜索、重置、刷新、分页切换和 pageSize 切换。
- 检查空数据、接口失败、加载中和权限按钮状态。
- 修改页面、API 或类型后运行项目约定的类型检查或构建命令。
