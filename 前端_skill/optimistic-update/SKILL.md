---
name: optimistic-update
description: 实现乐观更新、回滚、并发提交保护和失败恢复。Use when making UI update before API success, toggling status optimistically, reordering items, liking/favoriting, or handling rollback on failure.
---

# Optimistic Update

## Quick Start

处理乐观更新时：

1. 先确认操作是否适合乐观更新：成功率高、回滚容易、失败影响可控。
2. 查列表状态、详情状态、Store、请求封装和错误提示机制。
3. 保存更新前快照，提交失败时能恢复 UI 和相关派生数据。
4. 对高风险操作优先使用保守提交，不强行乐观。

## Must Do

- 乐观更新前要记录原始状态，包含列表项、详情、计数和选择状态。
- 失败后必须回滚，并给用户明确提示。
- 并发提交要有顺序保护，避免较早失败覆盖较晚成功。
- 删除、支付、权限变更等高风险操作不要默认乐观更新。
- 服务端返回最终数据时要以服务端为准重新同步。
- 回滚逻辑要覆盖分页、筛选、排序和缓存副本。

## Verification

- 检查成功、失败、连续点击、并发提交和刷新后状态。
- 检查列表、详情、计数、缓存和消息提示是否同步。
- 运行项目约定的类型检查或构建命令。
