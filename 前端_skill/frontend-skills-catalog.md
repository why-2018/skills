# 前端 Skills 常用场景清单

这个文件用于规划前端项目里最常用、最值得沉淀成 Cursor Skill 的场景。后续可以按优先级把其中某一项拆成独立目录，例如 `.cursor/skills/vue-api-module/SKILL.md`。

## 拆分原则

- 一个 Skill 只解决一个高频、可重复的前端工作流。
- Skill 名称使用小写短横线，例如 `admin-crud-page`。
- `description` 要同时写清楚“做什么”和“什么时候触发”。
- 优先沉淀项目内反复出现的场景，而不是抽象的知识点。
- 如果 Skill 依赖项目约定，应写清楚目录、命名、验证命令和禁止事项。

## 已有 Skills

- `vue3-vite-stack`：Vue3 + Vite + TypeScript 项目通用实现约定。
- `vue-router-page`：新增和维护 Vue Router 页面、路由、懒加载页面组件。
- `vue-api-module`：维护业务 API 模块、请求类型、响应类型和接口封装。
- `vue-pinia-store`：维护 Pinia Store、跨页面状态和异步 action。
- `admin-crud-page`：生成后台列表、搜索、表格、分页、弹窗和操作流。
- `admin-form`：生成后台表单、编辑弹窗、校验规则和提交逻辑。
- `request-client`：维护请求客户端、拦截器、鉴权 Header、统一错误和响应解包。
- `admin-list-page`：生成后台列表页、搜索区、表格、分页、loading 和刷新流。
- `search-filter-form`：维护搜索筛选表单、默认值、重置、折叠展开和查询参数转换。
- `data-table`：维护表格列、操作列、选择列、排序、空状态和自定义渲染。
- `pagination-flow`：维护分页请求、页码回退、搜索回到第一页和 total 同步。
- `form-validation`：维护表单校验规则、自定义 validator、异步校验和错误定位。
- `dialog-form`：实现弹窗表单的打开关闭、props 回显、emit 提交和状态清理。
- `router-guard-auth`：实现登录态校验、路由守卫、Token 过期和跳转回源页面。
- `permission-routing`：实现动态菜单、权限路由、按钮权限、角色差异和无权限回退。
- `layout-shell`：实现后台主布局、顶部栏、侧边栏、菜单、面包屑和页签。
- `loading-empty-error-state`：统一 loading、空数据、错误重试、骨架屏和局部刷新状态。
- `import-export`：实现 Excel/CSV 导入导出、模板下载、文件校验和错误明细。
- `upload-file`：实现文件上传、图片上传、大小类型限制、预览、删除和失败重试。
- `performance-optimization`：排查首屏慢、重复渲染、大列表卡顿、请求瀑布和 bundle 体积。
- `unit-test-component`：为组件、组合函数、Store 和工具函数补充单元测试。
- `e2e-user-flow`：为登录、CRUD、表单提交、权限跳转等关键链路补充端到端测试。
- `security-frontend`：检查 XSS、开放跳转、敏感信息暴露、Token 存储和上传安全。
- `observability-frontend`：接入前端错误监控、性能指标、用户行为日志和接口失败追踪。
- `page-skeleton`：快速生成标准页面骨架，包括标题区、操作区、内容区和基础状态。
- `error-pages`：实现 403、404、500、空权限、网络错误等异常页面和回退导航。
- `request-error-handling`：统一处理接口失败、业务错误码、登录失效、重试、用户提示和日志。
- `admin-detail-page`：实现后台详情页、分组展示、状态标签、关联数据和返回逻辑。
- `batch-actions`：实现批量删除、批量启停、批量导出、选择校验和二次确认。
- `feedback-message`：规范成功、失败、警告、确认弹窗、通知和表单错误提示。
- `mock-data-contract`：维护 mock 数据、接口契约、测试夹具和前后端联调占位数据。
- `project-bootstrap`：初始化前端项目结构、基础目录、入口文件、全局样式和默认配置。
- `env-config`：维护 `.env`、构建环境变量、接口地址和开发/测试/生产环境差异。
- `vite-config`：维护 Vite 插件、代理、构建配置、静态资源路径和开发服务器配置。
- `typescript-strictness`：补充和修复 TypeScript 类型、接口模型、泛型和严格模式错误。
- `path-alias-config`：配置和排查路径别名，保持 `vite.config.ts`、`tsconfig`、IDE 解析一致。
- `lint-format-build`：处理 ESLint、Prettier、Stylelint、构建失败和格式化规则冲突。

