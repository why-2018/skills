---
name: data-table
description: 维护数据表格的列定义、操作列、选择列、排序、空状态、固定列和自定义渲染。Use when building or refactoring admin tables, Element Plus tables, typed column configs, row actions, selection tables, sortable columns, or custom cell renderers.
---

# Data Table

## Quick Start

处理数据表格时：

1. 先查项目是否已有表格封装、列配置格式、权限按钮组件、状态标签和空状态组件。
2. 确认列表项类型、唯一行 key、列展示规则、操作列按钮、选择模式和排序来源。
3. 简单表格直接使用组件库；重复出现的列配置、状态渲染和操作按钮再抽成局部 helper。
4. 表格只负责展示和交互事件，数据请求、分页、弹窗状态放在页面层。

## Must Do

- 每行必须有稳定 `row-key`，选择、展开、树表格和局部刷新都依赖它。
- 金额、日期、状态、枚举、布尔值要统一格式化，避免页面内散落魔法值。
- 操作列要处理权限、业务状态、loading、禁用态和二次确认。
- 空数据、加载中、接口错误和筛选无结果要有清晰状态。
- 远程排序要把排序字段和方向同步到查询参数，并触发第一页刷新。
- 表格宽度、固定列和溢出 tooltip 要兼顾窄屏和长文本。

## Verification

- 检查列展示、选择、排序、操作按钮、空状态和 loading 状态。
- 检查长文本、缺失值、枚举未知值和权限差异。
- 修改表格相关组件后运行项目约定的类型检查或构建命令。
