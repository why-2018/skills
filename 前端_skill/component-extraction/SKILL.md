---
name: component-extraction
description: 从页面中抽取可复用组件，设计 props、emits、slots 和类型。Use when refactoring duplicated Vue page blocks into reusable components, designing component APIs, slots, typed props, or local shared UI.
---

# Component Extraction

## Quick Start

抽取组件时：

1. 先确认重复逻辑是否真的跨页面复用，而不是单页内部临时拆分。
2. 查项目组件目录、命名方式、props/emits 写法、样式作用域和测试习惯。
3. 明确组件边界：展示、交互、数据请求、状态管理和业务规则分别放在哪里。
4. 优先抽取稳定 UI 和交互，不把未稳定业务流程提前固化。

## Must Do

- props 要小而明确，避免把整页状态对象直接传入。
- emits 要表达用户意图，例如 `submit`、`cancel`、`change`，不要泄露内部实现细节。
- 可变展示区域优先使用 slots，固定业务字段用 props。
- 组件内部不要直接依赖页面路由、全局 Store 或特定 API，除非它本来就是业务组件。
- 样式要局部化，并保持父容器可控制宽度、间距和布局。
- 抽取后原页面行为、权限、loading 和错误态不能退化。

## Verification

- 检查所有调用方的展示、事件、默认值、插槽和边界状态。
- 检查 props 类型、emits 类型和样式覆盖。
- 运行项目约定的类型检查或构建命令。