## 前端 Skills 候选清单

### 工程初始化与项目规范

- `project-bootstrap`：初始化前端项目结构、基础目录、入口文件、全局样式和默认配置。
- `dependency-management`：安装、替换、升级前端依赖，并检查包管理器、版本冲突和引入成本。
- `env-config`：维护 `.env`、构建环境变量、接口地址、开发/测试/生产环境差异。
- `vite-config`：维护 Vite 插件、代理、构建配置、静态资源路径和开发服务器配置。
- `typescript-strictness`：补充和修复 TypeScript 类型、接口模型、泛型和严格模式错误。
- `path-alias-config`：配置和排查路径别名，保持 `vite.config.ts`、`tsconfig`、IDE 解析一致。
- `lint-format-build`：处理 ESLint、Prettier、Stylelint、构建失败和格式化规则冲突。
- `frontend-code-review`：审查前端改动的正确性、可维护性、交互状态、类型和测试缺口。

### 页面、路由与布局

- `layout-shell`：实现后台主布局、顶部栏、侧边栏、面包屑、标签页和内容区域。
- `router-guard-auth`：实现登录态校验、路由守卫、Token 过期、跳转回源页面。
- `permission-routing`：实现动态菜单、权限路由、按钮权限、角色差异和隐藏规则。
- `page-skeleton`：快速生成标准页面骨架，包括标题区、操作区、内容区和基础状态。
- `error-pages`：实现 403、404、500、空权限、网络错误等异常页面和回退导航。
- `responsive-page`：处理移动端、自适应布局、断点、栅格和窄屏交互。
- `breadcrumb-tabs`：维护面包屑、页签缓存、关闭页签、刷新当前页和路由标题同步。

### API、请求与状态管理

- `request-client`：封装请求实例、拦截器、超时、统一错误、鉴权 Header 和响应解包。
- `api-module`：创建业务接口模块、请求参数类型、响应类型、分页模型和导出规范。
- `request-error-handling`：处理接口失败、业务错误码、登录失效、重试、用户提示和日志。
- `pinia-store`：创建业务 Store、状态模型、getter、action、持久化和重置逻辑。
- `cache-and-refresh`：实现列表缓存、详情缓存、刷新策略、失效策略和重复请求合并。
- `optimistic-update`：实现乐观更新、回滚、并发提交保护和失败恢复。
- `websocket-sse`：接入 WebSocket 或 SSE，处理连接、重连、心跳、消息分发和页面卸载。

### 后台 CRUD 与数据管理

- `admin-list-page`：生成后台列表页，包含搜索区、表格、分页、loading 和刷新。
- `admin-crud-dialog`：实现新增、编辑、查看弹窗，处理打开、回显、提交、关闭和清理。
- `admin-detail-page`：实现详情页、分组展示、状态标签、关联数据和返回逻辑。
- `search-filter-form`：实现搜索表单、重置、折叠展开、默认值、字典选项和时间范围。
- `data-table`：维护表格列、操作列、选择列、固定列、空状态、排序和自定义渲染。
- `pagination-flow`：处理分页请求、页码回退、搜索回到第一页、pageSize 变化和总数同步。
- `batch-actions`：实现批量删除、批量启停、批量导出、选择校验和二次确认。
- `import-export`：实现 Excel/CSV 导入导出、模板下载、文件校验、进度提示和错误明细。
- `tree-table-management`：实现树表格、层级数据、懒加载、展开状态和父子级操作。

### 表单与输入场景

- `form-validation`：维护表单校验规则、自定义 validator、异步校验和错误定位。
- `dynamic-form`：根据配置或接口动态渲染表单项、联动显隐、默认值和提交转换。
- `multi-step-form`：实现分步表单、步骤校验、草稿保存、上一步/下一步和最终提交。
- `dialog-form`：实现弹窗表单的 props 回显、emit 提交、loading、关闭确认和状态清理。
- `inline-edit-table`：实现表格行内编辑、单元格校验、保存取消、批量提交和脏数据提示。
- `date-time-range`：处理日期范围、时间区间、快捷选项、时区转换和接口参数格式。
- `upload-file`：实现文件上传、图片上传、大小类型限制、预览、删除和失败重试。
- `rich-text-editor`：接入富文本编辑器，处理内容回显、图片上传、XSS 风险和提交格式。
- `cascader-tree-select`：处理级联选择、树选择、懒加载节点、回显路径和半选状态。

