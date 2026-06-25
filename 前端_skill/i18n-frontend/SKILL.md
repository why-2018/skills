---
name: i18n-frontend
description: 接入国际化、语言包、日期数字格式、本地语言切换和缺失 key 检查。Use when adding frontend i18n, locale files, language switching, translation keys, date/number formatting, or multilingual UI.
---

# I18n Frontend

## Quick Start

处理国际化时：

1. 先查项目 i18n 依赖、语言包目录、路由标题、组件库 locale 和格式化工具。
2. 明确支持语言、默认语言、切换入口、持久化方式和缺失 key 策略。
3. 文案从 UI 中抽离到语言包，业务枚举和接口文案按项目约定处理。
4. 日期、时间、数字、金额和复数规则要走格式化工具，不手写拼接。

## Must Do

- key 命名要稳定、分模块组织，避免用整句中文当 key。
- 语言切换要同步组件库 locale、日期库 locale、路由标题和页面缓存标题。
- 缺失翻译要能在开发环境暴露，生产环境有可接受兜底。
- 接口返回文案要区分后端已翻译和前端翻译码两种模式。
- 不要把变量插值和 HTML 混在未净化翻译内容里。
- 新增页面时同步所有目标语言或标注待翻译状态。

## Verification

- 检查语言切换、刷新保持、路由标题、组件库文案和格式化结果。
- 检查缺失 key、插值、长文本和不同语言下布局溢出。
- 运行项目约定的类型检查或构建命令。
