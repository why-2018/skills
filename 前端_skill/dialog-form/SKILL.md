---
name: dialog-form
description: 实现和维护弹窗表单的打开关闭、props 回显、emit 提交、loading、关闭确认和状态清理。Use when creating create/edit dialogs, modal forms, drawer forms, form submit emits, dialog visibility sync, or reusable admin form popups.
---

# Dialog Form

## Quick Start

处理弹窗表单时：

1. 先查项目已有新增/编辑弹窗写法，沿用 `v-model`、`props`、`emit`、表单 ref 和提交事件约定。
2. 明确弹窗模式是新增、编辑、查看还是复用模式，并定义对应标题、禁用态和提交 payload。
3. 父组件负责打开弹窗、传入初始数据和刷新列表；弹窗内部负责本地表单、校验、提交和清理。
4. 编辑回显时复制 props 到本地表单，避免直接修改 props 或共享引用。

## Must Do

- 打开弹窗时初始化表单；关闭弹窗时清理 loading、校验状态和临时数据。
- 提交前必须执行校验；提交中禁用确认按钮并显示 loading。
- 成功后通过 `emit` 通知父组件刷新或关闭，不在多个地方重复刷新列表。
- 用户编辑过内容后关闭弹窗，必要时提示确认，避免误丢输入。
- 新增和编辑共用弹窗时，字段默认值、回显值和提交 payload 要区分清楚。
- 弹窗内的接口失败必须给出用户可见反馈，并保持弹窗可继续修改。

## Verification

- 检查新增、编辑、查看、提交失败、提交成功、取消关闭和再次打开。
- 检查 props 更新、表单重置、校验清理、按钮 loading 和父组件刷新。
- 修改弹窗表单后运行项目约定的类型检查或构建命令。
