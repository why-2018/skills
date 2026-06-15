---
name: mock-data-contract
description: 维护 mock 数据、接口契约、测试夹具和前后端联调占位数据。Use when creating frontend mocks, API fixtures, MSW handlers, test data contracts, backend integration placeholders, or stable demo data.
---

# Mock Data Contract

## Quick Start

维护 mock 和契约时：

1. 先查项目 mock 目录、请求客户端、测试夹具、接口类型和后端接口文档来源。
2. 明确 mock 用途：本地开发、单元测试、e2e 测试、联调占位或演示数据。
3. mock 结构必须贴近真实接口契约，并与 TypeScript 类型保持同步。
4. 测试 mock 要稳定，开发 mock 可以更丰富但不能掩盖边界场景。

## Must Do

- 分页字段、错误码、状态枚举、时间格式和嵌套结构要与真实接口一致。
- 同时准备成功、空数据、失败、权限不足和边界值数据。
- mock 数据中不要放真实手机号、身份证号、Token 或生产用户信息。
- 不要为了页面方便随意改接口字段；需要转换时放在 API 适配层。
- e2e mock 要支持可重复运行和数据重置。
- 契约变化时同步更新 API 类型、mock、测试和相关页面。

## Verification

- 检查页面在成功、空数据、错误和边界数据下都能正常展示。
- 检查 mock 字段与接口类型一致。
- 运行相关测试或项目约定的类型检查命令。
