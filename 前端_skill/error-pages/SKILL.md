---
name: error-pages
description: 实现 403、404、500、空权限、网络错误等异常页面和回退导航。Use when adding frontend error pages, not-found routes, forbidden pages, server error views, network failure pages, or route fallback behavior.
---

# Error Pages

## Quick Start

处理异常页面时：

1. 先查路由配置、全局错误处理、现有空状态组件和布局容器。
2. 明确异常类型：无权限、页面不存在、服务异常、网络异常、登录失效或数据为空。
3. 异常页应给出可执行出口，例如返回首页、返回上一页、重新登录或重试。
4. 页面样式沿用项目后台布局，不做脱离系统风格的大型营销式页面。

## Must Do

- 404 路由要放在路由匹配末尾，避免吞掉有效动态路由。
- 403 要区分无菜单权限、无按钮权限和直接访问无权限页面。
- 500 或网络错误页要提供重试或回退，不应让用户停在死页面。
- 登录失效优先走统一鉴权流程，不在异常页里重复写 Token 清理。
- 异常页文案要短、明确，避免暴露接口细节或堆栈信息。
- 异常状态组件要支持局部使用和整页使用两种场景。

## Verification

- 检查未知路由、无权限路由、接口失败和网络失败。
- 检查返回、重试、重新登录等操作是否可用。
- 运行项目约定的类型检查或构建命令。
