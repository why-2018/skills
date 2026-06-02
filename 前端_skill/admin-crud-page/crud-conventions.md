# CRUD Conventions

## Page Shape

- 搜索区使用 `reactive` 查询条件；包含查询、重置按钮。
- 操作区包含新增、批量操作、刷新；批量按钮依赖 selection。
- 表格区使用项目已有表格封装；没有封装时使用 `el-table`。
- 分页区使用项目已有分页封装；没有封装时使用 `el-pagination`。
- 新增/编辑弹窗复用同一个表单组件；表单校验遵循 `admin-form`。

## State Names

- 查询条件：`query`
- 列表数据：`tableData`
- 列表加载：`tableLoading`
- 选中行：`selection`
- 分页：`pagination`，包含 `page`、`pageSize`、`total`
- 弹窗显隐：`dialogVisible`
- 弹窗模式：`dialogMode`，使用 `create` 或 `edit`
- 提交加载：`submitLoading`

## API Rules

- 页面只调用 `src/api/modules/` 导出的语义化函数。
- API 模块必须导出列表查询参数、列表项、表单 payload、分页结果类型。
- GET 查询参数使用 `params`；POST/PUT/PATCH 请求体使用 typed payload。
- 列表接口返回分页时，页面必须同步 `tableData` 和 `pagination.total`。
- 不在页面里重复判断通用业务错误码；通用错误交给 `src/api/request.ts`。

## Element Plus Rules

- 删除、禁用、启用、重置、批量操作使用 `ElMessageBox.confirm`。
- 成功反馈使用 `ElMessage.success`。
- 页面自己捕获到的业务失败使用 `ElMessage.error` 或项目已有消息封装。
- 表格操作列固定到右侧；字段较长的列设置 `min-width`。
- 表格枚举展示优先使用项目已有字典/枚举；没有时在当前模块定义 typed map。

## Permission And Dictionary

- 先搜索项目是否存在权限指令、权限组件或按钮权限函数；存在时新增按钮必须接入。
- 先搜索项目是否存在字典、枚举、常量目录；存在时状态、类型、性别等选项必须复用。
- 未发现权限系统时，不要新增假的权限封装。
- 未发现字典系统时，只在业务模块内定义当前页面需要的枚举和展示映射。

## Refresh Rules

- 查询：设置 `pagination.page = 1` 后请求列表。
- 重置：清空 query，设置 `pagination.page = 1` 后请求列表。
- 分页变化：更新 `pagination.page` 或 `pagination.pageSize` 后请求列表。
- 新增/编辑成功：关闭弹窗，重置表单，请求列表。
- 删除成功：当前页只剩一条且不是第一页时，页码减一后请求列表。
