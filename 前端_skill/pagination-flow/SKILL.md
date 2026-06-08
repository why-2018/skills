---
name: pagination-flow
description: 维护分页请求、页码回退、搜索回到第一页、pageSize 变化和总数同步。Use when implementing paginated lists, page query params, total counts, current page fallback, page size changes, or frontend table pagination flows.
---

# Pagination Flow

## Quick Start

处理分页时：

1. 先确认项目分页字段命名，例如 `page`、`pageNum`、`current`、`pageSize`、`size`、`total`。
2. 查已有列表页的分页组件用法，沿用事件名、默认页大小和接口参数转换。
3. 把分页状态集中在页面或列表组合函数中，避免搜索表单、表格和 API 模块各自维护一份。
4. 搜索、重置、排序和筛选变化通常都应回到第一页再请求。

## Must Do

- 初始页码和 pageSize 要有明确默认值。
- pageSize 变化后必须回到第一页，避免请求不存在的页。
- 删除当前页最后一条后，如果当前页大于第一页，要回退一页重新请求。
- 接口返回 total 后要同步到分页组件，不能用当前页数据长度冒充总数。
- 前端字段和后端字段不一致时，在请求前统一转换，不让页面到处散落映射。
- 分页请求失败时不要错误清空已有分页状态，除非项目明确要求。

## Verification

- 检查第一页、最后一页、空结果、pageSize 切换、搜索后分页和删除后回退。
- 检查分页参数实际传给接口的字段和值。
- 修改分页逻辑后运行项目约定的类型检查或构建命令。
