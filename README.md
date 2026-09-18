# agent-skill-technical-design

> 🏛️ 生产级前期系统架构、技术方案设计 (TDD/RFC)、数据建模与算法状态机规范 Agent Skill。

## 🌟 核心特性 (Features)

- **方案先行与审阅确认铁律**：复杂业务与系统改造必须先输出 TDD/RFC 方案，经用户审阅确认后再动手编码。
- **需求模糊 2-3 个确认点机制**：面对信息不足时，基于通用最优实践给出版本，精准列出 2-3 个关键决策点。
- **杜绝静默重试与兜底降级**：方案中涉及异常补偿与重试时，必须详尽分析潜在风险并显式提示，待确认后再定案。
- **严格算法与数学建模规范**：复杂计费与分流逻辑必须采用标准 LaTeX 公式完整推导。
- **全链路架构三件套**：领域与数据存储建模、时序与状态机跃迁图 (FSM)、分布式幂等与并发控制。

## 📦 安装与加载 (Installation)

### 方式 1: 安装至 Antigravity / Gemini 全局技能库
```bash
git clone git@github.com:Garfield247/agent-skill-technical-design.git ~/.gemini/config/skills/technical-design
```

### 方式 2: 在任意项目中作为本地工作区技能引入
```bash
mkdir -p .agents/skills
git clone git@github.com:Garfield247/agent-skill-technical-design.git .agents/skills/technical-design
```

## 📄 开源协议 (License)
本项目采用 [MIT License](LICENSE) 授权。
