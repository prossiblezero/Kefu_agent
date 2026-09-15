# Kefu Agent

面向安克全产品售后的轻量 Agent Harness。通过文本、图片、产品知识与服务历史，完成产品消歧、排障引导、反馈验证和人工升级接续。

**当前阶段（2026-09-14）：第 1～13 步首版设计已补齐，尚未实现可运行应用。** 首版采用 Python／FastAPI、PostgreSQL＋pgvector、Redis 和 React；保留受控工具、持久运行时、上下文管理和可更正记忆。Milvus、独立重排等按需求与评测结果再引入。

开始开发先读[实施路线与交付验收](design/第十三步-实施路线与交付验收.md)；查看项目定位读[问题场景与架构选型](design/第一步-问题场景与架构选型.md)。各模块以对应分步文档为准，日期较新的明确修订优先，历史归档不作为实施依据。模型与预算有默认起点，准确度、容量与真实业务接入仍需实施验证。

## 设计入口

1. [问题场景与架构选型](design/第一步-问题场景与架构选型.md)
2. [Agent 主逻辑与运行时](design/第二步-Agent主逻辑与运行时.md)
3. [工具与 Skill](design/第三步-工具与Skill.md)
4. [权限与安全边界](design/第四步-权限与安全边界.md)
5. [上下文管理](design/第五步-上下文管理.md)
6. [Memory 设计](design/第六步-Memory设计调研.md)
7. [产品知识库与 RAG](design/第七步-产品知识库与RAG.md)
8. [数据准备与评测闭环](design/第八步-数据准备与评测闭环.md)
9. [模型接入与调用管理](design/第九步-模型接入与调用管理.md)
10. [后端接口与持久化](design/第十步-后端接口与持久化.md)
11. [前端交互与人工接续](design/第十一步-前端交互与人工接续.md)
12. [部署运维与成本控制](design/第十二步-部署运维与成本控制.md)
13. [实施路线与交付验收](design/第十三步-实施路线与交付验收.md)

默认复用 Docling／HybridChunker 解析切块，以官方产品资料为知识主体；48 条开发起步＋240 条正式评测。后端事件、页面卡片、人工回执和恢复处理已形成同一套契约，具体开发顺序见第十三步。

## 文件结构

```text
Kefu_agent/
├── README.md
└── design/                  # 当前第 1～13 步设计
    ├── 第一步-问题场景与架构选型.md
    └── archive/             # 历史架构讨论，不作为当前实施依据
```

[历史架构讨论](design/archive/架构讨论历史稿.md)仅供追溯，冲突时以当前分步设计为准。

原欧莱雅材料位于相邻的 `../LOreal_agent/`；Commerce 学习指南和上游源码分别位于 `../learn-commerce-agents/Commerce-Agents中文学习指南.md`、`../learn-commerce-agents/commerce-agents/`。这些资料均位于本 Git 仓库之外；新环境可直接访问 [Commerce Agents 上游仓库](https://github.com/anthropics/commerce-agents)。

## 远程仓库

[prossiblezero/Kefu_agent](https://github.com/prossiblezero/Kefu_agent)，本地远程名称为 `origin`。
