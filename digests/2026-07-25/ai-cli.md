# AI CLI 工具社区动态日报 2026-07-25

> 生成时间: 2026-07-25 15:45 UTC | 覆盖工具: 9 个

- [Claude Code](https://github.com/anthropics/claude-code)
- [OpenAI Codex](https://github.com/openai/codex)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [GitHub Copilot CLI](https://github.com/github/copilot-cli)
- [Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli)
- [OpenCode](https://github.com/anomalyco/opencode)
- [Pi](https://github.com/badlogic/pi-mono)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [DeepSeek TUI](https://github.com/Hmbown/DeepSeek-TUI)
- [Claude Code Skills](https://github.com/anthropics/skills)

---

## 横向对比

好的，作为专注于 AI 开发工具生态的资深技术分析师，我将基于您提供的 2026-07-25 各主流 AI CLI 工具的社区动态摘要，生成一份横向对比分析报告。

---

### AI CLI 工具生态横向对比分析报告 (2026-07-25)

#### 1. 生态全景

当前 AI CLI 工具生态正处于 **“繁荣分化，痛点集中”** 的快速迭代阶段。一方面，各工具积极拥抱新模型（如 Claude Opus 5），并围绕 Agent、MCP 协议、插件系统等构建差异化能力。另一方面，社区反馈的核心矛盾高度一致：**性能与稳定性成为最大短板**。无论是 OpenAI Codex 的日志膨胀、Claude Code 的 session 限制异常，还是 Gemini CLI 的 Agent 挂起，都表明工具的“可用性”远未成熟。同时，**成本感知、跨平台兼容性和安全隐私**正成为决定用户体验和工具采纳率的关键杠杆。开发者对工具的期待已从“能做什么”转向了“能否稳定、高效、透明地做好”。

#### 2. 各工具活跃度对比

| 工具 | 活跃 Issues (精选) | 活跃 PRs (精选) | Release 情况 | 社区焦点 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 条 | 2 条 (已关闭) | v2.1.219 / v2.1.220 | Max 计划 Session 限制、模型访问权限、Windows 兼容性 |
| **OpenAI Codex** | 10 条 | 10 条 | rust-v0.146.0-alpha.7~10 | 日志膨胀、认证中断、上下文限制错误、MCP稳定性 |
| **Gemini CLI** | 10 条 | 10 条 | 无 | Agent 稳定性 (挂起/误报)、Shell 输出截断、MCP OAuth |
| **GitHub Copilot CLI** | 10 条 | 1 条 (已撤回) | v1.0.75 | Plan 模式权限回归、终端交互退化、大会话 OOM、插件问题 |
| **Kimi Code CLI** | 4 条 | 2 条 | 无 | 核心Bug (死循环、登录失败)、远程控制、企业网络兼容 |
| **OpenCode** | 10 条 | 10 条 | v1.18.5 | CPU性能崩坏、模型透明度、安全问题、会话生命周期管理 |
| **Pi** | 10 条 | 10 条 | v0.82.1 | TUI 性能、Compaction 可靠性、跨平台路径、模型切换损坏 |
| **Qwen Code** | 10 条 | 10 条 | v0.21.0-nightly | 渲染/输入法Bug、子代理模型控制、自动化工具链、Session 恢复 |
| **DeepSeek TUI (CodeWhale)**| 10 条 | 10 条 | v0.9.1 | macOS 兼容性、App 神对象重构、国际化、配置验证过度严格 |

#### 3. 共同关注的功能方向

以下需求在多个工具的社区中同时涌现，构成了当前生态的“最大公约数”：

- **模型支持与访问管理**：
    - **工具**: Claude Code, GitHub Copilot CLI, Pi, OpenCode
    - **诉求**: 快速适配新模型（如 Claude Opus 5），同时解决与订阅计划/定价的权责不清问题（如Fable 5要求额外Credits），以及对模型切换的可靠性和透明度要求。

- **性能与资源管理**：
    - **工具**: OpenAI Codex, OpenCode, Pi, Gemini CLI
    - **诉求**: 解决**日志/会话文件无限膨胀**（Codex, OpenCode, Pi）、**CPU/内存泄漏**（OpenCode, Pi）和**会话恢复导致OOM**（Copilot CLI）等严重影响长期运行和用户体验的根本性问题。

- **跨平台兼容性与稳定性**：
    - **工具**: Claude Code, OpenAI Codex, Kimi Code CLI, Pi, Qwen Code, DeepSeek TUI
    - **诉求**: 围绕**Windows**（更新失败、GPU崩溃、路径问题）和**Linux**（Wayland支持）的各类 Bug。这已成为阻碍工具大规模普及的关键瓶颈。

- **成本可视化与控制**：
    - **工具**: Claude Code, OpenAI Codex, Qwen Code
    - **诉求**: 提供更精确的Token消耗、Session限制、Usage Credits等实时监控工具，并对异常消耗进行预警和解释，以满足开发者对“FinOps”的需求。

- **认证与网络稳定性**：
    - **工具**: OpenAI Codex, Gemini CLI, Kimi Code CLI
    - **诉求**: 修复OAuth流程脆弱、登录失败、企业代理/SSL证书不兼容等问题，确保在不同的网络环境下都能可靠连接。

- **会话与状态管理**：
    - **工具**: OpenCode, Qwen Code, Claude Code
    - **诉求**: 提供更完善的会话生命周期管理（自动清理、TTL）、历史记录恢复、以及压缩（Compaction）后的可靠性，避免数据丢失或不一致。

#### 4. 差异化定位分析

各工具正围绕不同的核心价值点构建差异化壁垒：

- **Claude Code**: **深度代理与安全**。主打复杂任务的委派执行和高级安全策略（如Sandbox网络白名单），定位为高阶开发者的“可靠副驾驶”。
- **OpenAI Codex**: **企业级协作与插件生态**。聚焦远程执行、凭证代理、技能变更通知等基础设施，旨在成为企业级AI开发工作流的核心枢纽。
- **Gemini CLI**: **探索性强，Agent架构领先**。积极引入“Caretaker Agent”自动化工单评估、PR生成器等高级自动化功能，探索AI agentic workflow的新范式。
- **Kimi Code CLI**: **聚焦核心体验与跨设备协同**。社区呼声最高的“远程控制”功能暗示其瞄准多设备无缝切换的开发者场景。
- **OpenCode**: **开源与自托管导向**。社区对模型透明度的强烈要求和安全漏洞（加密货币挖矿）的暴露，凸显其面向注重隐私和可定制性用户群体的定位。
- **Pi: 性能优先与多模型生态**。通过优化渲染性能（O(viewport)）和解决模型切换问题，并快速支持 Claude Opus 5，定位为提供流畅、灵活多模型体验的轻量级工具。
- **Qwen Code**: **深耕编码流程与AI辅助**。更多关注终端交互细节（输入法、自动补全）、子代理模型等级控制等，显示其专注于优化开发者在IDE/CLI中的编码体验闭环。
- **DeepSeek TUI (CodeWhale)**: **国际化与架构重构并行**。在解决核心Bug（macOS兼容性）和重构代码的同时，大规模启动国际化，显示出其意图迅速扩大全球用户基础。

#### 5. 社区热度与成熟度

- **高活跃度/成熟度**：**Claude Code** 和 **OpenAI Codex** 的社区讨论最深入、Issue 标签体系最完善、官方响应也相对积极。但问题暴露得也最全面，处于“盛名之下，其实难副”的阵痛期。
- **快速迭代/探索期**：**Gemini CLI**、**OpenCode** 和 **Pi** 的社区非常活跃，每日有大量 Issue 和 PR 提交，功能迭代速度快，但部分核心功能稳定性仍有待验证。
- **小规模/聚焦期**：**Kimi Code CLI** 和 **DeepSeek TUI (CodeWhale)** 社区规模较小，但讨论聚焦于少数痛点（登录、死循环/兼容性、国际化），表明其处于功能打磨和用户增长的早期阶段。
- **稳健演进**：**GitHub Copilot CLI** 和 **Qwen Code** 社区活动平稳，Bug 修复和功能优化稳步推进，但缺乏革命性突破，显示其已度过早期爆发期，进入成熟维护阶段。

#### 6. 值得关注的趋势信号

- **“Post-Demo”时代的到来**：社区已不再对 AI 功能“能做什么”感到兴奋，转而激烈讨论“**为何不稳定**”、“**为何这么贵**”和“**为何在Windows上不能用**”。稳定性、TCO（总拥有成本）和平台兼容性成为决定工具生死的三大要素。
- **Agent 可靠性的信任危机**：Gemini CLI 和 OpenCode 爆出的“Agent 假成功”和“空结果”问题，直接动摇了开发者对 Agent 自主执行的信任。未来，**Agent行为的可解释性、可追溯性和确定性的“回滚”机制** 将成为核心竞争力。
- **成本透明化成为刚需**：从 Claude Code 的 Session 限制到 Codex 的日志膨胀，再到 Qwen Code 的 Token 显示需求，开发者不再满足于黑盒收费，要求对每一笔“算力花费”了如指掌。**多维度、实时化的成本仪表盘** 会从“加分项”变为“必选项”。
- **“安全左移”从口头变为行动**：OpenCode 的挖矿事件、DeepSeek TUI 的测试污染问题，以及各工具对 OAuth、SSL 等认证机制的反复修复，表明**安全已不是功能特性，而是基础设施**。工具链的默认安全配置和最小权限原则将受到更严格的审视。
- **从“单点工具”到“生态系统”的野心**：各工具都在通过 MCP、插件、Hook 等方式建立自己的生态。但插件市场的可靠性（Copilot CLI）、连接器稳定性（Claude Code）等问题说明，生态建设任重道远。**生态的“质量”而非“数量”** 将是下一阶段竞争的关键。

**对开发者的参考价值**：在选择 AI CLI 工具时，**不应仅被“最新模型”或“炫酷功能”吸引**。建议根据自身平台的 **稳定性需求**（优先选择对 Windows/macOS 兼容性良好的工具）、对 **成本透明度的要求**（选择提供精准监控的工具）以及对 **Agent 可靠性的容忍度**（选择状态报告更透明的工具）来综合决策。当前，**性能稳定性和社区问题响应速度** 是比“谁有新功能”更值得关注的指标。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，这是根据你提供的数据生成的 Claude Code Skills 社区热点分析报告。

---

### Claude Code Skills 社区热点报告（数据截止 2026-07-25）

#### 1. 热门 Skills 排行

以下是社区讨论热度最高、关注度最集中的 5 个 Skills（Pull Requests）：

1.  **[修复] skill-creator 核心评估脚本 (`run_eval.py`)** (`#1298`)
    -   **功能**：修复 `run_eval.py` 中导致技能触发率评估始终为 0% 的多个严重 Bug，包括 Windows 兼容性、触发检测逻辑等问题。
    -   **社区热点**：讨论最为激烈。该 PR 关联并试图解决 `#556`、`#1061`、`#1169` 等多个被广泛报告的 Issue，旨在修复技能创作与优化流程中“评估结果完全不可信”的根本性问题。
    -   **状态**：🟡 **Open**
    -   **链接**：`https://github.com/anthropics/skills/pull/1298`

2.  **[新技能] 自我审计 (self-audit)** (`#1367`)
    -   **功能**：引入一个通用技能，在 AI 输出交付前执行机械性文件验证和四维推理质量审计。这是对现有 Skills 能力的一种元级补充。
    -   **社区热点**：虽然被提出的时间较短，但评论活跃，反映社区对 AI 输出质量和可靠性的担忧。提案者提出的“机械验证 + 推理质量门”结构引发了关于如何系统化保证 AI 工作成果的讨论。
    -   **状态**：🟡 **Open**
    -   **链接**：`https://github.com/anthropics/skills/pull/1367`

3.  **[新技能] 色彩专家 (color-expert)** (`#1302`)
    -   **功能**：提供一个全面的色彩知识技能，涵盖命名体系、色彩空间、调色板生成等，专为涉及色彩的任务设计。
    -   **社区热点**：讨论周期长（从 6月10日 持续到 7月21日），表明这是一个跨领域、需求明确且专业性强的工具。社区关注其覆盖的广度（ISCC-NBS, RAL等多种标准）和深度（色彩空间使用建议）。
    -   **状态**：🟡 **Open**
    -   **链接**：`https://github.com/anthropics/skills/pull/1302`

4.  **[新技能] 测试模式 (testing-patterns)** (`#723`)
    -   **功能**：提供一个全面的测试技能，覆盖单元测试、React 组件测试、集成测试和 E2E 测试，并包含测试哲学和命名约定。
    -   **社区热点**：社区普遍关注代码质量，该 Skill 试图将最佳测试实践标准化并注入到 Claude 的工作流中。评论焦点在于其内容的完整性和实用性，以及如何确保 Claude 能准确应用这些模式。
    -   **状态**：🟡 **Open**
    -   **链接**：`https://github.com/anthropics/skills/pull/723`

5.  **[新技能] 复古游戏开发 (pyxel)** (`#525`)
    -   **功能**：为 Pyxel 复古游戏引擎提供 MCP 集成技能，涵盖从编写到迭代的完整工作流。
    -   **社区热点**：这是一个特定领域（创意编码）的技能，讨论热度高表明社区对非传统编程任务（如游戏开发）的兴趣。评论可能涉及 MCP 的集成方式和工作流的有效性。
    -   **状态**：🟡 **Open**
    -   **链接**：`https://github.com/anthropics/skills/pull/525`

#### 2. 社区需求趋势

从 Issues 的讨论热度来看，社区最期待的新 Skill 方向集中在：

1.  **安全与治理**：`#492` (社区Skills的信任边界滥用，43条评论) 和 `#412` (Agent治理技能) 是高热度议题。社区迫切需要官方提供关于 Skill 来源的信任机制、权限管理 Agent 行为的安全模式。
2.  **协作与共享**：`#228` (组织级技能共享，8个👍) 和 `#189` (技能下载重复问题) 表明，当技能数量增多后，社区对技能的**分发、安装和团队协作**的需求非常强烈，不再满足于单机自行上传。
3.  **技能创作与优化工具链**：`#202` (skill-creator 需更新) 和一系列关于 `run_eval.py` 失效的 Issues (`#556`, `#1061`, `#1169`)，都指向同一个痛点：**官方提供的 Skill 创作与评估工具存在严重的质量缺陷**，导致社区难以有效开发和迭代自己的 Skills。
4.  **通用性与可扩展性**：`#1329` (紧凑记忆技能) 和 `#16` (将Skills暴露为MCPs) 反映了社区希望 Skills 不仅能处理特定任务，还能在更宏大的 Agent 系统或工作流中发挥作用，例如管理上下文、作为标准 API 调用。

#### 3. 高潜力待合并 Skills

以下 PR 评论活跃，尚未合并，但很可能在未来被考虑合并：

-   **`#1367`**: [自我审计 (self-audit)](https://github.com/anthropics/skills/pull/1367) —— 概念新颖，直接回应了社区对 AI 输出质量的担忧。如果验证有效，其通用性会使其极具价值。
-   **`#1302`**: [色彩专家 (color-expert)](https://github.com/anthropics/skills/pull/1302) —— 讨论周期长，内容详实，定位清晰。合并后可直接提升 Claude 在设计、可视化等领域的专业度。
-   **`#723`**: [测试模式 (testing-patterns)](https://github.com/anthropics/skills/pull/723) —— 内容完善，直接命中开发者核心需求。
-   **`#525`**: [复古游戏开发 (pyxel)](https://github.com/anthropics/skills/pull/525) —— 特定领域但非常有趣且有明确受众，其 MCP 集成模式可为其他类似工具提供参考。

#### 4. Skills 生态洞察

**当前社区最集中的核心诉求是：修复并完善官方提供的 Skill 创作与评估工具链（特别是 `run_eval.py`），以建立一个稳定、可信的开发基础，并在此基础上建立官方的安全治理和团队协作机制。** 大量围绕着 `run_eval.py` 失效的 Issues 和旨在修复它的 PRs，构成了此次数据分析中最突出的“社区共识”。

---

# 🗞️ Claude Code 社区动态日报 | 2026-07-25

---

## 今日速览

Anthropic 于今日凌晨发布两个热修复版本（v2.1.219 / v2.1.220），其中最引人注目的是 **Claude Opus 5 正式成为默认 Opus 模型**，支持 1M context，且 fast 模式定价 $10/$50 per Mtok。社区方面，**Max 计划用户遭遇 session 限制异常快速消耗**（#38335，809 条评论）仍是头号焦点，同时 **Fable 5 在 TUI 交互模式下被错误地要求 usage credits** 引发大量讨论。Windows 端的更新失败、Cowork 选项卡缺失等问题持续发酵。

---

## 版本发布

### v2.1.220
> 发布于 2026-07-25

- Bug 修复与可靠性改进。

### v2.1.219
> 发布于 2026-07-25

- **新增模型**：`claude-opus-5`，现为默认 Opus 模型，支持 1M context，fast 模式定价 $10/$50 per Mtok。
- **安全增强**：新增 `sandbox.network.strictAllowlist` 设置，可拒绝未在白名单中的主机访问沙盒命令（无需二次确认）。
- **Hook 扩展**：新增 `DirectoryAdded` hook，在目录被添加后触发。

---

## 社区热点 Issues

| 编号 | 标题 | 标签 | 评论 | 👍 | 状态 |
|------|------|------|------|----|------|
| [#38335](https://github.com/anthropics/claude-code/issues/38335) | Claude Max 计划 session 限制自 3月23日起异常快速耗尽（CLI 使用） | bug | 809 | 470 | 🟠 OPEN |
| [#48407](https://github.com/anthropics/claude-code/issues/48407) | Windows 11 桌面 app v1.2581.0 上 Cowork 选项卡消失 | bug, platform:windows, area:cowork, area:desktop | 40 | 16 | 🟠 OPEN |
| [#41456](https://github.com/anthropics/claude-code/issues/41456) | 【功能请求】为桌面应用添加状态栏 | enhancement, area:statusline, area:desktop | 13 | 30 | 🟠 OPEN |
| [#76357](https://github.com/anthropics/claude-code/issues/76357) | Windows (MSIX) 更新失败：“另一个程序正在使用此文件”，每次更新后需重启才能启动 | bug, platform:windows, area:cowork, area:desktop | 8 | 4 | 🟠 OPEN |
| [#80749](https://github.com/anthropics/claude-code/issues/80749) | Fable 5 在交互 TUI 中被要求“usage credits”才能使用（Max 计划）；headless 模式正常 — 2.1.216 回归 | bug | 6 | 1 | 🟠 OPEN |
| [#79597](https://github.com/anthropics/claude-code/issues/79597) | Fable 5 对使用 setup-token 的 Max 账户在交互选择器中错误地要求 usage credits | bug | 5 | 7 | 🟠 OPEN |
| [#81044](https://github.com/anthropics/claude-code/issues/81044) | Gmail 连接器在设置中显示“已连接”，但无法在 session 或定时任务中使用 | bug | 4 | 0 | 🟠 OPEN |
| [#56317](https://github.com/anthropics/claude-code/issues/56317) | OTEL 成本计数器 `claude_code_cost_usage_USD_total` 在并行进程共享相同 session_id 时冲突，导致数值震荡和 inflate | bug, platform:linux, area:cost | 4 | 3 | 🟠 OPEN |
| [#80999](https://github.com/anthropics/claude-code/issues/80999) | Windows: 隐藏的浏览器预览窗格因 `vk_swiftshader.dll` 被代码完整性阻止导致应用崩溃 | bug, platform:windows | 4 | 1 | 🟠 OPEN |
| [#77484](https://github.com/anthropics/claude-code/issues/77484) | 状态栏缺乏每个命令的模型/effort 可见性，且长时间 agent 轮次中限速/上下文数据过期 | enhancement, area:agents, area:statusline | 3 | 1 | 🟠 OPEN |

### 🔥 重点解读

1. **#38335** — 持续几个月的 Max 计划 session 限制问题至今未解决，社区呼声极高（470👍）。用户报告在 3月23日后 session 消耗速度异常加快，严重影响日常使用。
2. **#80749 & #79597** — Fable 5 模型对 Max 用户显示“需要 usage credits”的误报，headless 模式 (`-p`) 正常，但交互 TUI 和 setup-token 认证用户受影响。Anthropic 已在追踪，但尚未正式修复。
3. **#76357** — Windows MSIX 安装用户每次更新都需重启电脑，严重阻碍更新流程，已有明确重现步骤。
4. **#56317** — 企业级用户关注的 OTEL 成本计数器冲突，可能导致成本监控数据膨胀 100x+，影响 FinOps 决策。

---

## 重要 PR 进展

（过去24小时内更新仅2条）

| 编号 | 标题 | 状态 | 摘要 |
|------|------|------|------|
| [#15727](https://github.com/anthropics/claude-code/pull/15727) | fix(hookify): 修正 hook 模块的 Python 导入路径 | ✅ CLOSED | 修复 hookify 插件因 `No module named 'hookify'` 错误而失败的问题。插件目录结构导致 `from hookify.core.config_loader` 导入路径错误，现已修正。 |
| [#49596](https://github.com/anthropics/claude-code/pull/49596) | refactor: 将共享 GitHub API 客户端提取到 github-api.ts 并添加测试 | ✅ CLOSED | 重构代码，将 GitHub API 客户端从各模块中提取为单一共享文件 `github-api.ts`，并补充单元测试，提升可维护性。 |

> 两个 PR 均为早期提交并已关闭，反映本周社区贡献相对平静。

---

## 功能需求趋势

从近期 Issues 中提炼出社区最关注的五大方向：

1. **新模型支持与访问管理**  
   Opus 5 刚发布，但 Fable 5 的访问权限混淆（usage credits 门槛）成为当前痛点。用户期望模型选择更透明、与订阅计划一致。

2. **桌面应用体验完善**  
   - 状态栏（#41456）呼声很高，30👍，用户希望在桌面端获得 CLI 同等的状态可视化。  
   - Cowork 选项卡在 Windows 上反复丢失（#48407, #49748），反映跨平台稳定性仍需加强。

3. **Windows 兼容性**  
   更新失败（#76357）、插件安装 EPERM（#52435）、路径含重音字符崩溃（#45432）、Code Integrity 冲突（#80999）——Windows 用户面临多个阻塞性问题。

4. **成本与限制可视化**  
   用户希望实时看到 session 消耗、usage credits 余额、每个命令的 token 成本。OTEL 计数器缺陷（#56317）进一步削弱了成本监控的可靠性。

5. **连接器 & 自动化集成**  
   Gmail 连接器“假连接”问题（#81044）表明连接器生态的测试覆盖面不足。同时，定时任务、headless 模式等自动化场景的稳定性受到关注。

---

## 开发者关注点

- **Max 计划 session 限制异常**：影响面最广、情绪最激烈的话题，社区期待 Anthropic 提供更明确的消耗逻辑或补偿方案。
- **Fable 5 访问权限困惑**：Max 用户在交互模式下被错误提示需要额外购买 credits，headless 模式却正常，导致工作流中断和信任问题。
- **Windows 更新灾难**：每次更新需重启电脑才能使用，且曾出现更新后 Cowork 选项卡永久消失的情况，严重阻碍用户升级。
- **粘贴功能退化**：多平台（macOS、Windows）用户反馈 `cmd+v` 或右键粘贴在 CLI 中失效（#39764, #49571），影响日常操作效率。
- **模型质量与 token 消耗权衡**：部分用户报告 Opus 4.7 比 4.6 质量更差且 token 更高（#51440），建议 Anthropic 回归模型选择机制或提供回退选项。

> 整体而言，社区对 Claude Code 的深度整合能力（headless、agent、hook）表示认可，但 **定价感知、跨平台稳定性、新模型准入策略** 是当前最大的摩擦点。

---

*数据来源：GitHub `anthropics/claude-code` 仓库，截至 2026-07-25 23:59 UTC。*

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# 🧠 OpenAI Codex 社区动态日报 | 2026-07-25

---

## 今日速览

- **连续发布四个 Rust 版本（v0.146.0-alpha.7～alpha.10）**，修复多个内部组件，但未公布具体变更细节。
- **ChatGPT App 出现大规模服务中断（#35315）**，用户反馈 503 及 `auth error code: biscuit_bak`，影响发起/继续对话，已获 42 条评论，社区高度关注。
- **磁盘与日志膨胀问题持续升温**：多个 Issue（#24948、#31198、#33735、#34061、#35092）报告会话日志/JSONL 文件增长至数十 GB，成为当下最突出的性能痛点。

---

## 版本发布

过去 24 小时 OpenCodex 仓库发布了 **4 个 Rust 相关 alpha 版本**，均为 CLI/runtime 层面的内部迭代：

- [`rust-v0.146.0-alpha.7`](https://github.com/openai/codex/releases/tag/rust-v0.146.0-alpha.7)
- [`rust-v0.146.0-alpha.8`](https://github.com/openai/codex/releases/tag/rust-v0.146.0-alpha.8)
- [`rust-v0.146.0-alpha.9`](https://github.com/openai/codex/releases/tag/rust-v0.146.0-alpha.9)
- [`rust-v0.146.0-alpha.10`](https://github.com/openai/codex/releases/tag/rust-v0.146.0-alpha.10)

> 注：Release Note 仅标注版本号，未列出具体变更，推测为内部修复或自动化 CI 产出。

---

## 社区热点 Issues（挑选 10 条）

### 1. 🔴 [严重] ChatGPT App 完全服务中断
- **Issue**: [#35315](https://github.com/openai/codex/issues/35315)
- **标签**: `bug`, `auth`, `app`, `connectivity`
- **为何重要**: 用户无法发起或继续任何对话，返回 503 错误与 `biscuit_bak` 认证异常。评论 42 条，热度极高，Max 订阅用户也无法使用。
- **社区反应**: 大量用户反馈类似现象，怀疑是服务端配置或证书问题。

### 2. 🔴 [高频] 关于自动确认超时设置的呼声
- **Issue**: [#28969](https://github.com/openai/codex/issues/28969)
- **标签**: `bug`, `CLI`, `config`, `plan`
- **为何重要**: 用户希望增加一个配置选项来禁用自动在 60 秒后确认问题。获得 161 个 👍，评论 56 条，是目前社区最核心的诉求之一。
- **社区反应**: 开发者普遍认为自动确认机制在复杂场景下容易误操作，强烈要求可关闭。

### 3. 🔴 [性能] 会话日志膨胀至 700MB~2GB
- **Issue**: [#24948](https://github.com/openai/codex/issues/24948)
- **标签**: `bug`, `TUI`, `performance`
- **为何重要**: 日志文件因重复的 compaction 历史和原始工具输出持续增长，严重影响体验。
- **社区反应**: 21 条评论，1 个 👍（可能因该问题被其他同类 Issue 分流）。

### 4. 🔴 [性能] GPT-5.6 Sol 上下文窗口被错误限制
- **Issue**: [#31860](https://github.com/openai/codex/issues/31860)
- **标签**: `bug`, `context`, `app`
- **为何重要**: 模型规格显示上下文窗口 1.05M，但实际被 catalog 限制在 372K（有效 353.4K），严重影响长会话能力。
- **社区反应**: 9 条评论，23 个 👍，Pro 用户高度关注。

### 5. 🔴 [Windows] 添加第二个文件夹后应用崩溃
- **Issue**: [#35057](https://github.com/openai/codex/issues/35057)
- **标签**: `bug`, `windows-os`, `app`, `session`
- **为何重要**: 在已有项目上新增文件夹导致 Codex Desktop 卡在“正在加载”页面，无法启动。
- **社区反应**: 20 条评论，5 个 👍，Business 订阅用户受影响。

### 6. 🔴 [MCP] OAuth 认证因 issuer 校验失败
- **Issue**: [#31573](https://github.com/openai/codex/issues/31573)
- **标签**: `bug`, `auth`, `MCP`, `CLI`
- **为何重要**: OAuth 流程中 issuer 校验失败导致无法登录，影响所有依赖 MCP 的技能。
- **社区反应**: 22 条评论，54 个 👍，免费用户也受影响。

### 7. 🔴 [macOS Intel] Computer Use 插件始终不可用
- **Issue**: [#18404](https://github.com/openai/codex/issues/18404)
- **标签**: `bug`, `mcp`, `app`, `skills`, `computer-use`
- **为何重要**: Intel Mac 上即使 MCP 服务器显示已启用，Computer Use 插件仍显示“unavailable”，已有 26 条评论。
- **社区反应**: 持续数月的旧 Issue 今日仍有更新，说明至今未完全修复。

### 8. 🔴 [Windows] GPU 进程因 vk_swiftshader.dll 崩溃
- **Issue**: [#34133](https://github.com/openai/codex/issues/34133)
- **标签**: `bug`, `windows-os`, `app`, `browser`
- **为何重要**: 应用内截图功能触发 GPU 崩溃，原因是被 Code Integrity 拒绝的 SwiftShader 驱动。
- **社区反应**: 13 条评论，虽然点赞少但影响面广。

### 9. 🔴 [VS Code] Codex Diff 发生崩溃
- **Issue**: [#35058](https://github.com/openai/codex/issues/35058)
- **标签**: `bug`, `extension`
- **为何重要**: 在 VS Code 中打开 Codex Diff 标签页时始终报错，无法进行差异对比，8 个 👍，涉及 Apple Silicon。
- **社区反应**: 用户表示每个仓库都复现，插件更新后仍未修复。

### 10. 🔴 [UX] 消费限制仪表盘起始值显示 99%
- **Issue**: [#26370](https://github.com/openai/codex/issues/26370)
- **标签**: `bug`, `rate-limits`, `app`
- **为何重要**: 使用量仪表盘从 99% 开始而非 100%，给用户造成困惑，是否已用完额度？
- **社区反应**: 8 条评论，8 个 👍，虽是数值显示问题但影响用户对额度的信任。

---

## 重要 PR 进展（挑选 10 条）

### 1. 🚀 [CLOSED] 线程选中技能变更通知机制
- **PR**: [#30228](https://github.com/openai/codex/pull/30228)
- **内容**: 当线程的环境就绪/恢复/失败时，向客户端推送 `skills/list` 变更信号，避免客户端缓存失效。
- **为何重要**: 这是技能插件系统的基础设施改进，使客户端能及时感知环境变化。

### 2. 🚀 [CLOSED] Windows 启动器传递显式应用路径
- **PR**: [#29845](https://github.com/openai/codex/pull/29845)
- **内容**: 引入 `WindowsProcessLaunch` 结构体，在统一执行、提权运行器等环节传递显式可执行路径。
- **为何重要**: 为 Windows 统一执行解析奠定基础，提高启动稳定性。

### 3. 🚀 [CLOSED] 限制 stdio JSON-RPC 帧大小
- **PR**: [#31782](https://github.com/openai/codex/pull/31782)
- **内容**: 将 `BufReader::lines()` 的最大帧大小限制为 64 MiB，防止恶意/异常 stdio 执行服务器导致内存无限增长。
- **为何重要**: 安全性与稳定性改进，与 Noise 层已有的 JSON-RPC 上限对齐。

### 4. 🚀 [CLOSED] 管道化祖先发现优化
- **PR**: [#31810](https://github.com/openai/codex/pull/31810)
- **内容**: 将 AGENT 候选目录和 `.agents/skills` 的检查流水线化，根标记也支持八请求并发探测。
- **为何重要**: 显著提升远程项目启动速度，减少串行等待。

### 5. 🚀 [CLOSED] 跳过插件 MCP 过滤（无 allowlist 时）
- **PR**: [#35280](https://github.com/openai/codex/pull/35280)
- **内容**: 当所有插件均未指定 `mcp_servers` 时，不再对 MCP 服务进行过滤；显式空列表仍视为拒绝全部。
- **为何重要**: 修正了插件 MCP 的默认行为，减少配置复杂性。

### 6. 🚀 [CLOSED] 远程执行服务器连接追踪
- **PR**: [#35275](https://github.com/openai/codex/pull/35275)
- **内容**: 在后台延迟启动远程环境时保留当前追踪 span，为连接、注册、Noise、WebSocket 等阶段增加 span。
- **为何重要**: 方便调试远程环境连接问题，提升可观测性。

### 7. 🚀 [CLOSED] Responses Lite 元数据中加入代码模式工具名
- **PR**: [#35271](https://github.com/openai/codex/pull/35271)
- **内容**: 在 turn 元数据中添加 `code_mode_tool_names` 字段，映射代码模式标识符到结构化 `ToolName`。
- **为何重要**: 为客户端提供更清晰的工具调用信息，支持代码模式功能。

### 8. 🟡 [OPEN] 集成实验性凭证代理（credential broker）
- **PR**: [#29752](https://github.com/openai/codex/pull/29752)
- **内容**: Codex core 需要主动选择使用代理接管凭证替换行为，并在命令生命周期中传递 brokered 值。
- **为何重要**: 对于安全沙箱和多级子代理环境至关重要，防止凭证泄露。

### 9. 🚀 [CLOSED] 强化网络审批取消与并发控制
- **PR**: [#35267](https://github.com/openai/codex/pull/35267)
- **内容**: 将待审批网络请求限定在单个 turn 和执行内，合并同一执行内的重复请求；失败时取消被拒绝的执行和等待请求。
- **为何重要**: 提升网络审批的安全性与用户体验，防止死锁。

### 10. 🚀 [CLOSED] 签名 macOS 捆绑辅助二进制文件
- **PR**: [#35264](https://github.com/openai/codex/pull/35264)
- **内容**: 修复 macOS 发布工作流在打包后签名阶段遗漏 `rg` 和 zsh 的问题，现在在打包前获取并签名。
- **为何重要**: 解决因未签名导致的 Gatekeeper 拦截问题，提升 macOS 用户体验。

---

## 功能需求趋势

综合分析今日所有 Issues（50 条）及 PR 主题，社区最关注的功能方向如下：

| 方向 | 代表 Issues | 说明 |
|------|-------------|------|
| **性能与资源管控** | #24948, #31198, #33735, #34061, #35092, #31860 | 日志/JSONL 膨胀、磁盘写频繁、上下文限制错误是当前最大痛点 |
| **认证与连接稳定性** | #35315, #31573, #35318 | 服务中断、OAuth issuer 校验失败频繁出现 |
| **Windows/macOS 兼容性** | #35057, #34133, #18404, #34219, #25353 | GPU 崩溃、插件不可用、WSL 集成问题、窗口闪烁 |
| **MCP 技能与插件生态** | #31582, #30228, #35280, #35275, #31307, #31310 | 技能变更通知、MCP 过滤逻辑、远程插件 ID 传播 |
| **用户界面改进** | #28969, #19504, #35357, #35356 | 自动确认设置、RTL 支持、消息队列冻结/分组 |
| **IDE 集成** | #35058, #25353 | VS Code 扩展中的 Diff 崩溃、浏览器插件不注册 |

---

## 开发者关注点

从 Bug 报告、评论和 PR 讨论中提炼出开发者最常抱怨的 **Top 5 痛点**：

1. **日志文件失控**  
   多个开发者反映子代理日志、compacted history、内嵌图片数据导致 JSONL 文件膨胀至数十乃至上百 GB（#24948, #31198, #33735），严重占用磁盘且影响启动速度。社区呼吁提供日志裁剪配置或限制。

2. **持续存在的 MCP / 插件稳定性问题**  
   Computer Use 插件在 Intel Mac 上仍“unavailable”（#18404），插件在重启后消失（#25809），浏览器不注册路由（#25353）。这些跨平台问题反复出现，用户感到沮丧。

3. **上下文窗口被错误截断**  
   GPT-5.6 Sol 被 catalog 限制到 372K（#31860）被标记为 Critical，Pro 用户期望获得完整的 1.05M 上下文。类似限制可能出现在其他模型上。

4. **OAuth 与认证流程脆弱**  
   OAuth issuer 校验失败（#31573）与 App 服务中断（#35315）共同指向认证基础设施的可靠性不足，影响所有订阅等级的用户。

5. **Windows 专属崩溃与渲染问题**  
   GPU 进程因 vk_swiftshader.dll 崩溃（#34133）、添加第二文件夹后无法启动（#35057）、启动时闪烁（#34219）——Windows 用户面临更多自有的平台缺陷，且修复进度偏慢。

---

> **总结**：今日社区核心动向是 **性能顽疾与连接稳定性**，开发者普遍期待 OpenAI 尽快解决日志膨胀和上下文限制问题，同时改善跨平台兼容性。Rust alpha 版本的密集发布暗示内部正在快速迭代，但公开信息有限。建议关注明日是否有正式 Release Note。

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，以下是基于 2026 年 7 月 25 日 GitHub 数据生成的 Gemini CLI 社区动态日报。

---

# Gemini CLI 社区动态日报 | 2026-07-25

## 今日速览

今日社区主要关注点集中在 **Agent 系统的稳定性与可靠性**上。多个高优先级 Bug 报告指出子代理在达到轮次限制后错误报告“成功”状态，以及通用代理在执行简单任务时挂起。代码库方面，社区贡献活跃，多个 PR 聚焦于 **MCP OAuth 认证**修复和 **shell 命令输出截断**等关键功能，同时“Caretaker Agent”自动化工单评估系统也在紧锣密鼓地推进。

## 版本发布

过去24小时内无新版本发布。

## 社区热点 Issues

以下选取了 10 个最值得关注的 Issue，它们反映了当前开发者和社区最关心的痛点与功能方向。

1.  **[#22323] Subagent recovery after MAX_TURNS is reported as GOAL success, hiding interruption**
    - **重要性**: ⭐⭐⭐⭐⭐
    - **分析**: 这是一个严重影响用户对 Agent 状态判断的 **P1 Bug**。`codebase_investigator` 子代理在达到最大执行轮次后被强制中断，但却向主代理返回“成功”状态，导致用户完全不知道任务实际上因为轮次限制而失败。社区对此反应强烈，12 条评论显示出此问题具有普遍性。
    - **链接**: [Issue #22323](https://github.com/google-gemini/gemini-cli/issues/22323)

2.  **[#21409] Generalist agent hangs**
    - **重要性**: ⭐⭐⭐⭐⭐
    - **分析**: 同样是 **P1 Bug**。通用代理在执行“创建文件夹”等简单任务时会无限期挂起。该 Bug 严重影响了日常工作流，用户只能通过指令禁止模型调用子代理来规避。8 个 👍 和 8 条评论表明这是社区高频遇到的问题。
    - **链接**: [Issue #21409](https://github.com/google-gemini/gemini-cli/issues/21409)

3.  **[#21968] Gemini does not use skills and sub-agents enough**
    - **重要性**: ⭐⭐⭐⭐
    - **分析**: 虽然这是一个 **P2** 问题，但它揭示了核心功能体验的缺陷。用户抱怨即使配置了自定义技能（如“git”和“gradle”），Gemini CLI 也极少主动使用。这说明 Agent 的意图识别和任务规划能力仍有待提升，“智能化”程度不足。
    - **链接**: [Issue #21968](https://github.com/google-gemini/gemini-cli/issues/21968)

4.  **[#25166] Shell command execution gets stuck with "Waiting input" after command completes**
    - **重要性**: ⭐⭐⭐⭐
    - **分析**: **P1 Bug**，直接影响用户体验。当 CLI 执行完一个简单命令后，会卡在“等待输入”状态，导致后续流程无法继续。社区有 3 个 👍，反映了这是一个常见的“卡死”场景。
    - **链接**: [Issue #25166](https://github.com/google-gemini/gemini-cli/issues/25166)

5.  **[#26522] Stop Auto Memory from retrying low-signal sessions indefinitely**
    - **重要性**: ⭐⭐⭐
    - **分析**: **Auto Memory** 功能的一个设计缺陷。当提取代理判断某个会话内容无价值（低信号）时，系统会反复重试该会话，造成资源浪费和循环。社区正在寻求更优的内务处理机制。
    - **链接**: [Issue #26522](https://github.com/google-gemini/gemini-cli/issues/26522)

6.  **[#26525] Add deterministic redaction and reduce Auto Memory logging**
    - **重要性**: ⭐⭐⭐
    - **分析**: **安全相关的 P2 Bug**。Auto Memory 功能在读取本地记录时，会将内容发送给模型。虽然提示词要求模型进行机密信息编辑，但这种“事后处理”的方式存在安全风险。社区希望实现“确定性编辑”，即在发送前就完成脱敏。
    - **链接**: [Issue #26525](https://github.com/google-gemini/gemini-cli/issues/26525)

7.  **[#21983] browser subagent fails in wayland**
    - **重要性**: ⭐⭐⭐
    - **分析**: **P1 Bug**，环境兼容性问题。在 Linux Wayland 显示服务器下，Browser Agent 会直接失败。这影响了特定操作系统用户群体的核心功能使用。
    - **链接**: [Issue #21983](https://github.com/google-gemini/gemini-cli/issues/21983)

8.  **[#24246] Gemini CLI encounters 400 error with > 128 tools**
    - **重要性**: ⭐⭐⭐
    - **分析**: 这是一个可扩展性问题。当可用工具数量超过 128 个时，API 调用会返回 400 错误。社区讨论围绕如何让 Agent 更智能地“隔离”当前任务相关的工具，而不是把所有工具都加载进去。
    - **链接**: [Issue #24246](https://github.com/google-gemini/gemini-cli/issues/24246)

9.  **[#22672] Agent should stop/discourage destructive behavior**
    - **重要性**: ⭐⭐⭐
    - **分析**: **P2 增强请求**。社区反馈 Agent 有时会执行危险命令（如 `git reset --force`），而完全可以使用更安全的替代方案。这体现了对 Agent 行为安全约束和“谨慎性”的更高要求。
    - **链接**: [Issue #22672](https://github.com/google-gemini/gemini-cli/issues/22672)

10. **[#22598] Feat: Subagent trajectory should be visible via `/chat share`**
    - **重要性**: ⭐⭐
    - **分析**: **P3 功能请求**。虽然优先级不高，但该请求反映了开发者对“可观察性”的追求。用户希望分享聊天记录时能包含子代理的执行轨迹，以便于调试、评估和协作。
    - **链接**: [Issue #22598](https://github.com/google-gemini/gemini-cli/issues/22598)

## 重要 PR 进展

以下 PR 揭示了当前社区开发者正在积极贡献的关键领域。

1.  **[#28481] fix(core): refresh MCP OAuth tokens with the stored client ID**
    - **重要性**: ⭐⭐⭐⭐⭐
    - **分析**: **P1 安全修复**。解决了 MCP（模型上下文协议）服务器 OAuth 令牌刷新时因未使用存储的 Client ID 而失败的问题。修复前，刷新失败会删除已存储的凭据，导致用户需要反复重新认证。
    - **链接**: [PR #28481](https://github.com/google-gemini/gemini-cli/pull/28481)

2.  **[#28401] fix(shell): bound command output sent to the model**
    - **重要性**: ⭐⭐⭐⭐⭐
    - **分析**: **P1 性能修复**。针对 Shell 工具将大量命令输出（如 `find /`）无限制地送入模型上下文，导致 Tokens 浪费和模型响应质量下降问题。此 PR 为输出大小设置了上限，是提升 CLI 性能和成本效益的关键改进。
    - **链接**: [PR #28401](https://github.com/google-gemini/gemini-cli/pull/28401)

3.  **[#28348] fix: resolve MaxListenersExceededWarning and infinite auth loop**
    - **重要性**: ⭐⭐⭐⭐
    - **分析**: 修复了两个关键问题：API 重试时的侦听器泄漏和 Windows 系统下 OAuth 成功后的无限循环认证。这对于提升 CLI 的稳定性和跨平台兼容性至关重要。
    - **链接**: [PR #28348](https://github.com/google-gemini/gemini-cli/pull/28348)

4.  **[#20079] fix: Recognize symlink agents in ~/.gemini/agents/**
    - **摘要**: 该 PR 旨在修复 Claude CLI 无法识别 `~/.gemini/agents/` 目录下符号链接的问题，这是一个用户期待已久的小但有用的改进。
    - **链接**: [PR #20079](https://github.com/google-gemini/gemini-cli/pull/20079)

5.  **[#28530] feat(caretaker-evals): add triage evaluation framework and judge runner**
    - **重要性**: ⭐⭐⭐⭐
    - **分析**: **“Caretaker Agent”** 项目的一部分，引入了一套用于评估 Issue 分诊效果的系统。这表明开发团队正致力于通过自动化评估来提升 AI Agent 处理社区反馈的可靠性。
    - **链接**: [PR #28530](https://github.com/google-gemini/gemini-cli/pull/28530)

6.  **[#28531] fix(a2a-server): normalize CRLF line endings to LF in getProposedContent**
    - **重要性**: ⭐⭐⭐
    - **分析**: 修复了 Windows 用户在使用 Gemini Code Assist 时，因行尾符（CRLF/LF）不匹配导致代码差异视图无法正常高亮的问题，对提升跨平台开发者体验有直接帮助。
    - **链接**: [PR #28531](https://github.com/google-gemini/gemini-cli/pull/28531)

7.  **[#28509] fix(core): filter out thought parts from getHistoryTurns**
    - **重要性**: ⭐⭐⭐
    - **分析**: 确保模型的内部思考过程不会泄露到历史记录中，这是一个重要的数据和隐私保护修复。
    - **链接**: [PR #28509](https://github.com/google-gemini/gemini-cli/pull/28509)

8.  **[#28523] fix(core): enforce explicit tag length and validation in file keychain**
    - **重要性**: ⭐⭐⭐
    - **分析**: 对基于文件的凭证存储（Keychain）增加了强制的认证标签长度和验证，增强了本地存储的加密安全性。
    - **链接**: [PR #28523](https://github.com/google-gemini/gemini-cli/pull/28523)

9.  **[#28517] fix(core): enforce HTTPS for GoogleCredentialsAuthProvider**
    - **重要性**: ⭐⭐⭐
    - **分析**: 强制要求 Google 凭证认证提供者使用 HTTPS 协议，防止网络传输中的凭据泄露，是重要的安全加固措施。
    - **链接**: [PR #28517](https://github.com/google-gemini/gemini-cli/pull/28517)

10. **[#28435] feat(pr-generator-core): add environment config parser, command executor, GitHub R…**
    - **摘要**: “PR Generator”系列 PR 的一部分，用于实现自动化 Issue 到 PR 的生成管线。这代表了对高级、自动化开发工作流的探索。
    - **链接**: [PR #28435](https://github.com/google-gemini/gemini-cli/pull/28435)

## 功能需求趋势

从过去 24 小时的 Issues 中，可以提炼出社区最关注的几个功能方向：

1.  **Agent 智能调度与行为优化**：社区普遍反映了 Agent（特别是子代理）在**任务规划**和**自动调用能力**上的不足。用户期望 Agent 能够更智能地判断何时使用技能、何时委派给子代理，避免挂起或错误汇报。
2.  **Agent 执行可靠性与可观察性**：对 Agent 执行结果的**确定性**和**透明度**需求强烈。包括修复“假成功”状态、公开子代理的执行轨迹、以及对 Agent 行为进行更精细的约束（如避免危险操作）。
3.  **安全性与隐私保护**：随着 Auto Memory 等功能的引入，用户对**数据脱敏**、**凭据管理**和**通信安全**的关注度显著上升。OAuth 流程的修复和 HTTPS 的强制要求都是这一趋势的直接体现。
4.  **跨平台兼容性与稳定性**：Shell 命令卡死、Wayland 环境下的 Bug 等问题，显示了社区对在 Linux、Windows 等不同环境下获得一致、稳定体验的期望。
5.  **开发者体验与内务管理**：社区对 CLI 的**可配置性**（如通过 symlink 配置 Agent）、**性能监控**（如输出截断）和**自动化的维护工具**（如 Caretaker Agent）表现出浓厚兴趣。

## 开发者关注点

今日的反馈揭示了开发者在实际使用中遇到的主要痛点：

-   **Agent 状态报告不可信**: `#22323` 和 `#21409` 等问题导致开发者无法信任 Agent 的汇报结果，必须额外人工验证，违背了使用 AI 工具提升效率的初衷。
-   **执行流程受阻**: `#25166` 中命令执行后卡死，以及 `#22465` 中创建应用时卡在交互式提示符，直接打断了开发流程，体验较差。
-   **配置与管理混乱**: `#24246` 工具过多导致请求失败，`#20079` 无法识别 symlink 以及 `#22267` Browser Agent 忽略设置，都体现出配置管理上的混乱和不一致。
-   **故障诊断困难**: `#21763` 指出 Bug 报告不包含子代理上下文，使得排查问题非常困难。`#21968` 中无法理解 Agent 为何不使用相关技能，也让开发者感到困惑。
-   **安全与合规隐忧**: `#26525` 中“事后编辑”机密信息的模式，以及 `#26522` 中无意义的循环重试，都让开发者对自动化功能的安全性和效率产生疑虑。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 — 2026-07-25

---

## 今日速览

- **v1.0.75 发布**：新增对 Claude Opus 5 的支持，修复了此前版本的多项关键问题。
- **社区焦点转向稳定性与性能**：大量 Issue 集中在终端滚动回退、Plan 模式权限回归、大会话 OOM 以及插件持久化等痛点，开发者反馈活跃。
- **仅 1 个 PR 被关闭（已撤回）**，无新增代码合入，社区近期更关注 bug 修复而非新功能。

---

## 版本发布

### v1.0.75（2026-07-24）
- 添加对 **Claude Opus 5** 模型的支持，用户可在 Copilot CLI 中选用该模型。
- 此前版本的已知问题（如僵尸进程、Ctrl+C 中断失效等）未在该版本中明确提及修复，但社区期待后续补丁。

---

## 社区热点 Issues（精选 10 条）

### 1. #2205 — 终端滚动失效（Terminator 用户受影响）
- **标签**：`area:terminal-rendering` | **状态**：Open  
- **摘要**：更新后鼠标滚轮无法上下滚动 agent 的输出历史，反而滚动输入历史。`--no-mouse` 参数也无济于事。  
- **社区反应**：13 条评论，14 👍，被认为是严重 UI 回归，影响日常使用。  
- 🔗 [Issue #2205](https://github.com/github/copilot-cli/issues/2205)

### 2. #1996 — 无法安装 anthropics/claude-plugins-official 市场
- **标签**：`area:plugins`, `area:installation` | **状态**：Open  
- **摘要**：安装官方 Claude 插件市场时因 `marketplace.json` 格式校验失败而报错，schema 不兼容。  
- **社区反应**：5 条评论，1 👍，插件生态入口受阻，影响扩展能力。  
- 🔗 [Issue #1996](https://github.com/github/copilot-cli/issues/1996)

### 3. #4188 — Plan 模式回归：误拦截 `gh` 等只读命令
- **标签**：`area:permissions`, `area:tools` | **状态**：Open  
- **摘要**：最新版本中 Plan 模式的命令门控将 `gh` CLI 的只读查询（如 `gh issue list`）判定为可能修改工作区，导致 Plan 过程受阻。  
- **社区反应**：4 条评论，3 👍，被认为是破坏性回归，影响基于 Plan 的自动化工作流。  
- 🔗 [Issue #4188](https://github.com/github/copilot-cli/issues/4188)

### 4. #4183 — 自动压缩无法防止 CAPI 5MB 请求体超限
- **标签**：`area:context-memory`, `area:models` | **状态**：Open  
- **摘要**：长时间工具密集型会话虽未超过模型上下文 token 限制，但序列化后的请求体超过 5MB，导致后续调用永久失败。自动压缩不阻止此问题。  
- **社区反应**：3 条评论，10 👍，高赞问题，暴露了会话管理的深层限制。  
- 🔗 [Issue #4183](https://github.com/github/copilot-cli/issues/4183)

### 5. #4163 — 子进程僵尸积累（v1.0.71）
- **标签**：`area:platform-linux`, `area:tools` | **状态**：CLOSED  
- **摘要**：Linux 上 `copilot` 进程未正确回收子进程，每个会话每分钟约产生 2 个僵尸进程，长时间运行后堆积严重。  
- **社区反应**：3 条评论，3 👍，虽已关闭但问题严重，影响服务器长期运行场景。  
- 🔗 [Issue #4163](https://github.com/github/copilot-cli/issues/4163)

### 6. #4220 — Plan 模式误报 `gh api GET/GraphQL` 为“可能修改工作区”
- **标签**：`area:permissions` | **状态**：Open  
- **摘要**：类似 #4188，Plan 模式下 `gh api` 的 GET 请求和 GraphQL 查询被误判为有写操作，导致被阻止。  
- **社区反应**：1 条评论，1 👍，进一步凸显 Plan 模式权限策略的缺陷。  
- 🔗 [Issue #4220](https://github.com/github/copilot-cli/issues/4220)

### 7. #4241 — 密码屏蔽功能反效果：浪费 token，影响 agent 执行
- **标签**：`area:tools` | **状态**：Open  
- **摘要**：读取包含（甚至测试）密码的文件时，密码被屏蔽导致 agent 找不到原始值，转而使用 Python 读取字节，陷入死循环。  
- **社区反应**：0 条评论，刚创建，但描述生动，引起关注。  
- 🔗 [Issue #4241](https://github.com/github/copilot-cli/issues/4241)

### 8. #4244 — 支持 VS Code Agent 会话中的 `/rename` 命令
- **标签**：`area:sessions`, `area:agents` | **状态**：Open  
- **摘要**：`/rename` 在终端 CLI 中工作正常，但在 VS Code Agent 窗口内无效，且 agent 无法调用重命名。  
- **社区反应**：0 条评论，跨 IDE 集成需求持续提升。  
- 🔗 [Issue #4244](https://github.com/github/copilot-cli/issues/4244)

### 9. #4251 — 恢复大型会话 OOM / CPU 100% 约 70 分钟（v1.0.74 回归）
- **标签**：`area:sessions` | **状态**：Open  
- **摘要**：v1.0.74 中恢复一个长期存在的巨大会话导致内存耗尽或单核满载约 70 分钟，v1.0.73 无此问题，确认回归。  
- **社区反应**：0 条评论，但问题严重，直接影响重度用户。  
- 🔗 [Issue #4251](https://github.com/github/copilot-cli/issues/4251)

### 10. #4252 — 会话退出时静默覆盖 `settings.json`，导致模型设置被还原
- **标签**：`area:sessions`, `area:models`, `area:configuration` | **状态**：Open  
- **摘要**：交互式会话退出时，将启动时的模型版本写回 `settings.json`，覆盖其他会话或手动修改，造成自我维持的过期默认值。  
- **社区反应**：0 条评论，新发现的数据丢失类 bug，影响配置稳定性。  
- 🔗 [Issue #4252](https://github.com/github/copilot-cli/issues/4252)

---

## 重要 PR 进展

过去 24 小时内仅有 **1 个 PR** 被关闭，且内容无实际变更：

### #4228 — 已撤回（Withdrawn）
- **标题**：Withdrawn: incorrect scope for #3534  
- **状态**：CLOSED  
- **摘要**：PR 本想修改文档，但实际应修改私有剪贴板运行时实现，作者自行撤回，源分支已删除。  
- **社区影响**：无  
- 🔗 [PR #4228](https://github.com/github/copilot-cli/pull/4228)

> 注：当日无其他活跃 PR，表明团队当前重心在修复 Issue 而非合并新功能。

---

## 功能需求趋势

从近期 Issue 中可提炼社区最关注的三大方向：

1. **IDE 集成与一致性**  
   - `/rename` 命令在 VS Code Agent 中不可用（#4244）  
   - 多人质疑终端 CLI 与 IDE 会话行为不一致，期望统一用户体验。

2. **性能与资源管理**  
   - 大会话 OOM（#4251）、僵尸进程堆积（#4163）、5MB 请求体限制（#4183）表明会话生命周期管理是当前最大短板。  
   - 自动压缩策略需重新设计，防止文件句柄和内存泄漏。

3. **模型与插件生态**  
   - v1.0.75 新增 Claude Opus 5 支持，但插件市场安装受阻（#1996）  
   - 用户期待更灵活的非交互式模式、SSH 主机别名支持（#4248）以及更智能的密码屏蔽（#4241）。

---

## 开发者关注点

- **Plan 模式权限误判**（#4188、#4220）：大量只读命令被错误阻止，直接打断了已有的自动化工作流，社区情绪较为不满。  
- **终端交互回退**（#2205）：滚动功能失效是常用操作，用户反映“几乎无法使用”。  
- **配置持久化问题**（#4252）：静默覆盖 `settings.json` 导致模型设置意外变更，可能引发连锁故障。  
- **会话恢复稳定性**（#4251）：从正常使用到完全不可用（OOM）的突然回归，表明测试覆盖不足。  
- **Plugin 市场可靠性**（#4247）：添加成功后不持久化，等同于无功能，严重打击第三方扩展信心。

> 建议开发团队优先修复 **#4188**（Plan 权限回归）、**#2205**（终端滚动）和 **#4251**（大会话 OOM），这三个问题直接影响日常生产力。同时重新评估命令行参数校验与配置持久化的设计，避免类似 #4252 的数据丢失风险。

---

*数据采集时间：2026-07-25 12:00 UTC*  
*来源：GitHub - github/copilot-cli*

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

好的，作为专注于AI开发工具的技术分析师，我已根据您提供的GitHub数据，为您生成2026-07-25的Kimi Code CLI社区动态日报。

---

# Kimi Code CLI 社区动态日报 | 2026-07-25

## 今日速览

今日Kimi Code CLI无新版本发布，但社区活跃度较高。新提交的`死循环（Dead Loop）`bug（Issue #2557）和`登录失败`问题（Issue #2556）成为开发者关注焦点。此外，关于`远程控制（Remote Control）`的功能请求（Issue #1282）获得了持续的关注和点赞，反映出用户对跨设备无缝编码体验的强烈需求。PR方面，社区贡献者致力于解决Windows平台兼容性和企业级网络环境下的SSL证书问题。

## 版本发布

*   **无**（过去24小时内无新Release）

## 社区热点 Issues

基于现有数据，共4个活跃Issue，均已收录。

**1. [Feature] 远程控制：从任何设备继续本地会话**
*   **Issue #1282** | **👍 16** | **评论 8**
*   **重要性：** 社区呼声最高的功能请求之一。它直击开发者“多设备协同工作”的痛点，允许用户从手机、平板或浏览器接管电脑上正在进行的CLI会话，实现工作流的无缝衔接。获得16个赞和8条评论，说明社区对此功能有强烈的通用需求。
*   **链接：** [MoonshotAI/kimi-cli Issue #1282](https://github.com/MoonshotAI/kimi-cli/issues/1282)

**2. [Bug] 死循环问题**
*   **Issue #2557** | **👍 0** | **评论 0**
*   **重要性：** 今日最新提交的严重Bug。用户使用v1.44.0版本时遇到“死循环”，这是导致程序无响应或资源耗尽的严重问题，需要开发团队优先排查。目前尚无社区讨论。
*   **链接：** [MoonshotAI/kimi-cli Issue #2557](https://github.com/MoonshotAI/kimi-cli/issues/2557)

**3. [Bug] `kimi login` 登录失败**
*   **Issue #2556** | **👍 0** | **评论 0**
*   **重要性：** 另一个新提交的阻塞性问题。用户在购买订阅后，于Linux ARM64平台使用`kimi-k3`模型通过OAuth登录失败。这是影响付费用户的第一道门槛，需紧急处理。
*   **链接：** [MoonshotAI/kimi-cli Issue #2556](https://github.com/MoonshotAI/kimi-cli/issues/2556)

**4. [Bug] 登录失败：无法连接到 auth.kimi.com:443**
*   **Issue #1070** | **👍 0** | **评论 7** | **已关闭**
*   **重要性：** 一个老问题，虽已关闭，但用户反馈了网络不可达导致的SSL连接失败。其关联的PR（#762）今日有更新，因此重新进入视野。这表明该问题在某些网络环境下可能仍存在。
*   **链接：** [MoonshotAI/kimi-cli Issue #1070](https://github.com/MoonshotAI/kimi-cli/issues/1070)

## 重要 PR 进展

基于现有数据，共2个活跃PR，均已收录。

**1. fix(tests): 改进Windows跨平台测试兼容性**
*   **PR #2558** | **今日更新**
*   **功能/修复：** 修复了测试套件在Windows上执行的两个问题：1） `Path.write_text()` 写入文件时未使用 `newline=""` 导致换行符被自动转换；2） 另一个未提及的跨平台问题。这是对代码健壮性和开发体验的提升，确保贡献者在Windows环境也能顺利运行测试。
*   **链接：** [MoonshotAI/kimi-cli PR #2558](https://github.com/MoonshotAI/kimi-cli/pull/2558)

**2. fix: 支持 `SSL_CERT_FILE` 环境变量，适配企业代理**
*   **PR #762** | **今日更新**
*   **功能/修复：** 这是一个久拖未决但极其重要的功能。它通过支持标准的`SSL_CERT_FILE`环境变量，解决了使用企业级代理（如Zscaler, BlueCoat）的用户遇到的SSL证书验证错误问题，使得Kimi CLI能在企业防火墙后正常工作。
*   **链接：** [MoonshotAI/kimi-cli PR #762](https://github.com/MoonshotAI/kimi-cli/pull/762)

## 功能需求趋势

从今日的 Issues 和 PR 中，可以提炼出社区对以下功能的关注：

1.  **跨设备/远程协作：** 以 `Remote Control` 功能为代表，用户希望打破物理设备限制，实现编码会话的远程接管和无缝流转。这是高端开发者对“云原生”编码体验的自然延伸。
2.  **企业级网络兼容性：** `SSL_CERT_FILE` 环境变量的支持，直接指向了企业开发者的核心痛点。这表明Kimi Code CLI正在或希望被应用于具有严格网络安全策略的企业环境。
3.  **跨平台稳定性：** 针对Windows测试兼容性的修复，虽然是小改动，但体现了社区对主流操作系统支持完善度的持续追求。

## 开发者关注点

主要痛点集中在**准入和稳定性**方面：

1.  **登录流程体验不佳：** 近期连续出现登录失败问题（#2556, #1070），尤其是出现在用户付费后，影响极其负面。登录流程的鲁棒性和对不同网络环境的适配需要加强。
2.  **核心功能稳定性：** `Dead Loop` 错误是严重的事故，它会直接导致工具不可用，必须得到最高优先级的关注和修复。
3.  **企业网络支持欠佳：** 使用企业代理无法正常连接（#1070），说明默认的SSL配置不够友好，影响了付费用户的第一印象。PR #762 如能合并，将极大改善这一局面。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

好的，这是为您生成的 2026-07-25 OpenCode 社区动态日报。

---

## 2026-07-25 OpenCode 社区动态日报

### 今日速览

今日社区焦点集中在 **Desktop v1.18.5 升级后出现的一系列兼容性问题**（#38789），以及一个由来已久且讨论热烈的 **CPU 性能问题**（#30086）。同时，一项关于未授权服务器配置导致 **加密货币挖矿安全漏洞**（#38857）的报告引发了对默认安全策略的讨论。此外，社区对 **会话生命周期管理**、**模型与服务透明度** 等功能的长期需求热度不减。

### 版本发布

**v1.18.5 发布** (`anomalyco/opencode Release v1.18.5`)

本次发布主要聚焦于核心稳定性与兼容性修复：
-   **Core**：针对 `Claude` 模型优化了自适应思考（adaptive thinking）的处理逻辑。
-   **OpenAI**：移除了可能导致对话中断的响应阶段处理机制。
-   **搜索**：修复了 `grep` 搜索结果中 `symlink` 路径未能保留的问题（贡献者：@remixz）。
-   **模型兼容性**：改进了 `Mistral` 模型在跨轮对话中的推理历史保留，并对其稳定性进行了增强。

### 社区热点 Issues

1.  **#30086：新版 OpenCode CPU 占用飙升**
    -   **重要性**：社区反馈最强烈的问题，35条评论，18人点赞。用户反映在近期版本更新后，从过去稳定运行10个会话到连3个都困难，并严重影响系统整体响应速度。
    -   **社区反应**：问题影响面广，用户期待能尽快定位并修复性能回归。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/30086)

2.  **#24649：[已关闭] OpenCode Go：明确哪些模型是自托管 vs. 通过第三方提供商代理**
    -   **重要性**：虽然已关闭，但获得了31个点赞，体现了用户对定价模式和服务透明度的核心关切。大家想知道“Go”计划中模型的真实成本和可靠性。
    -   **社区反应**：用户希望清晰了解OpenCode Go背后的基础设施，以做出更明智的决策。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/24649)

3.  **#38789：[Bug] Desktop v1.18.5：更新后项目重载出现“UnsupportedContentType”错误**
    -   **重要性**：最新版本的即时回归问题，有7条评论。用户更新到最新桌面版后，应用启动时立即报错，导致部分项目无法加载。
    -   **社区反应**：影响新版本的首日用户体验，需要紧急修复。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/38789)

4.  **#32747：`@` 文件引用不包含启动后创建的新文件**
    -   **重要性**：一个影响日常开发效率的Bug，12条评论。用户发现新创建的文件无法通过 `@` 命令找到，必须重启OpenCode。
    -   **社区反应**：用户指出问题根源是TUI的搜索状态未能实时更新。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/32747)

5.  **#16101：[功能请求] 会话生命周期管理**
    -   **重要性**：一个获得13个赞的长期功能请求。用户指出OpenCode会话无限制增长，缺乏TTL、自动清理和存储上限机制。
    -   **社区反应**：社区对该功能的呼声很高，认为这是保证应用稳健运行的核心基础设施。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/16101)

6.  **#38857：[安全] 通过未受保护的 `opencode web` 服务器部署的加密货币矿工**
    -   **重要性**：严重的默认安全配置问题。用户报告其主机因运行了未设置密码的 `opencode web` 服务器而被植入门罗币挖矿程序。
    -   **社区反应**：社区对默认监听 `0.0.0.0:4096` 且无认证机制表示担忧。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/38857)

7.  **#36677：[Bug， 核心] 长期运行的V2服务器进入持久分配循环**
    -   **重要性**：一个核心性能问题。长期运行的 `opencode2 serve` 进程会消耗约一个CPU核心和1.1-1.3 GB的RSS内存。
    -   **社区反应**：虽然评论不多，但对服务器端性能和资源占用有直接影响，值得团队关注。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/36677)

8.  **#34410：[功能请求] 支持在 TUI 提示符中使用 `@` 和 `/` 技能调用**
    -   **重要性**：社区期望将图形界面和CLI的便捷功能统一。用户希望能在TUI中直接通过 `@` 提及文件或使用 `/` 调用特定技能。
    -   **社区反应**：该功能被4人点赞，体现了开发者对更高效交互的追求。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/34410)

9.  **#37096：Web UI 会话列表为空——Windows/WSL上的项目自动注册失败**
    -   **重要性**：跨平台兼容性问题，用户需要在WSL环境中手动解决。Windows用户在特定配置下无法看到Web UI中的会话列表。
    -   **社区反应**：环境差异引起的可用性问题正在影响部分用户。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/37096)

10. **#38866：子代理流错误可能导致空的执行结果**
    -   **重要性**：一个较难察觉的Bug。当子代理的流式调用失败时，系统可能返回一个 `空的成功结果` 而不是错误信息，容易被用户忽略。
    -   **社区反应**：用户指出这会影响自动化工作流的可靠性，因为父模型可能误认为任务已成功。 → [查看 Issue](https://github.com/anomalyco/opencode/issues/38866)

### 重要 PR 进展

1.  **#38872：[贡献] 重构(tui)：提取事件流连接**
    -   **内容**：将事件流重连逻辑从主循环中提取出来，单独封装，提高了代码的模块化和可维护性。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38872)

2.  **#38825：[已关闭] 修复(core)：在作用域清理时关闭 Promise 插件的事件订阅**
    -   **内容**：修复了长期运行V2服务器内存泄漏/CPU高占用问题（关闭#36677）。修正了Promise插件未正确注销事件订阅的问题。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38825)

3.  **#38871：[开发中] 修复(session)：在撤销清理后重新分配孤儿助手消息**
    -   **内容**：修复了 `/undo` 操作后，部分助手消息可能成为孤儿（失去父节点）的问题，保证了会话历史的一致性。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38871)

4.  **#38870：[已关闭] feat(tui)：配置工具详细信息的可见性**
    -   **内容**：新增 `tool_details` 配置项，允许用户默认折叠/展开工具的输出内容，提供更清爽的体验。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38870)

5.  **#38728：[开发中] 修复：在 Safari IME 输入期间保持提示输入静止**
    -   **内容**：修复了Safari浏览器下输入中日韩（CJK）文字时，IME（输入法编辑器）会意外中断的问题。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38728)

6.  **#35324：[开发中] 修复(zen)：为 Zen 的 Google 请求去除认证头**
    -   **内容**：修复了 `opencode zen` 模式在向 Google 发送请求时，可能错误携带了OpenCode API密钥的问题，避免敏感信息泄露。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/35324)

7.  **#38862：[开发中] feat(app)：添加固定侧边栏选项**
    -   **内容**：新增“固定侧边栏”开关，开启后侧边栏将始终展开，无法通过切换或快捷键收起，满足部分用户习惯。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38862)

8.  **#35400：[开发中] feat(opencode)：任务信号——结构化返回、简洁完成、稀疏上下文、消息唤醒**
    -   **内容**：一个重大的功能集改进，为任务工具增加了结构化返回、简洁完成提示、稀疏上下文和“消息唤醒”能力，旨在优化代理间的协作效率。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/35400)

9.  **#38834：[已关闭] 修复：Markdown 渲染**
    -   **内容**：使用基于 `marked` 的渲染器替换了旧的 `<markdown>` 组件，将Markdown转换为ANSI，修复了部分终端下Markdown显示不佳的问题。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/38834)

10. **#26861：[开发中] 修复(tui)：长会话中旧消息消失**
    -   **内容**：引入懒加载滚动，解决了长对话中向上滚动加载历史消息时，部分内容丢失的问题（关闭#7380）。
    -   **链接**：[查看 PR](https://github.com/anomalyco/opencode/pull/26861)

### 功能需求趋势

从今日的Issues中，可以提炼出社区最关注的功能趋势：

1.  **性能与资源优化**：高CPU占用（#30086）、内存泄漏（#36677）和会话无限增长（#16101）是用户最核心的痛点。社区希望应用能更高效、更可持续地运行。
2.  **模型与服务透明度**：用户不再满足于黑盒使用，对OpenCode Go等服务背后的模型托管方式和成本策略（#24649）有更清晰的了解需求。同时，对新模型（如Nvidia NIM）的支持（#38865）呼声不减。
3.  **会话管理与导航**：除了生命周期管理（#16101），用户还希望在长对话中能轻松导航/跳转（#38821），并支持浏览和恢复历史会话（#38858）。
4.  **安全与合规**：未授权访问导致的挖矿（#38857）是一个严重警告。社区更重视默认安全配置，并对支付（#20252）、计费逻辑（#38869）等商业条款的简洁和合规性提出要求。
5.  **交互与UI增强**：包括对TUI中`@`和`/`技能调用（#34410）、桌面版Sidebar固定（#38862）、和 Safari 浏览器兼容性（#38728）的改进需求，体现了从“能用”到“好用”的期望。

### 开发者关注点

-   **升级兼容性**：每次新版本发布，其与旧项目的兼容性（#38789）是开发者最关心的问题之一。
-   **环境配置**：跨平台（Windows/WSL）的环境差异导致的可用性问题（#37096）依然是痛点。
-   **模型选择与灵活性**：开发者希望绑定非官方/第三方模型（如Cursor）时，能不受限制地使用Provider Hook（#38836）。
-   **输入体验**：移动端（#38850）和特定浏览器（如Safari， #38728）下的输入体验问题，对部分用户来说是最直接的障碍。
-   **文档不完善**：用户报告发现官方文档中示例链接失效（#38867），影响了新用户对功能的了解和上手体验。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 | 2026-07-25

## 今日速览

Pi v0.82.1 正式发布，核心亮点是 **Claude Opus 5 的支持**（Anthropic / Bedrock），并附带自适应思考与提示缓存。社区提交活跃：50 条 Issue 和 21 个 PR 在过去 24 小时内更新，性能（TUI 高 CPU、Compaction 截断）与跨平台兼容性（WSL 路径、OpenRouter SSH 登录）是今日最热门的讨论话题。

## 版本发布

### [v0.82.1](https://github.com/earendil-works/pi/releases/tag/v0.82.1) — 新功能摘要

- **Claude Opus 5** — 在 Anthropic 和 Amazon Bedrock 上可用，支持自适应思考（含 `xhigh` 模式）、推理配置文件（Inference Profiles）和提示缓存（Prompt Caching）。
- 详见[Provider 文档](https://github.com/earendil-works/pi/blob/v0.82.1/packages/coding-agent/docs/providers.md#api-keys)。

## 社区热点 Issues（精选 10 条）

1. **#6665 [OPEN] TUI 在流式响应时吃满单核 CPU**  
   ➤ 原因：`Intl.Segmenter` 未缓存 + 每次 chunk 都完全重建 Markdown。  
   ➤ 社区反应：7 条评论，无点赞，但严重影响长时间会话体验。  
   [GitHub](https://github.com/earendil-works/pi/issues/6665)

2. **#7020 [OPEN] 压缩（Compaction）后 Pi 不继续响应**  
   ➤ 发生在长期运行的协调器会话中，压缩后模型无输出。  
   ➤ 4 条评论，1 人赞同，属于中等严重度但影响高频用户。  
   [GitHub](https://github.com/earendil-works/pi/issues/7020)

3. **#6948 [CLOSED] llama.cpp 提供者：defaultProvider/defaultModel 启动时不生效（竞态）**  
   ➤ 因异步模型刷新导致默认模型未正确设置，引发多次错误。  
   ➤ 已通过 #7072 PR 修复，但仍值得关注。  
   [GitHub](https://github.com/earendil-works/pi/issues/6948)

4. **#7064 [OPEN] WSL 下绝对 Windows 路径处理错误**  
   ➤ 导致 `read`/`write`/`edit` 工具失败，回退到命令行。  
   ➤ Windows 用户高频痛点，3 条评论。  
   [GitHub](https://github.com/earendil-works/pi/issues/7064)

5. **#7090 [CLOSED] 重新生成 0.82.x shrinkwrap 以修复 brace-expansion 漏洞**  
   ➤ CVE-2026-14257 导致内存耗尽 DoS，需要升级依赖。  
   ➤ 3 条评论，安全相关，已合并。  
   [GitHub](https://github.com/earendil-works/pi/issues/7090)

6. **#7077 [CLOSED] 任务完成后状态仍显示“Working…”**  
   ➤ 用户困惑是否仍在处理，3 条评论。  
   [GitHub](https://github.com/earendil-works/pi/issues/7077)

7. **#7048 [OPEN] Compaction 摘要生成时若达到 token 上限会截断在单词中间**  
   ➤ 未检查 `stopReason: "length"`，导致保留不完整的句子。  
   ➤ 3 条评论，影响上下文质量。  
   [GitHub](https://github.com/earendil-works/pi/issues/7048)

8. **#7069 [CLOSED] 升级到 v0.82.0 后 bash 工具持续验证失败**  
   ➤ 用户广泛遇到，3 条评论，影响日常工作流。  
   [GitHub](https://github.com/earendil-works/pi/issues/7069)

9. **#7087 [CLOSED] 允许通过 RPC 调用 refreshModels**  
   ➤ 目前强制 4h 等待窗口，无法程序化触发，用户提供 hack。  
   [GitHub](https://github.com/earendil-works/pi/issues/7087)

10. **#7067 [CLOSED] 模型中切换导致会话损坏**  
    ➤ GPT HTML 错误、Qwen 400 错误、缺少预切换验证。  
    ➤ 用户经过详细复现，开发关注度高（3 条评论）。  
    [GitHub](https://github.com/earendil-works/pi/issues/7067)

## 重要 PR 进展（精选 10 条）

1. **#7114 [OPEN] 为 OpenRouter OAuth 登录添加手动重定向 URL 回退**  
   ➤ 解决 SSH / 容器中无法使用本地回调服务器的场景。  
   [GitHub](https://github.com/earendil-works/pi/pull/7114)

2. **#7112 [CLOSED] 修复 Windows 下 footer 路径分隔符显示**  
   ➤ `~` 缩写后仍显示反斜杠，改为始终使用前斜杠。  
   [GitHub](https://github.com/earendil-works/pi/pull/7112)

3. **#7111 [CLOSED] 支持持久化的外部工具结果**  
   ➤ 工具可返回 `defer: true`，Pi 持久化调用并等待外部结果。  
   [GitHub](https://github.com/earendil-works/pi/pull/7111)

4. **#7110 [OPEN] 防止启动时 session 切换导致重复消息**  
   ➤ 解决特定场景下的消息重复问题。  
   [GitHub](https://github.com/earendil-works/pi/pull/7110)

5. **#7106 [CLOSED] 修复资源加载器尝试读取目录的问题**  
   ➤ 防止 `EISDIR` 警告。  
   [GitHub](https://github.com/earendil-works/pi/pull/7106)

6. **#7091 [CLOSED] 拒绝重叠的用户 bash 命令**  
   ➤ 通过 RPC 调用防止并发冲突。  
   [GitHub](https://github.com/earendil-works/pi/pull/7091)

7. **#7072 [CLOSED] 缓存 llama.cpp 模型目录**  
   ➤ 修复 #6948 默认模型不生效的竞态问题。  
   [GitHub](https://github.com/earendil-works/pi/pull/7072)

8. **#7081 [CLOSED] 支持 Bedrock 上的 Claude Opus 5**  
   ➤ 配置自适应思考，修复错误消息显示。  
   [GitHub](https://github.com/earendil-works/pi/pull/7081)

9. **#7085 [CLOSED] 添加 vitest eval 测试框架**  
   ➤ 引入 `packages/evals`，支持 Pi SDK 评估。  
   [GitHub](https://github.com/earendil-works/pi/pull/7085)

10. **#7082 [CLOSED] 优化 TUI 性能：O(viewport) 渲染**  
    ➤ 通过视口裁剪 + 控件 memoization 解决大 transcript 下的输入延迟。  
    [GitHub](https://github.com/earendil-works/pi/pull/7082)

## 功能需求趋势

- **新模型支持**：Claude Opus 5 发布后，社区立即要求添加 xAI Grok 4.5 长上下文定价、OpenRouter Inkling 输出上限修复。**模型切换验证**（上下文窗口、thinking 块转换）成为高频改进点。
- **性能与可观测性**：TUI 渲染性能（#6665, #7082）、Compaction 截断（#7048）、状态提示不准确（#7077）是开发者最关心的稳定性问题。
- **跨平台兼容**：WSL 路径（#7064）、Windows 路径显示（#7112）、OpenRouter SSH 登录（#7114）反映出越来越多用户在多平台部署 Pi。
- **可配置性与扩展**：工具输出截断限制可配置（#7066）、session-affinity 头转发给自定义Provider（#7108/#7107）、模型刷新 RPC（#7087）、成本预览 UI（#7101）等，表明社区希望 Pi 更灵活、可集成。
- **安全与依赖**：brace-expansion 漏洞修复（#7090）提示开发者对供应链安全的关注。

## 开发者关注点

- **模型切换损坏**：多位用户报告跨模型切换（如 Qwen ↔ GPT）导致会话中断，缺乏预校验和 thinking 块转换。
- **Compaction 行为不稳定**：压缩后模型不继续（#7020）或摘要截断（#7048），影响长期会话可靠性。
- **TUI 高 CPU 与状态不准**：流式渲染吃满单核，且任务完成后仍显示“Working…”造成混淆。
- **默认模型不生效**：llama.cpp 提供者启动时竞态（#6948）虽已修复，但用户期待彻底解决方案。
- **命令行忽视环境变量**：`--provider openai` 忽略 `OPENAI_API_BASE`（#7105），对使用兼容 API 的用户造成困扰。
- **验证错误频发**：升级后 bash 工具验证失败（#7069）、openai-completions 处理 array content 和 custom 字段问题（#7097）等，影响工具链稳定性。

---

*数据来源：[earendil-works/pi GitHub](https://github.com/earendil-works/pi)*

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 — 2026-07-25

## 今日速览
今日发布 `v0.21.0-nightly` 版本，修复了洞察天数/小时数的时区计算问题。社区活跃度持续高涨：**27 条 Issue** 与 **50 条 PR** 在过去 24 小时内有更新，其中渲染性能、IME 兼容性、子代理模型控制及自动化工具链成为讨论热点。CI 故障与 Session 恢复问题被标记为高优先级，开发者正密集响应。

---

## 版本发布

### v0.21.0-nightly.20260725.1183a4c82
- **修复** `insight` 命令中天数/小时的时区计算，统一使用本地时间。
- **重构** `autofix` 模块的扩展逻辑（`refactor(autofix): ext`）。
- [查看 Release 详情](https://github.com/QwenLM/qwen-code/releases/tag/v0.21.0-nightly.20260725.1183a4c82)

---

## 社区热点 Issues（10 个精选）

### 1. 🐛 终端回复行覆盖问题（#5800）
- **标签**：P2 / bug / 渲染
- **问题**：在默认 TUI 模式下，若回复内容高于终端高度，最后一行会在渲染完成后被覆盖隐藏。
- **社区反应**：8 条评论，上游已关联 `Ink#973`，多位用户请求紧急修复。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/5800)

### 2. 🚀 外部上下文提供者配置文件（#7585）
- **标签**：P3 / feature-request / MCP 扩展
- **问题**：提议新增“直接外部上下文提供者”扩展，使 CLI 进程可共享管理员绑定的外部知识服务。
- **社区反应**：6 条评论，讨论集中在安全性与 MCP 协议兼容性。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7585)

### 3. 🐛 错误码 520/522（#7665）
- **标签**：P3 / bug / 集成
- **问题**：Qwen Code 桌面版启动后显示 520/522 错误，用户无法继续编码。
- **社区反应**：5 条评论，需要用户提供更多日志信息，状态为 `need-information`。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7665)

### 4. 🐛 Command 模式下输入法候选框位置偏移（#7684）
- **标签**：P2 / bug / macOS
- **问题**：当 `statusline` 显示多行时，输入法（IME）候选框远离光标位置，影响输入体验。
- **社区反应**：5 条评论，已有 PR #7711 提出修复方案。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7684)

### 5. ⚡ 冷启动性能优化：延迟加载候选模块（#7264）
- **标签**：P2 / enhancement / 性能
- **问题**：ACP 子进程冷启动时静态导入 17.24 MiB / 2420 个模块，提出继续执行延迟加载的审计建议。
- **社区反应**：5 条评论，核心开发者已标记为性能优化里程碑。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7264)

### 6. 🚀 CLI 缺少 Token 用量显示（#7719）
- **标签**：P3 / feature-request / UI
- **问题**：CLI 界面不显示 Token 消耗量与配额百分比，用户无法监控使用情况。
- **社区反应**：3 条评论，社区呼声较高，期待在 `/stats` 命令中集成。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7719)

### 7. 🚀 保护性 `pinned/` 内存目录（#6801）
- **标签**：P2 / feature-request / 内存管理
- **问题**：希望新增 `pinned/` 子目录，其内容只读且不受 `/dream` 压缩影响。
- **社区反应**：3 条评论，已有对应 PR #7714 在实现中。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/6801)

### 8. 🚀 显式数学编写语法契约（#7700）
- **标签**：feature-request / 渲染 / Markdown
- **问题**：提议采用更可移植、明确的数学公式语法，以统一终端渲染、复制、表格和流式场景。
- **社区反应**：3 条评论，与已合并的修复 PR #7699 关联。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7700)

### 9. 🐛 QQ Bot Session 恢复崩溃（#7721）
- **标签**：P1 / bug / Session 管理
- **问题**：Bridge 重启后 `AcpBridge.loadSession()` 返回 `undefined`，导致 QQ 频道机器人会话恢复异常。
- **社区反应**：2 条评论，已被标记为 P1 高优先级，对应修复 PR #7722 已提出。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7721)

### 10. 🐛 多技能连续输入时自动补全失效（#7717）
- **标签**：P2 / bug / 交互
- **问题**：在一行或连续多行中输入多个技能（如 `/skill1 /skill2`）时，只有第一个技能能触发自动补全。
- **社区反应**：2 条评论，状态为 `ready-for-agent`，已有 PR #7720 提供修复。
- [查看 Issue](https://github.com/QwenLM/qwen-code/issues/7717)

---

## 重要 PR 进展（10 个精选）

### 1. 🐛 修复底部粘滞虚拟列表视口（#7652）
- **状态**：OPEN
- **内容**：当列表项填充不够时，虚拟化列表会错误地“粘”在底部，导致滚动异常。该 PR 通过修正 viewport 计算解决此问题。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7652)

### 2. 🚀 子代理生成时模型等级选择（#7702）
- **状态**：Draft 🚧
- **内容**：为 `agent` 工具增加 `model` 参数，允许 AI 在调用时选择 Small/Medium/High/Super 等模型等级。对应 Issue #7685。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7702)

### 3. 🐛 默认启用虚拟化终端历史（#5738）
- **状态**：OPEN
- **内容**：将交互式 CLI 的虚拟化历史功能设为默认开启，新用户无需手动配置即可获得应用内可滚动历史视图。仍可通过 `ui.useTerminalBuffer` 关闭。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/5738)

### 4. 🐛 修复连续技能斜杠命令补全（#7720）
- **状态**：OPEN
- **内容**：恢复堆叠输入中后续技能的自动补全，区分行首、行中及模型粘贴等场景。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7720)

### 5. 🐛 修复 CI 分类状态标记冲突（#7723）
- **状态**：OPEN
- **内容**：工作流发布的 `stage=status` 标记与智能体的重复守卫模式冲突，导致智能体跳过实际分析。PR 重命名标记避免碰撞。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7723)

### 6. 🐛 修复 QQ Bot Session 加载逻辑（#7722）
- **状态**：OPEN
- **内容**：`AcpBridge.loadSession()` 现在返回输入的 `sessionId` 而非 `response.sessionId`（ACP 协议故意省略），并修复了 `catch` 分支错用 `sessionId` 的问题。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7722)

### 7. 🐛 本地 OpenAI 后端默认关闭 Follow-up 建议（#5821）
- **状态**：OPEN
- **内容**：当后端为本地 OpenAI 兼容（通过 loopback 地址访问）时，`ui.enableFollowupSuggestions` 默认设为 `false`，避免无效请求。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/5821)

### 8. 🐛 修复 Footer 更新后 IME 光标对齐（#7711）
- **状态**：OPEN
- **内容**：当多行 statusline 触发新交互帧时，将终端硬件光标保持在与渲染输入光标一致的位置，解决 IME 候选框偏移问题。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7711)

### 9. 🚀 技能默认禁用状态可覆盖（#7357）
- **状态**：OPEN
- **内容**：新增 `skills.defaultDisabled` 软默认值与 `skills.enabled` 显式启用列表，原 `skills.disabled` 保持高优先级。支持大小写不敏感匹配。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7357)

### 10. 🐛 批准 exit_plan_mode 后红 Action 计划参数（#7197）
- **状态**：OPEN
- **内容**：当用户批准 `exit_plan_mode` 后，工具调度器将历史记录中的 `plan` 参数替换为指向计划文件的短指针，避免泄露完整计划内容。
- [查看 PR](https://github.com/QwenLM/qwen-code/pull/7197)

---

## 功能需求趋势

从今日 Issue 与 PR 中提炼出社区最关注的五大方向：

1. **子代理模型等级控制**：Issue #7685 与对应 PR #7702 显示社区希望 AI 能够按需选择不同等级的模型（Small/Medium/High）驱动子代理，提升场景灵活性。
2. **渲染与输入法兼容性**：多个 Issue（#5800、#7684、#7719）集中投诉终端渲染、IME 候选框偏移及 Token 用量缺失，表明 TUI 的视觉反馈与输入体验是当前用户的主要痛点。
3. **性能持续优化**：Issue #7264 的冷启动延迟加载审计，以及 PR #5738 默认启用虚拟化历史，反映社区对启动速度和交互流畅性的持续关注。
4. **自动化与 CI/CD 增强**：PR #7710（沙箱验证通道）、PR #7723（CI 标记修复）以及 Issue #7712（E2E 测试失败）说明开发者正在强化自动化测试与工作流可靠性。
5. **外部集成扩展**：Issue #7585（外部上下文提供者）、#7687（钉钉图片传输）、#7697（Unity MCP 连接失败）等表明用户希望 Qwen Code 与更多外部工具（MCP、IM 平台）深度整合。

---

## 开发者关注点

- **终端显示Bug高频**：至少 3 个 Issue 涉及渲染/滚动/IME 光标问题，修复 PR #7711、#7652 正在处理，但用户反馈“每次按键终端上滚”等体验问题仍待系统解决。
- **Session 恢复严重缺陷**：P1 级别 Issue #7721 指向 QQ Channel 机器人的 Session 恢复完全失效，对应 PR #7722 已提交，需要优先合入。
- **技能自动补全断裂**：连续技能输入时补全失效（#7717）影响日常使用效率，社区期待 PR #7720 尽快合并。
- **配置灵活性不足**：Issue #7658 指出流式速率限制重试延迟（60s/120s/240s）硬编码，用户无法自定义；类似地，#6801 的 `pinned/` 目录保护需求也暗示用户希望更细粒度的文件控制。
- **CI 稳定性**：Issue #7712 报告主分支 E2E 测试失败，虽然 bot 自动创建了跟踪 Issue，但需开发者确认根因。

> 本文档由 AI 自动生成，数据来源于 [QwenLM/qwen-code](https://github.com/QwenLM/qwen-code) 仓库，时间范围：2026-07-25 00:00 UTC — 2026-07-25 23:59 UTC。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# DeepSeek TUI 社区动态日报 | 2026-07-25

数据来源：github.com/Hmbown/CodeWhale（原名 deepseek-tui，现已更名为 CodeWhale）

---

## 1. 今日速览

- **v0.9.1 正式发布**，但遗留的容器镜像和 Homebrew 分发仍卡在 v0.9.0，团队已提交修复 PR；同时项目正式更名为 **CodeWhale**，旧 npm 包 `deepseek-tui` 已弃用。
- **大量性能与架构重构 PR 合并**：App 神对象（7,205 行）被拆分为子模块，测试夹具从 87 处冗余文字减少为共享构造函数，为 v0.9.2 的稳定性奠定基础。
- **国际化成为社区焦点**：一天内提交了 7 个新语言支持 Issue（法、德、加泰罗尼亚、印地、印尼、乌克兰等），以及全面的本地化矩阵 CI 方案，反映出全球化部署的强烈需求。

---

## 2. 版本发布

### v0.9.1

- **概述**：这是 CodeWhale 作为 Shannon Labs 产品线的首次发布。旧 `deepseek-tui` npm 包已弃用，不再接收更新；所有后续版本均以 `codewhale` 命令和 npm 包交付。
- **发布状态**：GitHub Release 含 34 个资产，18 个 crate 已同步到 crates.io，npm latest 标签已更新，CNB 镜像标签已存在。但 **GHCR 容器镜像和 Homebrew tap 仍停留在 v0.9.0**，官方已提交修复工作流（PR #4801, #4802）。
- **链接**：https://github.com/Hmbown/CodeWhale/releases/tag/v0.9.1

---

## 3. 社区热点 Issues（10 条）

### #4520 - 在头部栏添加可配置的会话 token 细分
- **标签**：enhancement, ux, v0.9.2
- **摘要**：PR #2411 将 token 状态栏压缩为单一累计值，但用户希望恢复输入/缓存/输出三段的详细显示，并支持配置。
- **评论**：4 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4520

### #3927 - 为首次引导添加无提供者依赖的离线浏览路径
- **标签**：enhancement, onboarding, v0.9.2
- **摘要**：当前首次启动无论选择哪个提供者都会激活模型连接，用户希望有一条完全离线、无需 API Key 就能探索 UI 的路径。
- **评论**：3 | **链接**：https://github.com/Hmbown/CodeWhale/issues/3927

### #3314 - 将 App 神对象状态提取到子模块（已关闭）
- **标签**：refactor, god-object, v0.9.2
- **摘要**：`App` 结构体携带 ~252 个公有字段，`impl App` 块有 ~236 个方法、~4,450 行代码。需要拆分以提高可维护性（今日已通过 PR #4827 关闭）。
- **评论**：3 | **链接**：https://github.com/Hmbown/CodeWhale/issues/3314

### #3928 - 应用内无法阅读 constitution，自定义覆写静默失败
- **标签**：bug, ux
- **摘要**：constitution 是整个基座提示，但安装版未提供 `system_prompt` 路径，用户自定义 constitution 文件若无环境变量标记会静默不生效。
- **评论**：2 | **链接**：https://github.com/Hmbown/CodeWhale/issues/3928

### #4828 - macOS 上 underwater shell 破坏 open/osascript/launchctl
- **标签**：bug, macOS
- **摘要**：v0.9.0 引入的 "underwater" 交互式 shell 导致 `open`、`osascript`、`launchctl` 返回退出码 -54（操作不允许），降级到 v0.8.67 可恢复。
- **评论**：1 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4828

### #4406 - 区分已配置的提供者/MCP 与活跃健康状态
- **标签**：bug, enhancement, v0.9.2
- **摘要**：当前诊断报告将“已配置但未启用”的提供者标记为“down”，造成误报。需求是明确区分“配置存在”与“服务健康”。
- **评论**：1 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4406

### #4832 - `codew model resolve` 忽略配置的提供者和模型，总是回退到 DeepSeek
- **标签**：bug
- **摘要**：配置为 zai provider 和 GLM-5.2 模型时，`codew model resolve` 仍报告解析为 `deepseek-v4-pro`，且 `used_fallback: true`。三处错误。
- **评论**：0 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4832

### #4829 - 配置验证拒绝非 DeepSeek 提供者的模型（已关闭）
- **标签**：bug, validation
- **摘要**：`Config::validate()` 使用 DeepSeek-only 的模型标准化器，导致任何非 DeepSeek 模型（如 zai/GLM-5.2）的配置启动即报错，修复已合并。
- **评论**：0 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4829

### #4831 - 完整测试套件间歇性写入用户实际配置文件
- **标签**：bug, test flakiness
- **摘要**：运行 `cargo test --all-features` 同一棵树两次结果不同，与开发者的实际 `~/.codewhale/config.toml` 被写入相关。潜在数据安全风险。
- **评论**：0 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4831

### #4788 - 添加法语、德语和加泰罗尼亚语言本地化
- **标签**：enhancement, localization
- **摘要**：目前 9 个地区的本地化矩阵中不含任何西欧语言（除英语），而项目已为拉丁美洲交付完整包。用户希望增加这三大欧洲语言。
- **评论**：1 | **链接**：https://github.com/Hmbown/CodeWhale/issues/4788

---

## 4. 重要 PR 进展（10 条）

### #4827 - 将 App 神对象状态拆分为子模块（已合并）
- **描述**：将 7,205 行的 `app.rs` 拆分为 `init.rs`、`state.rs`、`commands.rs` 等独立文件，纯代码移动，无行为变更。关闭 #3314。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4827

### #4806 - 统一测试夹具：用共享构造函数替代 87 处 TuiOptions 文字（已合并）
- **描述**：28 个测试模块中 `create_test_app` 被复制粘贴，共 87 处文字。现统一为单点定义，增加字段只需编辑一处。关闭 #3923。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4806

### #4826 - 用真实产品页面替换文档索引（已合并）
- **描述**：docs.codewhale.net 首页原为源码文件列表链接。现替换为真正的产品文档页（Fleet/Sandbox/Configuration 等），遵循已有的 Modes 页面模式。部分关闭 #4800/#3984。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4826

### #4830 - 修复配置验证：针对活跃提供者校验 default_text_model（已合并）
- **描述**：修复 #4829，`Config::validate()` 现在使用活跃提供者的模型列表而非仅 DeepSeek 列表进行校验，确保 setup 向导写入的配置启动正常。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4830

### #4804 - v0.9.2 审计集群 + constitution 前缀 + TUI 清理（已合并）
- **描述**：合并至未发布的 v0.9.2 分支，包含审计 bug 集群、constitution/prefix 修复以及 TUI 可靠性与 UX 增强。工作区版本保持 0.9.1。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4804

### #4824 - 删除 composer 中冗余的 "Draft" 标题（已合并）
- **描述**：多行草稿模式下 composer 边框显示灰色 `Draft` 文字，用户已然知晓，予以移除。历史搜索标题保留。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4824

### #4805 - i18n(zh-Hans)：更新中文翻译至最新 en.json（Open）
- **描述**：同步 17 条消息键，涵盖命令描述、快捷键标签、主页提示和引导文本。纯翻译更新。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4805

### #4801 - CI：为衍生渠道（docker, homebrew）添加恢复路径（已合并）
- **描述**：v0.9.1 发布后容器镜像和 Homebrew tap 仍为 v0.9.0，新增工作流输入参数 `republish_channels` 允许手动重新发布这些渠道。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4801

### #4776 - CI：自动部署 codewhale.net（main 推送时）（已合并）
- **描述**：之前部署 job 仅支持 `workflow_dispatch`（手动触发），导致网站长期落后于 main。现在每次 push 到 main 自动触发部署。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4776

### #4768 - 文档：采纳“意图即工件”为 agent 操作准则（已合并）
- **描述**：记录 agent 工作新原则：基于当前的 main 分支生成代码比恢复/变基/调和旧代码更便宜、更快。更新 `AGENTS.md` 和 `CLAUDE.md`。
- **链接**：https://github.com/Hmbown/CodeWhale/pull/4768

---

## 5. 功能需求趋势

从过去 24 小时更新的 50 个 Issue 中，社区最关注的功能方向前三：

1. **国际化与本地化扩展**（约 20% 的 Issue）
   - 新增语言支持（法、德、加泰、印地、印尼、乌克兰、俄语）
   - 要求本地化矩阵包含 TUI 语言包，并在 CI 中监测漂移
   - 语言响应规则：constitution 为英文，回答使用用户语言，且需节省 token

2. **性能优化与 TUI 帧率改进**（约 15%）
   - 渲染函数中的同步文件系统调用（sidebar memory-file stat、Review read_dir）
   - 工具折叠每帧重新扫描全历史、重新分配 cell map
   - 流式解析时 O(N²) 的 markdown 重解析
   - 文件选择器（Ctrl+P）同步执行 git status 和 20k 文件遍历

3. **架构重构与代码拆分**（约 10%）
   - 神对象 App 拆分（今天已通过 PR #4827 完成）
   - 测试夹具统一
   - 配置验证清理（支持非 DeepSeek 模型）

其他活跃方向：Workflow 运行时与模型工具连接（#2974）、Onboarding 体验改进（离线路径 #3927）、macOS 兼容性问题（#4828）。

---

## 6. 开发者关注点

- **macOS 兼容性剧痛**：v0.9.0 引入的 underwater shell 导致 `open`/`osascript`/`launchctl` 等系统命令失败（退出码 -54），迫使部分用户降级回 v0.8.67。这可能是由于沙箱权限或 TCC 问题引起的，需要紧急修复。
- **配置验证过于严格**：非 DeepSeek 提供者的模型名被拒绝（#4829），导致 setup 向导自写的配置也无法启动。虽然今天已修复，但该问题暴露了验证层对多提供者支持的不完整。
- **测试套件可能污染用户环境**：`cargo test --all-features` 偶发性地写入真实 `~/.codewhale/config.toml`（#4831），这是一个严重的数据安全问题——用户可能无意中丢失配置或向测试泄漏敏感信息。
- **模型解析逻辑混乱**：`codew model resolve` 完全忽略配置，硬编码 DeepSeek 作为 fallback（#4832），导致用户以为使用了 GLM 或 Zai，实际得到的是 DeepSeek。信任度受挫。
- **文档网站问题**：docs 首页曾是源文件索引而非产品文档（#4800，今天已修复），且网站因未配置自动部署而滞后于代码变更（#4776，今天已修复）。开发者期望文档质量与代码同步。

---

**总结**：今日是 CodeWhale 从 DeepSeek TUI 改名后的第一个稳定发布日，技术债清理（拆神对象、统一测试）和文档建设取得显著进展。但 macOS 兼容性、多提供者支持完整性、以及测试安全是必须优先解决的痛点。国际化浪潮表明社区已准备好迎接全球开发者使用，但基础设施稳定性能否跟上需求有待观察。

</details>

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*