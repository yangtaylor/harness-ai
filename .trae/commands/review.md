---
name: review
description: 启动代码评审工作流（集成安全扫描）
parameters:
  - name: scope
    description: 评审范围 (all/frontend/backend)
    type: string
    required: false
---

# 代码评审工作流

## 触发条件

当代码提交合并请求时触发。

## 工作流步骤

### 步骤1: 自动化检查
- 代码规范检查
- 安全扫描
- 静态分析

### 步骤2: 人工评审
- 评审代码逻辑
- 评审设计合理性
- 评审安全性

### 步骤3: 问题修复
- 修复评审发现的问题
- 重新提交评审

### 步骤4: 评审通过
- 确认所有问题已修复
- 批准合并

## 输出

- 代码评审报告
- 安全扫描报告

## 质量门禁

- 代码规范检查通过
- 安全扫描无 Critical/Major 问题
- 人工评审通过
- 0 Critical, 0 Major 缺陷
