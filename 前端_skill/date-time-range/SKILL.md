---
name: date-time-range
description: 处理日期范围、时间区间、快捷选项、时区转换和接口参数格式。Use when implementing date range pickers, time filters, timezone conversion, quick date presets, or backend date parameter mapping.
---

# Date Time Range

## Quick Start

处理日期时间范围时：

1. 先查项目使用的日期库、组件库日期控件、接口时间格式和时区约定。
2. 明确字段含义：日期、日期时间、自然日、业务日、UTC 时间或本地时间。
3. 将 UI 显示值、组件绑定值和接口参数值分开处理。
4. 对搜索表单优先提供默认值、快捷选项、清空和重置行为。

## Must Do

- 开始时间和结束时间要处理边界，例如当天 00:00:00 到 23:59:59。
- 接口参数格式必须统一，不在多个页面重复拼接字符串。
- 清空范围时要同步清理两个端点参数。
- 快捷选项要定义清楚是否包含今天、最近 7 天、自然周或滚动区间。
- 时区转换要集中处理，避免前后端各自隐式转换造成偏差。
- 不要直接用展示文案作为提交值。

## Verification

- 检查默认范围、快捷选项、清空、重置、跨月跨年和非法范围。
- 检查接口参数、回显、时区差异和边界秒。
- 运行项目约定的类型检查或构建命令。
