---
name: chart-dashboard
description: 实现图表卡片、统计面板、筛选联动、加载状态和自适应尺寸。Use when building dashboards, chart cards, metrics panels, ECharts views, filter-linked charts, or responsive data visualization.
---

# Chart Dashboard

## Quick Start

处理图表面板时：

1. 先查项目图表库、统计卡片、筛选组件、接口模块和主题色板。
2. 明确指标口径、筛选条件、时间范围、刷新频率和空数据展示。
3. 图表配置和数据转换分开写，避免把接口字段直接塞进图表 option。
4. 首屏只加载必要图表，复杂面板考虑懒加载或分区加载。

## Must Do

- 指标名称、单位、口径和时间范围要清晰，避免图表看起来对但含义不明。
- 每个图表都要有 loading、空数据、错误重试和刷新状态。
- 筛选变化要同步所有相关图表，并避免重复请求风暴。
- 图表尺寸要随容器变化 resize，处理侧边栏折叠和窗口变化。
- 颜色要符合主题和可读性，同一状态在不同图表中保持一致。
- 不要在前端偷偷改变统计口径，必要计算要写清楚来源。

## Verification

- 检查加载、空数据、错误、筛选联动、刷新和窗口 resize。
- 检查单位、tooltip、图例、长标签和暗色主题。
- 运行项目约定的类型检查或构建命令。