### 组件、交互与体验

- `component-extraction`：从页面中抽取可复用组件，设计 props、emits、slots 和类型。
- `modal-drawer-flow`：实现弹窗、抽屉、关闭确认、嵌套交互和焦点管理。
- `loading-empty-error-state`：统一 loading、空数据、错误重试、骨架屏和局部刷新状态。
- `feedback-message`：规范成功、失败、警告、确认弹窗、通知和表单错误提示。
- `theme-dark-mode`：实现主题变量、暗色模式、Element Plus 主题覆盖和本地偏好保存。
- `i18n-frontend`：接入国际化、语言包、日期数字格式、本地语言切换和缺失 key 检查。
- `accessibility-ui`：改善键盘访问、语义标签、ARIA、焦点顺序、颜色对比和可读提示。
- `drag-drop-sortable`：实现拖拽排序、树节点拖拽、跨列表移动、排序保存和回滚。
- `chart-dashboard`：实现图表卡片、统计面板、筛选联动、加载状态和自适应尺寸。

### 性能、测试与上线质量

- `performance-optimization`：排查首屏慢、重复渲染、大列表卡顿、请求瀑布和 bundle 体积。
- `code-splitting`：处理路由懒加载、组件懒加载、依赖拆包、预加载和构建产物分析。
- `image-asset-optimization`：优化图片压缩、懒加载、占位图、响应式图片和静态资源路径。
- `unit-test-component`：为组件、组合函数、Store 和工具函数补充单元测试。
- `e2e-user-flow`：为登录、CRUD、表单提交、权限跳转等关键链路补充端到端测试。
- `mock-data-contract`：维护 mock 数据、接口契约、测试夹具和前后端联调占位数据。
- `security-frontend`：检查 XSS、开放跳转、敏感信息暴露、Token 存储和上传安全。
- `observability-frontend`：接入前端错误监控、性能指标、用户行为日志和接口失败追踪。
- `release-checklist`：上线前检查构建、环境变量、路由访问、权限、接口地址和回滚点。

## 优先级建议

- 第一批（已创建）：`request-client`、`admin-list-page`、`search-filter-form`、`data-table`、`pagination-flow`、`form-validation`、`dialog-form`。
- 第二批（已创建）：`router-guard-auth`、`permission-routing`、`layout-shell`、`loading-empty-error-state`、`import-export`、`upload-file`。
- 第三批（2026-06-15 已创建）：`performance-optimization`、`unit-test-component`、`e2e-user-flow`、`security-frontend`、`observability-frontend`。
- 第四批（2026-06-15 已创建）：`page-skeleton`、`error-pages`、`request-error-handling`、`admin-detail-page`、`batch-actions`、`feedback-message`、`mock-data-contract`。
- 第五批（2026-06-15 已创建）：`project-bootstrap`、`env-config`、`vite-config`、`typescript-strictness`、`path-alias-config`、`lint-format-build`。
- 第六批（下周建议）：`dynamic-form`、`multi-step-form`、`inline-edit-table`、`date-time-range`、`rich-text-editor`、`cascader-tree-select`。
- 第七批（下周建议）：`component-extraction`、`modal-drawer-flow`、`theme-dark-mode`、`i18n-frontend`、`accessibility-ui`、`drag-drop-sortable`、`chart-dashboard`。
- 第八批（下周建议）：`dependency-management`、`cache-and-refresh`、`optimistic-update`、`websocket-sse`、`code-splitting`、`image-asset-optimization`、`release-checklist`。

## 单个 Skill 模板

```markdown
---
name: skill-name
description: 简短说明该 Skill 做什么。Use when the user asks to handle specific trigger terms or common frontend workflow.
---

# Skill Title

## Quick Start

1. 先查项目中已有相似实现。
2. 沿用项目目录、类型、组件库、状态管理和请求封装。
3. 修改后运行项目约定的类型检查或构建命令。

## Must Do

- 写清楚输入、输出、状态流和错误处理。
- 复用已有工具和组件，不为单个页面发明新封装。
- 涉及用户操作时必须考虑 loading、失败反馈和重复提交。
```
