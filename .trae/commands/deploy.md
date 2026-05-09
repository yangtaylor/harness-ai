---
name: deploy
description: 启动部署工作流
parameters:
  - name: version
    description: 部署版本号
    type: string
    required: true
  - name: env
    description: 部署环境 (dev/staging/production)
    type: string
    required: true
---

# 部署工作流

## 触发条件

当交付复核通过后触发。

## 工作流步骤

### 步骤1: 部署准备
- 确认版本号
- 确认目标环境
- 准备部署包

### 步骤2: 数据库部署
- 执行数据库变更脚本
- 验证数据库状态

### 步骤3: 应用部署
- 部署前端应用
- 部署后端服务

### 步骤4: 健康检查
- 执行健康检查
- 验证服务状态

### 步骤5: 监控配置
- 配置监控告警
- 确认日志收集

## 输出

- `7ops/{版本号}/deploy.md` - 部署手册
- `7ops/{版本号}/docker-compose.yml` - 容器编排

## 质量门禁

- 部署包完整性检查通过
- 数据库脚本执行成功
- 健康检查通过
- 监控配置完成
