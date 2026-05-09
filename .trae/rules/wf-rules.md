# 前端编码&工程规范 (wf框架)

## 组件规范
- 组件名: PascalCase（`UserProfile.vue`）
- 基础组件以 `Base` 前缀
- Props 必须定义 type 和 default

## 状态管理
- 组件通信: props down, events up
- 复杂状态用 Vuex

## 样式规范
- 使用 scoped CSS + BEM 命名
- `v-for` 必须配合 `:key`
- 禁止 `v-if` 和 `v-for` 同元素
