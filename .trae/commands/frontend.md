---
name: frontend
description: 启动前端设计与开发工作流（基于 wf 框架）
parameters:
  - name: version
    description: 设计文档版本号
    type: string
    required: false
---

# 前端工作流

## 触发条件

当设计评审通过后触发。

## 工作流步骤

### 步骤1: 组件设计
- 基于 UI 设计文档设计组件结构
- 定义组件 Props 和 Events

### 步骤2: 页面开发
- 实现前端页面
- 实现可复用组件

### 步骤3: 状态管理
- 实现 Vuex store
- 处理复杂状态逻辑

### 步骤4: 接口联调
- 与后端进行接口联调
- 处理异常情况

### 步骤5: 代码评审
- 提交代码评审
- 修复评审问题

## 输出

- `4frontend/src/` - 前端源代码

## 质量门禁

- 代码规范检查通过
- 组件可复用性检查通过
- 联调测试通过
- 代码评审通过（0 Critical, 0 Major）
