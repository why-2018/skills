---
name: cascader-tree-select
description: 处理级联选择、树选择、懒加载节点、回显路径和半选状态。Use when building cascaders, tree selects, department selectors, region selectors, lazy tree loading, or checked tree state.
---

# Cascader Tree Select

## Quick Start

处理级联或树选择时：

1. 先查项目已有部门、地区、分类、权限树或组织树组件。
2. 明确数据结构：id、parentId、children、leaf、disabled、label 和 path。
3. 区分单选、多选、父子联动、半选、只选叶子和懒加载。
4. 回显前先确认接口保存的是节点 id、路径数组还是完整节点对象。

## Must Do

- 节点 key 必须稳定，不能依赖 label 或数组索引。
- 懒加载要处理 loading、失败重试、空子节点和叶子判定。
- 多选时要明确是否包含父节点、半选节点和禁用节点。
- 回显路径缺失时要能按 id 补全祖先链路或给出兜底展示。
- 搜索过滤不能破坏已选状态和展开状态。
- 提交值要和后端契约一致，不把组件内部节点对象直接提交。

## Verification

- 检查单选、多选、回显、清空、搜索、懒加载和禁用节点。
- 检查半选状态、父子联动、接口失败和超深层级。
- 运行项目约定的类型检查或构建命令。
