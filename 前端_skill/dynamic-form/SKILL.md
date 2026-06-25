---
name: dynamic-form
description: 根据配置或接口动态渲染表单项、联动显隐、默认值和提交转换。Use when building schema-driven forms, API-driven form fields, conditional fields, dynamic validation, or configurable admin forms.
---

# Dynamic Form

## Quick Start

处理动态表单时：

1. 先查项目是否已有表单 schema、字段组件映射、字典加载和校验规则生成方式。
2. 明确动态来源：本地配置、接口配置、角色权限、业务状态或上一步输入。
3. 把字段展示、默认值、联动显隐、校验规则和提交转换拆清楚。
4. 简单业务表单不要强行 schema 化；动态规则稳定复用时再沉淀配置。

## Must Do

- 每个字段配置必须包含稳定 key、标签、组件类型、默认值、校验和提交映射。
- 联动显隐要同步处理值清理、校验移除和提交参数。
- 异步选项要有 loading、失败重试和空选项状态。
- 动态校验要在字段变化后重新触发，不留下过期错误。
- 配置来自接口时必须做兜底校验，避免未知组件或危险属性直接渲染。
- 不要把复杂业务逻辑全部塞进模板表达式，必要时抽成可测试 helper。

## Verification

- 检查默认值、联动显隐、校验、重置、回显和提交参数。
- 检查接口配置缺字段、未知类型、选项加载失败和权限差异。
- 运行项目约定的类型检查或构建命令。
