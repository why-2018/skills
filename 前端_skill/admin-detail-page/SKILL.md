---
name: admin-detail-page
description: 实现后台详情页、分组展示、状态标签、关联数据、操作按钮和返回逻辑。Use when building admin detail pages, read-only business views, grouped fields, related records, status displays, or detail action flows.
---

# Admin Detail Page

## Quick Start

生成详情页时：

1. 先查相似详情页、字段展示组件、状态标签、字典格式化和返回导航写法。
2. 确认详情接口、路由参数、字段分组、关联列表、操作按钮和权限规则。
3. 页面状态至少包含详情数据、loading、错误态、刷新方法和返回逻辑。
4. 编辑、删除、审核等操作优先复用已有弹窗、确认和 API 模块。

## Must Do

- 路由参数必须校验，缺失或非法时进入错误态或返回列表。
- 字段展示要处理空值、日期、金额、枚举、长文本和敏感字段脱敏。
- 详情加载失败要有重试入口，不能只留下空白页面。
- 操作按钮要考虑权限、业务状态、二次确认、loading 和操作后刷新。
- 关联数据要区分随详情一起返回、单独分页请求和懒加载。
- 返回逻辑要尊重来源页面，无法回退时跳到稳定列表路由。

## Verification

- 检查正常详情、缺失 ID、接口失败、空字段和关联数据。
- 检查编辑、删除、审核、刷新和返回。
- 运行项目约定的类型检查或构建命令。
