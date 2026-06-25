---
name: drag-drop-sortable
description: 实现拖拽排序、树节点拖拽、跨列表移动、排序保存和回滚。Use when adding drag-and-drop sorting, draggable lists, tree node dragging, cross-list movement, or persisted order updates.
---

# Drag Drop Sortable

## Quick Start

处理拖拽排序时：

1. 先查项目是否已有拖拽库、表格排序、树节点拖拽和排序保存接口。
2. 明确拖拽对象、可拖区域、排序范围、跨列表规则和保存时机。
3. 简单排序优先用成熟库或组件库能力，不手写复杂指针事件。
4. 排序状态要能回滚，避免接口失败后 UI 和后端不一致。

## Must Do

- 拖拽项必须有稳定 id，不使用数组索引作为最终排序依据。
- 禁止拖拽的项、区域和业务状态要在 UI 与提交前同时校验。
- 保存排序要处理 loading、失败回滚、成功提示和重复提交。
- 树节点拖拽要校验父子关系、层级限制和循环引用。
- 跨列表移动要明确源列表、目标列表、插入位置和权限规则。
- 为键盘或无法拖拽场景提供可接受替代操作。

## Verification

- 检查同列表排序、跨列表移动、禁用项、接口失败回滚和刷新后顺序。
- 检查树拖拽层级、父子关系和边界位置。
- 运行项目约定的类型检查或构建命令。
