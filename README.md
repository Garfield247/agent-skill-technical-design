# agent-skill-technical-design

> 🏛️ 生产级前期系统架构、技术方案设计 (TDD/RFC)、数据建模与算法状态机规范 Agent Skill。

## 🌟 核心特性 (Features)

- **方案先行与审阅确认铁律**：复杂业务与系统改造必须先输出 TDD/RFC 方案，经用户审阅确认后再动手编码。
- **需求模糊 2-3 个确认点机制**：面对信息不足时，基于通用最优实践给出版本，精准列出 2-3 个关键决策点。
- **杜绝静默重试与兜底降级**：方案中涉及异常补偿与重试时，必须详尽分析潜在风险并显式提示，待确认后再定案。
- **严格算法与数学建模规范**：复杂计费与分流逻辑必须采用标准 LaTeX 公式完整推导。
- **全链路架构三件套**：领域与数据存储建模、时序与状态机跃迁图 (FSM)、分布式幂等与并发控制。

## 📦 安装与多 Agent 使用指南 (Installation & Multi-Agent Usage)

本项目遵循开放 Agent 规范，支持在 **Gemini / Antigravity**、**Anthropic Claude**、**Cursor / Codex** 等各类主流 Agent 环境中一键安装与激活：

### 1. Google Antigravity / Gemini Code Assist
- **全局安装（推荐）**：
  ```bash
  git clone git@github.com:Garfield247/agent-skill-technical-design.git ~/.gemini/config/skills/technical-design
  ```
- **项目工作区局部引入**：
  ```bash
  mkdir -p .agents/skills
  git clone git@github.com:Garfield247/agent-skill-technical-design.git .agents/skills/technical-design
  ```

### 2. Anthropic Claude (Claude Code / Claude Projects)
- **Claude Code (CLI 终端智能体)**：
  克隆至 Claude 全局技能库：
  ```bash
  mkdir -p ~/.claude/skills
  git clone git@github.com:Garfield247/agent-skill-technical-design.git ~/.claude/skills/technical-design
  ```
  *或者在项目根目录的 `CLAUDE.md` 中追加引入：*
  ```markdown
  See detailed engineering specifications in: ~/.claude/skills/technical-design/SKILL.md
  ```
- **Claude Projects (Web / 桌面端)**：
  直接将仓库中的 `SKILL.md` 内容复制并粘贴至 Project 的 **Project Knowledge (项目知识库)** 或 **Custom Instructions (自定义指令)** 中。

### 3. Cursor / GitHub Copilot / OpenAI Codex
- **Cursor (现代 MDC 规则体系)**：
  在项目根目录创建或链接规则：
  ```bash
  mkdir -p .cursor/rules
  # 克隆或软链接为 Cursor 专有规则文件
  git clone git@github.com:Garfield247/agent-skill-technical-design.git .cursor/rules/technical-design
  ```
- **GitHub Copilot / Codex**：
  将本技能规范注入 Copilot 指令集：
  ```bash
  mkdir -p .github
  cat << 'EOF' >> .github/copilot-instructions.md
  # 引入本技能核心规则
  EOF
  cat path/to/SKILL.md >> .github/copilot-instructions.md
  ```

## 📄 开源协议 (License)
本项目采用 [MIT License](LICENSE) 授权。
