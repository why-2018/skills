---
name: theme-dark-mode
description: 实现主题变量、暗色模式、Element Plus 主题覆盖和本地偏好保存。Use when adding theme tokens, dark mode, CSS variables, Element Plus theme overrides, or user theme preference persistence.
---

# Theme Dark Mode

## Quick Start

处理主题或暗色模式时：

1. 先查项目全局样式、CSS 变量、组件库主题覆盖和用户偏好存储。
2. 明确主题范围：颜色、字体、间距、圆角、阴影、图表色板和状态色。
3. 使用变量驱动主题，不在页面里散落硬编码颜色。
4. 先覆盖核心布局、表单、表格、弹窗和反馈组件，再处理边缘页面。

## Must Do

- 主题 token 要语义化，例如背景、文本、边框、主色、成功、警告、危险。
- 暗色模式要处理组件库、滚动条、图表、空状态、代码块和图片边界。
- 用户偏好要支持本地保存，并可跟随系统偏好作为默认值。
- 切换主题不能造成页面闪烁、文字不可读或状态色失真。
- 自定义组件必须使用主题变量，不直接写固定浅色背景。
- 不要只改主色而忽略 hover、active、disabled 和 focus 状态。

## Verification

- 检查浅色、暗色、系统跟随、刷新保持和运行时切换。
- 检查表格、表单、弹窗、通知、图表和错误状态。
- 运行项目约定的类型检查或构建命令。
