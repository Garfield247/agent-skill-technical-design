---
name: technical-design
description: >-
  生产级前期系统架构、技术方案设计 (TDD/RFC)、数据建模与算法状态机规范技能。
  涵盖方案先行与审阅确认铁律、苏格拉底式需求收敛协议 (Socratic Refinement)、
  附带自动化检验指令的微任务拆解 (Bite-Sized Verifiable Tasks)、完成前铁证验证门禁 (Verification Evidence Gate)、
  严禁静默重试与兜底补偿、复杂算法标准 LaTeX 公式推导、领域建模 (ER/索引/分表) 及有限状态机闭环。
---

# 系统架构与前期技术方案设计规范 (Technical Design Skill)

## 核心设计铁律 (Core Redlines)
1. 🚨 **复杂需求必须“方案先行、审阅确认后再编码”**：严禁在未输出 TDD/RFC 并经用户确认前直接动工写业务代码；
2. 🚨 **多层级递进分治与全局闭环串联铁律 (Hierarchical Decomposition & Closure Gate)**：复杂需求坚决禁止单层平铺设计；强制按 L1 宏观边界 -> L2 领域阶段 -> L3 原子单元递进拆解；局部设计完成后，必须向上执行契约拓扑、逆向补偿与状态终态三大闭环检查，方可进入微任务拆解；
3. 🚨 **坚决禁止静默添加重试、兜底与补偿逻辑**：凡遇潜在失败，必须在方案中设立专门章节阐明原因、副作用并由用户拍板；
4. 🚨 **苏格拉底式需求收敛协议 (Socratic Refinement)**：需求模糊时严禁长篇脑补，必须提出 2-3 个关键决策点聚焦收敛；
5. 🚨 **复杂算法与数学模型标准 LaTeX 规范**：严禁用自然语言含糊替代关键算法，强制使用标准 LaTeX 公式给出定义域与边界；
6. 🚨 **完成前铁证验证门禁 (Verification Evidence Gate)**：严禁口头声明完成，微任务实施落地必须提供真实命令通过证据（Exit Code 0）。

## 标准设计工作流 (Workflow SOP)
1. **需求探测与边界收敛**：通过苏格拉底协议澄清歧义，确定 In-Scope 与容量指标；
2. **多层级递进分治设计**：按 L1 宏观全景 -> L2 领域阶段 -> L3 原子单元逐层拆解并针对性设计；
3. **架构推演与模型设计**：制定 ER/索引、Redis 命名空间与 TTL、Mermaid 时序图与 FSM 状态机；
4. **整体串联与闭环审查**：执行契约拓扑、逆向补偿与状态机终态三大闭环门禁自查；
5. **可验证微任务拆解**：输出携带 Target Files、自动化检验命令与 Evidence Gate 的原子任务列表；
6. **用户审阅确认与开干**：交由用户审阅确认后，方可解锁写入权限开展微任务落地。

## 渐进式参考手册索引 (Progressive Disclosure References)
更深入的设计模板、状态机规范与技术栈专项，按需调阅：

| 领域模块 | 子手册路径 | 核心覆盖内容 |
| :--- | :--- | :--- |
| **需求收敛、分治与 RFC 模板** | [01_rfc_template_and_socratic_refinement.md](references/01_rfc_template_and_socratic_refinement.md) | 苏格拉底提问协议、多层级递进分治与闭环检查、标准 RFC 交付模板、ADR 决策记录 |
| **数据建模与算法状态机** | [02_data_fsm_and_latex_modeling.md](references/02_data_fsm_and_latex_modeling.md) | MySQL 索引/分表、Redis Key 规范、Mermaid 时序与 FSM 闭环、LaTeX 数学公式推导 |
| **微任务拆解与验证门禁** | [03_bite_sized_tasks_and_evidence_gate.md](references/03_bite_sized_tasks_and_evidence_gate.md) | 10~20 分钟微任务四要素、自动化验证命令标准、完成前铁证验证门禁 |
| **可观测性与安全规范** | [04_observability_security_and_domain_specs.md](references/04_observability_security_and_domain_specs.md) | SLO/Trace 穿透、越权防护与敏感脱敏、Go/FastAPI/爬虫专属前置规范与评审 Checklist |
