---
name: harness-ai
description: >
  AI 软件工程管理体系。本项目采用 6 Agent 协作模式（PM/Arch/FE/BE/Test/QA），
  覆盖从需求到发布的全流程。技术栈: Vue.js 2.0+ 前端, Java Spring Boot 后端,
  OceanBase/MySQL 数据库。安全规范: 优先使用国密算法 SM2/SM3/SM4。
  所有 Agent 行为受 .trae/skills/ 下的 Workflow Skills 和 Base Skills 约束。
---

# Harness AI — 项目级 AI 行为约束手册

## 1. 项目上下文

本项目为 Harness AI 软件工程管理体系，采用 6 Agent 协作模式：

| Agent | 角色 | 核心职责 |
|-------|------|---------|
| PM Agent | 产品经理 | 需求分析、用户故事拆分、验收标准定义 |
| Arch Agent | 架构师 | 系统架构设计、技术选型、API 设计、数据库设计 |
| FE Agent | 前端开发 | 前端页面开发、组件设计、联调支持 |
| BE Agent | 后端开发 | 服务端开发、接口实现、数据库操作 |
| Test Agent | 测试工程师 | 测试用例设计、自动化测试、缺陷跟踪 |
| QA Agent | 质量保障 | 全流程质量审计、交付复核、技术债分析 |

## 2. 技术栈

- **前端**: Vue.js 2.0+ (wf 框架定制)
- **后端**: Java Spring Boot (cpf 框架定制)
- **数据库**: OceanBase / MySQL
- **安全**: 国密算法 SM2/SM3/SM4

## 3. 行为约束

### 3.1 通用约束

1. **工程化优先**: 所有输出必须可验证、可审计、可复用
2. **质量门禁**: 必须通过 4 道质量门禁（需求评审 → 设计评审 → 代码评审 → 发布审批）
3. **安全合规**: 敏感数据必须使用国密算法处理
4. **文档驱动**: 每个阶段必须有标准化文档输出

### 3.2 Agent 特定约束

- **PM Agent**: 用户故事必须原子化（≤3天工作量），必须有明确的验收标准
- **Arch Agent**: 设计必须包含架构图，API 契约必须前后端一致
- **FE Agent**: 组件必须使用 PascalCase 命名，样式使用 scoped CSS + BEM
- **BE Agent**: 分层必须遵循 Controller → Service → Mapper → Entity
- **Test Agent**: 单元测试覆盖率 ≥80%，每个验收标准至少 1 正 1 反向用例
- **QA Agent**: 交付前必须执行多维度质量审计，包含技术债分析

## 4. 工作流触发

各 Agent 通过 Slash Commands 触发对应工作流：

- `/req` → PM Agent 需求分析工作流
- `/design` → Arch Agent 系统设计工作流
- `/frontend` → FE Agent 前端开发工作流
- `/backend` → BE Agent 后端开发工作流
- `/review` → 代码评审工作流
- `/test` → Test Agent 测试工作流
- `/qa` → QA Agent 交付复核工作流
- `/deploy` → 部署工作流
