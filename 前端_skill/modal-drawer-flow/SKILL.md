---
name: modal-drawer-flow
description: 实现弹窗、抽屉、关闭确认、嵌套交互和焦点管理。Use when building modal dialogs, drawers, nested overlays, close confirmation, focus handling, or overlay interaction flows.
---

# Modal Drawer Flow

## Quick Start

处理弹窗或抽屉时：

1. 先查项目组件库弹窗、抽屉、确认弹窗和表单弹窗封装。
2. 明确打开来源、回显数据、提交事件、关闭行为、遮罩点击和键盘行为。
3. 简单编辑用弹窗，信息密集或需要上下文保留时考虑抽屉。
4. 嵌套弹层要谨慎，优先简化流程或拆成步骤。

## Must Do

- 打开时初始化状态，关闭后清理表单、错误、loading 和临时数据。
- 有未保存修改时要关闭确认，避免误关丢数据。
- 提交中要禁止重复提交和关闭造成状态错乱。
- 嵌套弹层要处理层级、焦点返回、Esc 和遮罩关闭。
- 弹窗内容过长要有滚动区域，底部操作按钮保持可访问。
- 不要把弹窗可见状态分散在多个组件里互相抢控制权。

## Verification

- 检查打开、回显、提交、取消、遮罩点击、Esc、未保存确认和重复提交。
- 检查移动端宽度、长内容滚动和焦点返回。
- 运行项目约定的类型检查或构建命令。
