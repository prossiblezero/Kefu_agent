# Kefu Agent

面向安克全产品售后的轻量 Agent Harness。通过文本、图片、产品知识与服务历史，完成产品消歧、排障引导、反馈验证和人工升级接续。

**当前阶段：设计文档，尚未实现可运行应用。** 首版采用 Python／FastAPI、PostgreSQL + pgvector、Redis；保留受控工具、持久运行时、上下文管理和可更正记忆。Milvus、独立重排等按需求与评测结果再引入。

## 设计入口

1. [问题场景与整体架构](客服AgentHarness项目方案.md)
2. [Agent 主逻辑与运行时](design/第二步-Agent主逻辑与运行时.md)
3. [工具与 Skill](design/第三步-工具与Skill.md)
4. [权限与安全边界](design/第四步-权限与安全边界.md)
5. [上下文管理](design/第五步-上下文管理.md)
6. [Memory 设计](design/第六步-Memory设计调研.md)
7. [产品知识库与 RAG](design/第七步-产品知识库与RAG.md)

多跳检索的近期讨论结论：按证据缺口在既有 Agent 循环中继续检索，不要求知识图谱；具体触发、证据衔接和停止规则尚需整理进第七步。

## 文件结构

```text
Kefu_agent/
├── README.md
├── 客服AgentHarness项目方案.md
└── design/                  # 当前第 2～7 步设计
    └── archive/             # 历史架构讨论，不作为当前实施依据
```

[历史架构讨论](design/archive/架构讨论历史稿.md)仅供追溯，冲突时以当前分步设计为准。

原欧莱雅材料保存在本地工作区的 `archive/loreal/`；Commerce 学习指南和上游源码分别保存在工作区的 `reference/Commerce-Agents中文学习指南.md`、`reference/commerce-agents/`。这些资料均位于本 Git 仓库之外；新环境可直接访问 [Commerce Agents 上游仓库](https://github.com/anthropics/commerce-agents)。

## 远程仓库

[prossiblezero/Kefu_agent](https://github.com/prossiblezero/Kefu_agent)，本地远程名称为 `origin`。
