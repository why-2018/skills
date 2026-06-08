---
name: search-filter-form
description: 维护后台搜索筛选表单、默认值、重置、折叠展开、字典选项和时间范围转换。Use when implementing query forms, filter bars, search reset behavior, date range filters, select dictionaries, or collapsible admin search panels.
---

# Search Filter Form

## Quick Start

处理搜索筛选时：

1. 先确认页面已有的查询参数类型、列表请求函数和默认搜索条件。
2. 把搜索表单模型与接口查询参数分开；提交前再转换为空值、时间范围、枚举值和分页字段。
3. 搜索动作负责回到第一页并刷新列表；重置动作负责恢复默认值、清理校验和重新查询。
4. 选项数据来自字典、枚举或接口时，先复用项目已有字典加载方式。

## Must Do

- 搜索字段的默认值要集中定义，避免 reset 后和初次加载不一致。
- 空字符串、空数组、`null`、`undefined` 的提交规则要与项目 API 约定一致。
- 日期范围必须明确开始/结束字段、格式、时区和结束时间是否补到当天末尾。
- 折叠搜索区时不能丢失已填写条件；展开后状态要保持一致。
- 远程选项要处理 loading、失败反馈、空选项和回显。
- 搜索表单不要持有表格数据；列表刷新由页面统一方法负责。

## Verification

- 检查初始查询、输入搜索、回车搜索、重置、折叠展开和分页联动。
- 检查日期范围、枚举、多选、级联选择等字段提交给接口的最终参数。
- 修改表单和请求参数后运行项目约定的类型检查或构建命令。
