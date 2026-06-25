---
name: rich-text-editor
description: 接入富文本编辑器，处理内容回显、图片上传、XSS 风险和提交格式。Use when integrating rich text editors, rendering HTML content, uploading editor images, sanitizing content, or saving article-like fields.
---

# Rich Text Editor

## Quick Start

接入富文本编辑器时：

1. 先查项目是否已有编辑器依赖、上传接口、内容净化、预览组件和样式覆盖。
2. 明确内容格式：HTML、Markdown、JSON 文档模型或纯文本摘要。
3. 区分编辑态、预览态、详情回显和提交给后端的格式。
4. 如果只是简单备注，优先使用 textarea，不引入完整富文本编辑器。

## Must Do

- 回显 HTML 前要确认来源可信或经过 sanitizer 处理。
- 图片上传要复用项目上传接口，并处理大小、类型、失败、进度和删除。
- 编辑器内容为空时要识别空标签，不只判断字符串长度。
- 提交前要处理 XSS 风险、外链协议、图片 URL 和附件引用。
- 编辑器样式要限制作用域，避免污染全局排版。
- 不要把后端原始错误或内部存储路径直接展示给用户。

## Verification

- 检查输入、回显、预览、清空、图片上传、提交失败和只读展示。
- 检查恶意 HTML、空内容、长内容和移动端编辑体验。
- 运行项目约定的类型检查或构建命令。
