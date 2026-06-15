---
name: permission-routing
description: 实现和维护动态菜单、权限路由、按钮权限、角色差异、隐藏规则和无权限回退。Use when building permission routes, dynamic menus, role-based navigation, button permissions, route meta permissions, or frontend access control.
---

# Permission Routing

## Quick Start

处理权限路由时：

1. 先确认权限来源：后端菜单树、角色权限码、前端静态路由，或三者组合。
2. 查现有 `src/router/`、菜单组件、用户 Store、权限指令和按钮权限工具。
3. 明确路由记录、菜单项、按钮权限和页面权限之间的映射关系。
4. 动态路由生成应集中在一个流程内完成，避免页面组件各自判断路由权限。

## Must Do

- 路由 name、path、权限码和菜单 key 要稳定，避免刷新或缓存后无法匹配。
- 动态菜单必须过滤隐藏路由、无权限路由和不可访问子节点。
- 按钮权限要复用统一函数、指令或组件，不在模板里散落角色判断。
- 用户权限变化、退出登录、切换账号时必须重置动态路由和菜单缓存。
- 无权限访问页面要有明确回退，例如 403 页、首页或上一页。
- 不要只依赖前端权限保护敏感操作；接口仍需要后端鉴权。

## Verification

- 检查不同角色登录、刷新页面、直接输入路由、退出再登录和无权限访问。
- 检查菜单、面包屑、页签、按钮显隐与权限数据一致。
- 修改权限路由后运行项目约定的类型检查或构建命令。
