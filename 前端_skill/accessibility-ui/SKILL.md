---
name: accessibility-ui
description: 改善键盘访问、语义标签、ARIA、焦点顺序、颜色对比和可读提示。Use when improving accessibility, keyboard navigation, aria labels, semantic markup, focus states, or screen-reader friendly frontend UI.
---

# Accessibility UI

## Quick Start

处理无障碍体验时：

1. 先查项目组件库能力、按钮/表单/弹窗封装和已有可访问性约定。
2. 明确用户操作路径：键盘导航、读屏阅读、错误定位、弹窗焦点和颜色识别。
3. 优先修影响核心流程的问题，例如表单提交、弹窗关闭、菜单导航和表格操作。
4. 不改变视觉层级的前提下补语义、焦点和状态说明。

## Must Do

- 可点击元素必须使用 button、a 或具备键盘行为的语义元素。
- 图标按钮要有可访问名称，不能只依赖视觉图标。
- 表单字段要关联 label、错误信息和必填状态。
- 弹窗打开时焦点进入弹窗，关闭后回到触发元素。
- 不只用颜色表达状态，错误、成功、禁用和选中都要有额外提示。
- 自定义交互要支持 Tab、Enter、Space 和 Esc 等常见键盘行为。

## Verification

- 用键盘检查主要流程：菜单、表单、表格、弹窗和分页。
- 检查焦点可见、读屏标签、颜色对比和错误定位。
- 运行项目约定的类型检查或构建命令。
