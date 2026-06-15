---
name: page-skeleton
description: 快速生成标准前端页面骨架，包括标题区、操作区、内容区和基础状态。Use when creating new Vue pages, admin page shells, standard page layout, toolbar/content structure, or reusable page scaffolds.
---

# Page Skeleton

## Quick Start

生成页面骨架时：

1. 先查 `src/pages/` 中相似页面，沿用目录、命名、布局组件和样式粒度。
2. 确认页面职责、路由入口、标题、主操作、内容区域、权限和初始加载方式。
3. 先搭出可运行页面，再接入列表、表单、详情或图表等具体模块。
4. 骨架只承载布局和基础状态，不提前发明业务抽象。

## Must Do

- 页面应包含清晰的标题区、主操作区、内容区和必要的 loading/empty/error 状态。
- 主操作按钮要考虑权限、loading、禁用态和重复点击。
- 页面级状态命名要清楚，避免把所有状态堆进一个松散对象。
- 样式优先使用项目已有布局类或组件库间距，不散落大量一次性魔法数。
- 新页面要同步路由、懒加载组件、页面标题和必要权限元信息。
- 不要创建只有占位文案、没有真实工作流的空页面。

## Verification

- 检查路由可访问、页面标题、主操作、加载态和空态。
- 检查窄屏下标题与操作区不会重叠。
- 运行项目约定的类型检查或构建命令。
