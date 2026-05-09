---
name: backend
description: 启动后端设计与开发工作流（基于 cpf 框架）
parameters:
  - name: version
    description: 设计文档版本号
    type: string
    required: false
  - name: database
    description: 数据库类型 (mysql/oceanbase)
    type: string
    required: false
---

# 后端工作流

## 触发条件

当设计评审通过后触发。

## 工作流步骤

### 步骤1: 接口实现
- 基于 API 设计实现 Controller
- 实现 Service 层逻辑

### 步骤2: 数据库实现
- 实现 Entity
- 实现 Mapper
- 编写数据库脚本

### 步骤3: 业务逻辑
- 实现核心业务逻辑
- 处理异常和边界情况

### 步骤4: 单元测试
- 编写单元测试
- 确保覆盖率 ≥80%

### 步骤5: 代码评审
- 提交代码评审
- 修复评审问题

## 输出

- `5backend/src/` - 后端源代码
- `3db/{版本号}/update_db_{版本号}.sql` - 数据库变更脚本
- `3db/{版本号}/rollback_db_{版本号}.sql` - 数据库回退脚本
- `3db/{版本号}/impact-analysis.md` - 变更影响分析

## 质量门禁

- 代码规范检查通过
- 单元测试覆盖率 ≥80%
- 接口测试通过
- 代码评审通过（0 Critical, 0 Major）
