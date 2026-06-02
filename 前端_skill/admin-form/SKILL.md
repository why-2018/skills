---
name: admin-form
description: 生成和维护基于 Vue3 + TypeScript + Element Plus 的后台表单。Use when creating admin forms, edit dialogs, search forms, Element Plus Form validation, form submit/reset flows, or typed form models.
---

# Admin Form

## Quick Start

生成后台表单时：

1. 先确认 Element Plus 是否已安装并在 `src/main.ts` 注册。
2. 使用 `<script setup lang="ts">` 和 Element Plus 的类型导入。
3. 表单模型、校验规则、提交参数都要有明确类型。

## Form Pattern

```vue
<script setup lang="ts">
import { reactive, ref } from 'vue';
import type { FormInstance, FormRules } from 'element-plus';

interface FormModel {
  name: string;
  status: 'enabled' | 'disabled';
}

const formRef = ref<FormInstance>();
const form = reactive<FormModel>({
  name: '',
  status: 'enabled',
});

const rules: FormRules<FormModel> = {
  name: [{ required: true, message: '请输入名称', trigger: 'blur' }],
};

const submit = async () => {
  await formRef.value?.validate();
};
</script>
```

## Guidelines

- 使用 `el-form`、`el-form-item`、`el-input`、`el-select`、`el-date-picker` 等 Element Plus 组件。
- `rules` 和 `prop` 字段必须与表单模型字段一致。
- 提交前统一 `validate()`；提交中禁用按钮并显示 loading。
- 编辑表单接收初始值时，避免直接修改 props；复制到本地 `reactive` 模型。
- 重置表单使用 `resetFields()`，同时处理自定义字段的初始值。
- 复杂表单拆成小组件，但提交出口保持清晰。

## Output Contract

- 弹窗表单优先通过 `emit('submit', payload)` 把结果交给父组件。
- 页面内表单可以直接调用 API 或 Store action。
- 提交 payload 应只包含接口需要的字段，不把 Element Plus 内部状态传给 API。
