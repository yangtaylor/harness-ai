---
name: wf-template
description: >
  wf 框架（Vue2定制）前端编码规范模板 Skill。
  当进行前端开发或前端代码评审时使用此 Skill。
---

# wf 框架前端规范

## 组件模板

```vue
<template>
  <div class="component-name">
    <!-- 组件内容 -->
  </div>
</template>

<script>
export default {
  name: 'ComponentName',
  props: {
    // Props 定义
    propName: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      // 响应式数据
    }
  },
  computed: {
    // 计算属性
  },
  watch: {
    // 监听器
  },
  created() {
    // 创建钩子
  },
  mounted() {
    // 挂载钩子
  },
  methods: {
    // 方法
  }
}
</script>

<style scoped>
/* 组件样式 */
.component-name {
  /* BEM 命名 */
}

.component-name__element {
  /* 元素 */
}

.component-name--modifier {
  /* 修饰符 */
}
</style>
```

## Vuex Store 模板

```javascript
// store/modules/moduleName.js
const state = {
  // 状态
}

const getters = {
  // 计算属性
}

const mutations = {
  // 同步变更
}

const actions = {
  // 异步操作
}

export default {
  namespaced: true,
  state,
  getters,
  mutations,
  actions
}
```

## API 服务模板

```javascript
// services/apiService.js
import request from '@/utils/request'

export function apiName(params) {
  return request({
    url: '/api/path',
    method: 'get',
    params
  })
}

export function apiName(data) {
  return request({
    url: '/api/path',
    method: 'post',
    data
  })
}
```

## 编码规范检查清单

- [ ] 组件名使用 PascalCase
- [ ] 基础组件以 Base 前缀
- [ ] Props 定义 type 和 default
- [ ] 使用 scoped CSS
- [ ] 使用 BEM 命名规范
- [ ] v-for 配合 :key
- [ ] 禁止 v-if 和 v-for 同元素
- [ ] 组件通信使用 props down, events up
- [ ] 复杂状态使用 Vuex
- [ ] API 请求统一封装
