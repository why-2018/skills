---
name: admin-crud-page
description: 生成和维护 Vue3 + TypeScript + Element Plus 的后台 CRUD 页面。Use when building admin list pages, search filters, tables, pagination, create/edit/delete dialogs, batch operations, and API-backed management pages.
---

# Admin CRUD Page

## Quick Start

生成后台 CRUD 页面时：

1. 先查 `src/pages/`、`src/components/`、`src/api/modules/`、`src/router/index.ts`，找已有相似列表页、表单弹窗、接口模块和路由写法。
2. 先查项目是否已有权限按钮、字典枚举、表格二次封装、分页封装、消息提示封装；有就复用，没有就使用 Element Plus 原生组件，不要临时发明新封装。
3. 先确定列表、详情、新增、编辑、删除、启停、批量操作的接口和字段；缺接口或字段时先向用户确认。
4. 在 `src/api/modules/` 建业务 API 模块并导出请求参数、列表项、表单 payload、分页结果类型。
5. 页面放在 `src/pages/`；新增/编辑表单重复使用时拆到 `src/components/`。
6. 需要路由访问时更新 `src/router/index.ts`，并沿用已有路由命名和懒加载习惯。

## Must Do

- 删除、禁用、启用、重置、批量操作必须二次确认。
- 新增、编辑、删除、启停、批量操作失败时必须有用户可见反馈。
- 新增/编辑提交时必须设置 submit loading，并禁用提交按钮，避免重复提交。
- 列表请求必须设置 table loading；分页、搜索、重置必须能触发刷新。
- 搜索必须从第一页重新查；删除当前页最后一条后必须处理页码回退。
- 批量操作必须先判断 selection 是否为空，为空时直接提示用户。
- 成功的副作用操作必须刷新列表；新增/编辑成功后关闭弹窗并清理表单状态。

## Verification

- 检查新增路由能访问页面。
- 检查查询、重置、分页、新增、编辑、删除的状态流。
- 修改 Vue/TS/API 后运行 `npm run build`。

## Details

- 具体页面结构、状态命名、API、Element Plus 操作约定见 [crud-conventions.md](crud-conventions.md)。
