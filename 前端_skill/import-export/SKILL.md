---
name: import-export
description: 实现和维护 Excel/CSV 导入导出、模板下载、文件校验、进度提示、错误明细和下载文件名。Use when building import flows, export buttons, template downloads, CSV or Excel handling, file validation, blob downloads, or batch data transfer pages.
---

# Import Export

## Quick Start

处理导入导出时：

1. 先查项目已有上传组件、下载工具、请求封装、文件流处理和导入结果页面。
2. 明确导入文件格式、大小限制、模板来源、校验规则、错误明细和成功后的刷新策略。
3. 明确导出参数来自当前筛选条件、选中行还是全部数据。
4. 文件流接口应通过 API 模块封装，页面只负责触发、loading、提示和结果展示。

## Must Do

- 导入前必须校验文件类型、大小、数量和必填文件。
- 模板下载要有明确文件名，失败时给出提示，不能静默无响应。
- 导入中要显示 loading 或进度；导入完成后展示成功数、失败数和错误明细。
- 导出要处理 Blob、文件名、空数据、超时和后端返回 JSON 错误的情况。
- 批量导出选中数据时，必须先判断 selection 是否为空。
- 导入成功后的列表刷新、筛选保留和分页回退要符合页面现有规则。

## Verification

- 检查模板下载、非法文件、空文件、导入失败、部分失败、导入成功和导出失败。
- 检查导出的文件名、文件类型、筛选参数和选中行参数。
- 修改文件流或上传下载逻辑后运行项目约定的类型检查或构建命令。
