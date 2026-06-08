---
name: form-validation
description: 维护前端表单校验规则、自定义 validator、异步校验、错误定位和提交前验证。Use when writing Element Plus form rules, validating admin forms, adding async field checks, fixing validation errors, or aligning form models with submit payloads.
---

# Form Validation

## Quick Start

处理表单校验时：

1. 先确认表单模型类型、组件库校验 API、提交 payload 和接口必填规则。
2. 校验规则字段必须与表单模型字段、`prop` 和提交字段保持一致。
3. 提交前统一调用表单实例的 `validate()`；校验失败时不发送请求。
4. 对跨字段、远程唯一性、日期范围等复杂规则，优先写成命名 validator，避免塞进模板。

## Must Do

- 必填、长度、格式、枚举范围和数字边界要与接口约束一致。
- 自定义 validator 必须正确调用成功或失败回调，异步 validator 要处理竞态和重复触发。
- 编辑表单回显后要避免立即触发无意义错误；必要时清理校验状态。
- 动态显隐字段要同步处理默认值、校验启停和提交 payload。
- 提交 loading 期间禁用提交按钮，避免重复提交绕过校验。
- 校验错误要能定位到字段；长表单或分组表单需要考虑滚动到错误位置。

## Verification

- 检查空值、非法值、边界值、异步失败、编辑回显和重置后的校验状态。
- 检查校验通过后提交给接口的 payload 是否只包含需要字段。
- 修改表单校验后运行项目约定的类型检查或构建命令。
