# Harness AI — AI 软件工程管理体系

> **版本**: v2.0
> **核心理念**: 工程化而非简单自动化 — AI 与人机协同构建可验证、可审计、可复用的工作流

## 项目简介

Harness AI 是一套完整的 **AI 软件工程管理体系**，通过 Agent + Skills + Slash Commands 的方式，将 AI 能力与软件工程原则深度融合，构建从想法到产品的全流程工程化开发体系。

核心价值在于**工程化而非简单自动化**，重点是围绕 AI 及人机协同构建可验证、可审计、可复用的工作流，而非追求 100% 代码自动生成。

## 核心特性

- **6 大 Agent 协作**: PM / Arch / FE / BE / Test / QA，覆盖从需求到发布的完整软件生命周期
- **Workflow Skills**: 每个阶段都有标准化工作流 Skill，确保输出质量一致
- **Base Skills**: 编码规范、文档模板等基础能力，作为所有 Agent 的行为约束
- **国密安全规范**: 优先使用 SM2/SM3/SM4 国密算法，满足国内合规要求
- **质量门禁**: 4 道质量门禁（需求评审 → 设计评审 → 代码评审 → 发布审批）

## 项目结构

```
{project_workspace}/
├── .trae/
│   ├── skills/           # Workflow Skills & Base Skills
│   │   ├── 10-req-workflow/
│   │   ├── 20-design-workflow/
│   │   ├── 30-frontend-workflow/
│   │   ├── 40-backend-workflow/
│   │   ├── 50-review-workflow/
│   │   ├── 60-test-workflow/
│   │   ├── 80-qa-workflow/
│   │   ├── req-pack/
│   │   ├── design-pack/
│   │   ├── db-pack/
│   │   ├── wf-pack/
│   │   ├── cpf-pack/
│   │   ├── test-pack/
│   │   └── qa-pack/
│   ├── commands/         # Slash Commands 定义
│   │   ├── req.md
│   │   ├── design.md
│   │   ├── frontend.md
│   │   ├── backend.md
│   │   ├── review.md
│   │   ├── test.md
│   │   ├── qa.md
│   │   └── deploy.md
│   └── rules/            # 编码规范 & 工程规范
│       ├── req-rules.md
│       ├── design-rules.md
│       ├── api-rules.md
│       ├── db-rules.md
│       ├── wf-rules.md
│       ├── cpf-rules.md
│       └── test-rules.md
├── 1req/                 # 阶段1：需求管理目录（按迭代隔离）
├── 2design/              # 阶段2：设计文档目录
│   ├── frontend/
│   └── backend/
├── 4frontend/            # 阶段4：前端代码目录
├── 5backend/             # 阶段5：后端代码目录
├── 6test/                # 阶段6：测试用例目录
├── 7ops/                 # 阶段7：运维部署目录
└── 8qa/                  # 阶段8：质量保障目录
    └── archives/         # 归档目录
```

## Agent 协作模式

| Agent | 角色 | 核心职责 |
|-------|------|---------|
| PM Agent | 产品经理 | 需求分析、用户故事拆分、验收标准定义 |
| Arch Agent | 架构师 | 系统架构设计、技术选型、API 设计、数据库设计 |
| FE Agent | 前端开发 | 前端页面开发、组件设计、联调支持 |
| BE Agent | 后端开发 | 服务端开发、接口实现、数据库操作 |
| Test Agent | 测试工程师 | 测试用例设计、自动化测试、缺陷跟踪 |
| QA Agent | 质量保障 | 全流程质量审计、交付复核、技术债分析 |

## 快速开始

1. **需求阶段**: 使用 `/req` 命令启动需求分析工作流
2. **设计阶段**: 使用 `/design` 命令启动系统设计工作流
3. **开发阶段**: 使用 `/frontend` 或 `/backend` 命令启动开发工作流
4. **测试阶段**: 使用 `/test` 命令启动测试工作流
5. **评审阶段**: 使用 `/review` 命令启动代码评审工作流
6. **交付阶段**: 使用 `/qa` 命令启动交付复核工作流

## 技术栈

- **前端**: Vue.js 2.0+ (wf 框架定制)
- **后端**: Java Spring Boot (cpf 框架定制)
- **数据库**: OceanBase / MySQL
- **安全**: 国密算法 SM2/SM3/SM4

## 文档

- [AI软件工程管理体系设计方案](AI软件工程管理体系设计方案.md)
- [目录规划](目录规划.md)
- [Agent 行为约束手册](Agents.md)
- [PM Agent 手册](PM_Agent.md)
- [Arch Agent 手册](Arch_Agent.md)
- [FE Agent 手册](FE_Agent.md)
- [BE Agent 手册](BE_Agent.md)
- [Test Agent 手册](Test_Agent.md)
- [QA Agent 手册](QA_Agent.md)

## 许可证

MIT License
