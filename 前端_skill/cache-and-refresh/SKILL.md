---
name: cache-and-refresh
description: 实现列表缓存、详情缓存、刷新策略、失效策略和重复请求合并。Use when adding frontend cache, stale data refresh, request deduplication, list/detail cache, or keep-alive refresh behavior.
---

# Cache And Refresh

## Quick Start

处理缓存和刷新时：

1. 先查项目请求封装、Store、页面 keep-alive、列表刷新和已有缓存策略。
2. 明确缓存对象：列表、详情、字典、用户信息、权限或静态配置。
3. 定义缓存 key、生命周期、失效条件、强制刷新和并发请求合并规则。
4. 优先缓存低频变化数据，高频业务数据要谨慎避免陈旧。

## Must Do

- 缓存 key 必须包含影响结果的参数，例如分页、筛选、排序和用户身份。
- 修改、新增、删除后要失效相关列表和详情缓存。
- 重复请求合并要正确处理成功、失败和取消。
- 返回页面刷新要区分无需刷新、软刷新和强制重新请求。
- 缓存命中也要考虑 loading 表现和后台静默刷新。
- 不要缓存包含敏感信息或权限易变的数据，除非有明确失效策略。

## Verification

- 检查首次加载、缓存命中、参数变化、强制刷新和修改后失效。
- 检查并发请求、接口失败、返回页面和权限切换。
- 运行项目约定的类型检查或构建命令。
