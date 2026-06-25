---
name: inline-edit-table
description: 实现表格行内编辑、单元格校验、保存取消、批量提交和脏数据提示。Use when adding editable table rows, cell editors, row validation, save/cancel flows, or batch editing in admin tables.
---

# Inline Edit Table

## Quick Start

处理行内编辑表格时：

1. 先查项目表格封装、表单校验、单元格编辑组件和批量提交 API。
2. 明确编辑粒度：单元格、整行、多行批量或局部字段。
3. 区分原始数据、编辑副本、校验状态、保存中状态和脏数据状态。
4. 如果字段联动复杂，优先评估弹窗表单是否更适合。

## Must Do

- 编辑时使用副本，取消必须能恢复原始数据。
- 每行必须有稳定 row key，不能用索引作为编辑状态 key。
- 保存前校验当前行或当前批次，错误要定位到单元格。
- 保存中要禁用重复提交，并处理部分成功和失败回滚。
- 翻页、筛选、刷新或离开页面前要提示未保存修改。
- 不要让展示格式化值和实际提交值混在一起。

## Verification

- 检查进入编辑、修改、校验失败、保存、取消、批量提交和刷新。
- 检查分页切换、排序、删除行和接口失败后的状态恢复。
- 运行项目约定的类型检查或构建命令。
