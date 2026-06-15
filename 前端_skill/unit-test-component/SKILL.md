---
name: unit-test-component
description: 为前端组件、组合函数、Store 和工具函数补充单元测试。Use when adding Vitest, Vue Test Utils, component tests, composable tests, Pinia tests, utility function tests, or regression coverage.
---

# Unit Test Component

## Quick Start

补充单元测试时：

1. 先查项目测试框架、测试目录、mock 写法、组件挂载工具和已有断言风格。
2. 确认被测对象的输入、输出、用户事件、异步请求、边界值和错误分支。
3. 优先覆盖稳定业务行为，不测试组件库内部实现或易碎 DOM 细节。
4. 新增测试文件命名沿用项目约定，例如 `*.test.ts` 或 `*.spec.ts`。

## Must Do

- 组件测试要覆盖关键渲染、事件 emit、loading、禁用态、空状态和错误提示。
- 组合函数测试要覆盖初始状态、状态变化、异步成功失败和清理逻辑。
- Store 测试要隔离 Pinia 实例，并 mock API 模块或外部依赖。
- 表单测试要覆盖校验通过、校验失败、提交 loading 和重复提交保护。
- 涉及时间、随机数、路由、浏览器 API 时要使用可控 mock。
- 不要把测试写成实现快照；断言用户能观察到的结果和对外契约。

## Verification

- 运行项目单元测试命令或最小相关测试。
- 检查测试在重复运行时稳定，不依赖执行顺序。
- 如果无法运行测试，说明缺失依赖或命令，并保留可读测试用例。
