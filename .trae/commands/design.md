---
name: design
description: 启动系统设计工作流，包含概要设计、详细设计、API设计、数据库设计
parameters:
  - name: version
    description: 设计文档版本号
    type: string
    required: false
---

# 系统设计工作流

## 触发条件

当需求评审通过后触发。

## 工作流步骤

### 步骤1: 架构设计
- 设计系统整体架构
- 技术选型
- 模块划分
- 输出架构图

### 步骤2: 详细设计
- 模块详细设计
- 接口定义
- 数据流设计

### 步骤3: API 设计
- 定义 RESTful API
- 设计请求/响应格式
- 定义错误码

### 步骤4: 数据库设计
- 设计数据模型
- 绘制 ER 图
- 定义索引策略

### 步骤5: 设计评审
- 组织设计评审
- 收集反馈并修订

## 输出

- `2design/frontend/{版本号}/ui-design.md` - UI设计文档
- `2design/frontend/{版本号}/component-lib.md` - 组件库规范
- `2design/backend/{版本号}/api-design.md` - API接口设计
- `2design/backend/{版本号}/db-design.md` - 数据库设计

## 质量门禁

- 架构合理性检查通过
- API 契约一致性检查通过
- 数据库设计规范性检查通过
- 设计评审通过
