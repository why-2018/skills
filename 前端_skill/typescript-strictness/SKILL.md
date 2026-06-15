---
name: typescript-strictness
description: 补充和修复 TypeScript 类型、接口模型、泛型和严格模式错误。Use when fixing TypeScript errors, adding types for Vue props/emits/API responses, tightening generics, or resolving strict mode issues.
---

# TypeScript Strictness

## Quick Start

处理 TypeScript 问题时：

1. 先查 `tsconfig*.json`、项目类型工具、API 类型、组件 props/emits 和已有泛型写法。
2. 确认错误来源：缺类型、类型不匹配、空值风险、联合类型未收窄或第三方声明缺失。
3. 优先通过准确建模解决，不用 `any` 或强制断言绕过真实问题。
4. 类型改动后检查模板、API、Store 和表单模型是否同步。

## Must Do

- API 请求参数、响应、分页模型和错误结构要有明确类型。
- Vue `props`、`emits`、`ref`、`computed`、表单模型和表格行数据要避免隐式 `any`。
- 空值和可选字段要在使用前收窄，不靠非空断言硬压。
- 枚举、状态和权限值优先使用联合类型或常量映射。
- 第三方库缺声明时补局部声明文件，范围越小越好。
- 不要为了让构建通过关闭严格检查或扩大 tsconfig 排除范围。

## Verification

- 运行 `vue-tsc`、`tsc`、构建或项目约定的类型检查命令。
- 检查关键页面的模板类型、接口调用和表单提交。
- 确认没有新增无意义 `any`、非空断言和类型逃逸。
