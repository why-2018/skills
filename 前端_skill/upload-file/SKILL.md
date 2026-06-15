---
name: upload-file
description: 实现和维护文件上传、图片上传、大小类型限制、预览、删除、回显、失败重试和提交格式。Use when building upload components, image uploaders, attachment fields, file validation, preview dialogs, form upload fields, or API-backed file storage flows.
---

# Upload File

## Quick Start

处理文件上传时：

1. 先查项目已有上传组件、文件 API、图片预览、鉴权 Header 和表单提交格式。
2. 明确上传模式：自动上传、手动提交、单文件、多文件、图片、附件或分片上传。
3. 明确接口返回的文件标识、URL、名称、大小、MIME 类型和提交给业务接口的字段。
4. 上传组件负责文件选择、校验、上传状态和回显；业务表单负责最终 payload。

## Must Do

- 上传前必须校验文件类型、大小、数量和必填规则。
- 上传请求要携带项目约定的鉴权信息，并处理 401、超时和网络错误。
- 上传中要展示进度或 loading，并禁止重复提交造成状态错乱。
- 编辑回显时要把接口数据转换成组件需要的 file list，删除时同步业务字段。
- 图片上传要支持预览、删除和失败重试；敏感文件不要直接暴露不可控外链。
- 上传失败必须给出用户可见反馈，并保留可重试或重新选择的路径。

## Verification

- 检查合法文件、非法类型、超大文件、上传失败、删除、回显、重新上传和表单提交。
- 检查单文件、多文件、图片预览和接口返回字段转换。
- 修改上传组件或文件 API 后运行项目约定的类型检查或构建命令。
