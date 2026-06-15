---
name: layout-shell
description: 实现和维护后台主布局、顶部栏、侧边栏、菜单、面包屑、页签、内容区和响应式收起。Use when creating admin layouts, shell components, sidebars, headers, breadcrumbs, route tabs, keep-alive areas, or layout-level navigation.
---

# Layout Shell

## Quick Start

处理后台布局时：

1. 先查 `src/layouts/`、`src/components/`、`src/router/` 和已有菜单、面包屑、页签实现。
2. 明确布局区域：侧边栏、顶部栏、内容区、面包屑、页签、用户菜单和全局状态入口。
3. 布局组件只处理导航壳、全局交互和 `<router-view>`；业务页面内容不要写进布局。
4. 菜单、面包屑、页签都应从路由或统一菜单数据派生，避免维护多份结构。

## Must Do

- 侧边菜单选中态要和当前路由同步，刷新页面后仍正确。
- 折叠侧边栏、移动端窄屏和长菜单要有可用交互。
- 面包屑和页签要处理隐藏路由、动态标题、详情页标题和关闭当前页。
- 内容区 loading、错误边界或缓存策略要与页面级状态分清边界。
- 用户菜单中的退出登录要清理鉴权状态、路由权限和缓存。
- 布局样式使用项目已有变量或组件库主题，不写难维护的全局覆盖。

## Verification

- 检查刷新、路由跳转、菜单折叠、页签关闭、面包屑点击和退出登录。
- 检查不同权限菜单、长标题、窄屏和内容滚动。
- 修改布局后运行项目约定的类型检查或构建命令。
