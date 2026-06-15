---
name: feedback-message
description: 规范成功、失败、警告、确认弹窗、通知和表单错误提示。Use when refining frontend messages, toast notifications, confirm dialogs, alert banners, form error copy, or operation feedback consistency.
---

# Feedback Message

## Quick Start

处理反馈提示时：

1. 先查项目使用的消息组件、确认弹窗、通知组件、表单错误展示和文案风格。
2. 明确反馈类型：成功、失败、警告、确认、加载中、空状态或阻断错误。
3. 用户操作必须有结果反馈，后台自动刷新或静默动作则按项目约定控制提示强度。
4. 文案短、具体、可行动，不暴露技术堆栈。

## Must Do

- 成功提示说明结果，不重复页面标题或按钮文字。
- 失败提示说明用户下一步能做什么，必要时提供重试入口。
- 危险确认要说明影响对象、影响数量和不可逆后果。
- 表单错误优先定位到字段，页面级错误用于跨字段或服务端错误。
- 避免同一操作同时弹出多个 toast、通知和弹窗。
- 不把接口原始错误直接展示给用户，除非已经过安全和文案处理。

## Verification

- 检查新增、编辑、删除、导入、导出、上传、登录失效和权限失败。
- 检查连续点击、重复失败和并发请求不会刷屏。
- 运行项目约定的类型检查或构建命令。
