# OpenClaw 生态日报 2026-07-26

> Issues: 350 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-07-26 03:25 UTC

- [OpenClaw](https://github.com/openclaw/openclaw)
- [NanoBot](https://github.com/HKUDS/nanobot)
- [Hermes Agent](https://github.com/nousresearch/hermes-agent)
- [PicoClaw](https://github.com/sipeed/picoclaw)
- [NanoClaw](https://github.com/qwibitai/nanoclaw)
- [NullClaw](https://github.com/nullclaw/nullclaw)
- [IronClaw](https://github.com/nearai/ironclaw)
- [LobsterAI](https://github.com/netease-youdao/LobsterAI)
- [TinyClaw](https://github.com/TinyAGI/tinyagi)
- [Moltis](https://github.com/moltis-org/moltis)
- [CoPaw](https://github.com/agentscope-ai/CoPaw)
- [ZeptoClaw](https://github.com/qhkm/zeptoclaw)
- [ZeroClaw](https://github.com/zeroclaw-labs/zeroclaw)

---

## OpenClaw 项目深度报告

# OpenClaw 项目动态日报 (2026-07-26)

## 今日速览  
项目在过去 24 小时保持高度活跃：**350 条 Issue** 更新（251 条新开/活跃，99 条关闭），**500 条 PR** 更新（282 条待合并，218 条已合并/关闭）。未发布新版本。社区讨论集中在**安全、会话状态&内存管理**等方向，多个 P0/P1 级别的回归漏洞（如 `/new` 和 `/reset` 失效、Gateway 启动失败）引起关注，部分已有修复 PR 在推进。整体看，项目处于密集 bug 修复与功能扩展并行阶段，维护者介入积极。

## 版本发布  
今日无新版本发布。

## 项目进展  
今日合并/关闭的重要 PR 包括：  

- **#113986** `fix: refresh control UI startup baseline` – 调整 Control UI 启动基线，避免 lint 工具链更新后 CI 误报。  
  https://github.com/openclaw/openclaw/pull/113986  
- **#113989** `fix(ui): stabilize drag-managed group e2e` – 修复 macOS 端键盘菜单聚焦超时问题。  
  https://github.com/openclaw/openclaw/pull/113989  
- **#95359** `fix(skills): refuse owner-qualified ClawHub force install over a different owner` – 防止 `--force` 安装时覆盖已有同一技能的不同所有者版本。  
  https://github.com/openclaw/openclaw/pull/95359  
- **#113979** `refactor(agents): split acp-spawn helpers and drop max-lines suppression` – 拆解超大文件，消除遗留的代码行数压制。  
  https://github.com/openclaw/openclaw/pull/113979  

此外，多个与 **Session 性能、MCP 工具授权、Gateway 连接** 相关的修复 PR 仍在 review 或等待测试，项目整体向稳定版迈进。

## 社区热点  
讨论最活跃的 Issue 与 PR 如下（按评论数排序）：  

- **#7707** Memory Trust Tagging 功能请求（21 条评论）  
  https://github.com/openclaw/openclaw/issues/7707  
  *诉求：为 Agent 记忆条目按来源（用户命令、网页抓取、第三方技能）添加信任等级标签，防止记忆投毒攻击。*  

- **#78308** MCP 工具调用的频道审批机制（15 条评论）  
  https://github.com/openclaw/openclaw/issues/78308  
  *诉求：让 MCP 服务器可选择加入与 shell-exec 相同的 `/approve` 审批通道。*  

- **#113306** SQLite 快照恢复缺乏端到端崩溃保证（13 条评论，P1）  
  https://github.com/openclaw/openclaw/issues/113306  
  *用户报告快照创建/恢复可能在目录未持久化时报告成功，导致数据丢失风险。*  

- **#108435** Gateway 启动失败（11 条评论，P0）  
  https://github.com/openclaw/openclaw/issues/108435  
  *升级至 2026.7.1 后 Gateway 无法启动，涉及 systemd、Ollama、手动启动三种模式。*  

- **#67419** 会话上下文膨胀：bootstrap 文件每轮重复注入（10 条评论）  
  https://github.com/openclaw/openclaw/issues/67419  
  *每轮对话消耗 20-30% token 在静态引导文件上，引发 token 浪费和性能下降。*  

社区情绪：用户对**安全边界、会话稳定性、内存与 token 效率**的关注度最高，且多次提及回归问题的复现路径，表明对测试覆盖率和回归预防有更高期待。

## Bug 与稳定性  
以下为当日报告的严重 Bug（按严重程度排列）：

| 严重级别 | Issue # | 摘要 | 是否有 fix PR |
|----------|---------|------|---------------|
| **P0**   | #108435 | Gateway 启动失败（新版本回归） | 无直接 fix PR（讨论中） |
| **P0**   | #95515  | 升级 2026.6.8→2026.6.9 导致邮箱配置损坏（spurious groupAllowFrom 字段） | 无 fix PR |
| **P0**   | #109145 | Gateway HTTP 监听但不接受连接 | 无 fix PR |
| **P0**   | #48920  | 线上文档超前于发布版本（Live Docs vs Release） | 无 fix PR |
| **P1**   | #113466 | `/new` 和 `/reset` 无法创建新会话（2026.7.1-2） | 无 fix PR |
| **P1**   | #113306 | SQLite 快照恢复缺乏端到端保护 | 无 fix PR |
| **P1**   | #87109  | Gateway 堆内存持续增长至 1GB+，cron 任务静默失败 | 无 fix PR |
| **P1**   | #113315 | Telegram 入站更新永久丢失（offset 持久化后无分发） | 无 fix PR |
| **P1**   | #112423 | 大型 SQLite 转录清理阻塞事件循环 | 无 fix PR |
| **P1**   | #113341 | Codex 的 tool allowlist 阻止用户明确允许的 MCP 服务器 | PR #113341 已提出 |

当日共出现 **6 个 P0** 和 **10+ 个 P1** 活跃 bug，主要集中在 Gateway 可用性、会话管理、内存泄漏和配置兼容性上。其中 **#113341** 已有修复 PR 待审核。

## 功能请求与路线图信号  
当日社区提出的重要功能请求包括：  

- **#7707** Memory Trust Tagging（按来源信任标签） – 增强安全架构，但目前无对应 PR。  
- **#78308** MCP 工具调用的审批通道 – 与已有 shell-exec 审批流程对齐，PR #113341 部分涉及。  
- **#67419** 会话上下文压缩 / bootstrap 去重 – 已有 PR #113548（每日花费告警）可能间接缓解，但未直接解决。  
- **#7722** 文件系统沙箱配置 – 呼声高（👍4），暂无 PR。  
- **#15032** 子代理的每次生成工具限制 – 对应安全需求，无 PR。  
- **#9986** 上下文长度超限时模型回退 – 已有 fallback 配置但未支持此触发条件。  
- **#10944** Telegram 可配置解析模式 – 无 PR。  
- **#12219** Skill 权限声明标准（skill.yaml） – 无 PR。  

路线图信号：安全与权限管理（记忆标签、文件沙箱、技能权限）是未来重点方向，但多数仍停留在需求收集阶段，预计不会在近期版本密集落地。

## 用户反馈摘要  
从 Issues 评论中提炼的真实用户痛点（非官方摘要）：  

1. **“升级后 Gateway 无法启动”** – 多位用户反映 v2026.7.1 版本存在严重回归，不得不回退到 v2026.5.27 才能工作（#89445）。  
2. **“内存管理混乱”** – 同一组织内不同实例的记忆存储方式不一致（#43747）。  
3. **“子代理列表始终为空”** – 即使成功 spawn 也无法通过命令查看（#75593，已关闭但仍有类似投诉）。  
4. **“文档超前于代码”** – 文档中提到 `IsolatedSessions`、`toolProgress` 等配置在最新版本中不被支持（#48920，#103162）。  
5. **“Telegram 引用回复功能频繁失效”** – 需要本地运行时补丁才能工作，且在下个版本又回归（#88032）。  
6. **“自动更新留下旧模块导入”** – 热更新后网关仍引用已删除的旧文件（#85844）。  
7. **“OpenAI 提示缓存几乎失效”** – 每轮注入动态内容破坏了前缀缓存（#95610，#95840）。  

用户整体满意度中等，认可项目迭代速度，但对**升级兼容性、文档同步、核心功能稳定性**有较多批评。

## 待处理积压  
以下为长期未响应或可能被忽视的重要 Issue/PR，建议维护者优先关注：

- **#54634** (P1) 2026.3.24 更新后 `HOME` 变更导致配置静默丢失 – 已 stale 两个月，无 fix PR。  
  https://github.com/openclaw/openclaw/issues/54634  
- **#10687** (P2) 完全动态模型发现（OpenRouter） – 已 stale 5 个月，社区需求大（👍3）。  
  https://github.com/openclaw/openclaw/issues/10687  
- **#77249** (P1) Slack socket-mode 重连挂起在僵尸 WSS – 从未收到事件/日志，需要手动重启。  
  https://github.com/openclaw/openclaw/issues/77249  
- **#94536** (P2) 承诺交付仍失败（PR #92231 修复不完整） – 关闭后仍有第二案例。  
  https://github.com/openclaw/openclaw/issues/94536  
- **#104018** (XL PR) 添加就绪条件与提供者 – 自 7 月 11 日提交后无更新，影响集群部署。  
  https://github.com/openclaw/openclaw/pull/104018  

请维护者根据严重性和社区热度安排后续处理。

---

## 横向生态对比

好的，作为专注于 AI 智能体与个人 AI 助手开源生态的资深技术分析师，我为您呈上基于今日各项目社区动态的横向对比分析报告。

---

### 个人 AI 智能体开源生态横向对比分析报告 (2026-07-26)

#### 1. 生态全景

当前个人 AI 智能体开源生态正处于 **“核心功能深化”与“安全合规前置”** 并行的关键阶段。头部项目（如 OpenClaw）在快速迭代的同时，正面临由功能膨胀带来的严重回归问题和稳定性挑战，社区对**会话状态管理、内存效率和升级兼容性**的呼声极高。与此同时，以 NanoBot 和 CoPaw 为代表的第二梯队项目，通过版本里程碑（如 v0.3.0）和精细化功能（如 Reranker 内存搜索）实现了差异化突破。整个生态的焦点从“能用”正快速转向 **“好用、安全、可审计”**，围绕记忆投毒防护、工具调用审批、认证机制等安全议题的讨论显著升温。

#### 2. 各项目活跃度对比

| 项目名称 | 今日活跃 Issue 数 | 今日活跃 PR 数 | 版本发布 | 健康度评估 |
| :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 251 (新开) | 282 (待合并) | 无 | **中等** - 修复密集，但 P0/P1 Bug 积压严重，稳定性承压 |
| **NanoBot** | 0 | 3 (待合并) | **v0.3.0** | **优秀** - 版本里程碑发布，开发与合并效率高 |
| **Hermes Agent** | 活跃 | 活跃 (近100项总处理) | 无 | **良好** - 高 Bug 密度但有快速响应修复 PR，桌面端可用性是核心痛点 |
| **PicoClaw** | 2 | 1 (待合并) | 无 | **良好** - Bug 修复响应快，但 Matrix 稳定性问题久拖未决 |
| **NanoClaw** | 2 | 10 (待合并) | 无 | **良好** - Bug 修复及时（即报即修），但 PR 合并积压压力大 |
| **IronClaw** | 7 | 10+ (待合并) | 无 | **良好** - 核心架构与 WebUI 优化显著，但集成配置体验存在摩擦 |
| **LobsterAI** | 1 | 0 | 无 | **优秀** - 集中清理历史积压 PR，产品体验精细化阶段 |
| **Moltis** | 0 | 4 (待合并) | 无 | **良好** - 功能开发密集，社区贡献活跃 |
| **CoPaw** | 7 | 5 (待合并) | 无 | **良好** - Reranker 功能合并，但 MCP 驱动 Bug 需优先解决 |
| **ZeroClaw** | 16 | 48 (待合并) | 无 | **关注** - 大型特性丰富但陷于停滞，同时面临多个安全与稳定性风险 |
| **NullClaw / TinyClaw / ZeptoClaw** | 0 | 0 | 无 | **静默** - 无活动，可能处于维护或休眠状态 |

#### 3. OpenClaw 在生态中的定位

OpenClaw 作为生态中的 **“核心参照”** 和 **“能力边界”**，其定位清晰：

- **优势**：社区规模与活跃度绝对领先，Issue/PR 数量级远超其他项目，反映了最广泛的使用基础和贡献者网络。其功能覆盖最为全面，新功能（如技能市场、MCP 审批、会话优化）往往成为其他项目的参考标杆。
- **技术路线差异**：与 NanoBot（轻量、一键部署）或 ZeroClaw（Rust 实现、安全严谨）不同，OpenClaw 采用**通用架构**，追求最大的灵活性和扩展性。这也导致了其架构复杂性高，维护难度大，是当前回归 Bug 频发的根本原因。
- **社区规模对比**：每日 350+ Issue 和 500+ PR 的更新量，在单日内超过其他所有活跃项目更新量的总和。这既是其生态主导地位的体现，也反映了其面对的多元需求和沟通噪音是其他项目无法比拟的。

#### 4. 共同关注的技术方向

- **会话状态与内存管理**：
    - **相关项目**：OpenClaw, Hermes Agent, NanoClaw
    - **具体诉求**：OpenClaw 遇到会话上下文膨胀（bootstrap 重复注入）和 SQLite 快照恢复可靠性问题；Hermes Agent 讨论回合级时间感知以增强上下文；NanoClaw 的 Agent 上下文丢失是核心级 Bug。表明「如何高效、准确、持久地管理 Agent 记忆」是生态内最一致的痛点。
- **安全与权限精细化**：
    - **相关项目**：OpenClaw, Hermes Agent, ZeroClaw, CoPaw
    - **具体诉求**：OpenClaw 提出 Memory Trust Tagging（记忆来源信任标签）和 MCP 工具审批通道；Hermes Agent 强化技能写入的“失败关闭”策略；ZeroClaw 报告了 WhatsApp 配置空值导致的安全绕过Bug；CoPaw 报告 MCP 驱动硬编码绕过传输配置。安全已成为各项目跨越不同成熟度阶段的共同关注点。
- **升级兼容性与稳定性**：
    - **相关项目**：OpenClaw, Hermes Agent, ZeroClaw
    - **具体诉求**：多个 P0/P1 Bug 均指向升级后功能失效（OpenClaw Gateway 启动失败、Hermes 桌面端启动循环），社区对“升级即破坏”的容忍度显著降低，这要求项目加强 CI 测试覆盖率和回归预防。

#### 5. 差异化定位分析

- **功能侧重**：
    - **OpenClaw**: 全功能平台，覆盖聊天、技能、渠道、网关等，追求“大而全”。
    - **NanoBot**: **轻量级快速上手**，`nanobot webui` 一键启动，目标是小团队和个人用户。
    - **Hermes Agent**: **高可定制与扩展**，强调第三方供应商适配和复杂情景支持。
    - **LobsterAI**: **企业级协作助手**，侧重 Cowork 模块、任务计划、国际化，瞄准团队场景。
    - **Moltis**: **开放协议与集成**，专注与 Nostr、Slack 等外部平台的深度集成。
    - **CoPaw**: **高级内存检索**，当前特性集中在 Reranker 和混合搜索上，服务于知识密集型应用。
- **目标用户**：
    - **OpenClaw / Hermes Agent**: 开发者、高级用户，需要深度定制和管理。
    - **NanoBot / PicoClaw**: 普通用户、学生、AI 爱好者，追求开箱即用。
    - **LobsterAI**: 小团队、企业用户，关注多人协作与生产效率。
    - **ZeroClaw**: 对安全性和性能有极致要求的开发者（Rust 语言）。
- **技术架构**：
    - **ZeroClaw**: 基于 Rust 语言，强调内存安全和并发性能。
    - **Moltis**: 基于 ACP（Agent Communication Protocol）协议，构建可互操作的 Agent 网络。
    - **NanoClaw**: 强调容器化 Agent 隔离和沙箱安全。

#### 6. 社区热度与成熟度

- **快速迭代与功能扩张期**：**ZeroClaw** (虽有停滞风险但计划宏大)、**CoPaw** (新功能合并迅速)。这些项目敢于在新特性上投入资源，社区期待其能快速突破。
- **质量巩固与稳定期**：**OpenClaw** (修复 Bug 为主)、**Hermes Agent** (高强度修复Bug)、**NanoBot** (版本发布，清理兼容性)。这些项目经历过快速扩张，现在正“还技术债”，核心目标是提升可靠性。
- **产品体验精细化期**：**LobsterAI** (集中合并历史 UX 建议)、**IronClaw** (优化 WebUI 性能和架构)。功能已相对完备，开始聚焦于打磨易用性和感知性能。
- **半活跃或早期阶段**：**PicoClaw, Moltis** (功能开发活跃但社区讨论规模小)、**NullClaw** 等 (静默)。

#### 7. 值得关注的趋势信号

1.  **“安全左移”与“可审计性”成为刚需**：从 OpenClaw 的 Memory Trust Tagging 到 Hermes Agent 的技能签名验证，再到 CoPaw 的 MCP 传输协议问题，社区不再满足于功能实现，而是主动要求将安全、来源追溯和信任控制嵌入到 AI Agent 的设计中。对于开发者这意味着，在构建新 Agent 或集成现有系统时，**必须将代理（Proxy）、审批（Approval）和审计（Audit）作为一等功能（first-class features）来设计，而非事后补充**。

2.  **“内存架构”成为区分智能体能力的关键分水岭**：OpenClaw 的上下文膨胀、Hermes 的时间感知、CoPaw 的 Reranker 搜索，都指向了“如何更智能、更经济地管理 Agent 的长期记忆”。**单纯依赖 LLM 的上下文窗口已触达效率天花板**，外部向量数据库 + 精细化的重排序（Reranker） + 信任标签将成为下一代 Agent 记忆系统的标准范式。开发者应关注如何向 Agent 注入高质量、高相关度的动态上下文。

3.  **升级与兼容性管理进入“硬约束”时代**：NanoBot 明确声明 v0.3.0 为“最后一个兼容性窗口”，OpenClaw 和 Hermes 频繁因升级导致服务中断。这标志着生态正从“野蛮生长”进入“制度化”阶段。对于用户而言，**锁定版本和建立严格的升级测试环境**不再是可选，而是稳定使用 AI 智能体服务的必要前提。对于项目维护者，**自动化回归测试和清晰的破坏性变更声明**将是保持社区信任的基础。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据您提供的 GitHub 数据，我为您生成了 **2026 年 7 月 26 日** 的 NanoBot 项目动态日报。

---

### NanoBot 项目动态日报 | 2026-07-26

#### 1. 今日速览

今日项目活跃度极高，呈现出典型的版本发布日前后的高强度开发特征。核心事件是 **v0.3.0 版本正式发布**，标志着项目进入新的发展阶段。过去 24 小时内，社区开发热情高涨，共处理了 10 个 Pull Request，其中 7 个已被合并或关闭，合并效率高达 70%，显示出维护团队对主分支质量的强把控。尽管社区讨论热度（Issues 评论）相对有限，但版本发布和大量 PR 的合并表明项目正处在功能快速迭代和稳定性加固的关键时期。

#### 2. 版本发布

- **v0.3.0 正式发布** ([Release v0.3.0](https://github.com/HKUDS/nanobot/releases/tag/v0.3.0))
  - **更新内容**: 这是一个里程碑式的大版本更新，基于 260 个 PR 的合并和 38 位新贡献者的加入。核心主题是赋予智能体更多的“自主性”。
  - **关键特性**: 引入了一键启动 WebUI 的命令 `nanobot webui`，极大降低了新用户的上手门槛。该命令会自动准备本地 WebUI、启动网关并打开浏览器工作台。
  - **破坏性变更**: PR [#5083](https://github.com/HKUDS/nanobot/pull/5083) 明确指出，v0.3.0 是**最后的兼容性窗口**。旧版会话路径回退、懒迁移、`agents.defaults.maxMessages` 警告等遗留兼容性代码已被推迟到 v0.3.1 清理。这意味着 v0.3.0 之后的版本将不再支持这些旧的配置和行为。
  - **迁移注意事项**: 如果您是从 v0.2.x 系列升级，请仔细检查您的配置文件和自定义脚本，特别是涉及会话路径、消息限制等部分。建议在完成测试后，尽快基于 v0.3.0 的规范进行适配，以避免在 v0.3.1 发布后遇到兼容性问题。

#### 3. 项目进展

今日合并/关闭的 7 个 PR 涵盖了从文档、用户体验到关键 Bug 修复的多个方面，显示了项目在功能完善和稳定性上的全面进步。

- **文档与体验优化**:
  - [#5082](https://github.com/HKUDS/nanobot/pull/5082) 重构了 README，将 `nanobot webui` 作为浏览器优先的推荐路径，并对 Gateway 和 CLI 的不同使用场景进行了清晰说明，有助于降低新用户的迷惑。
  - [#5085](https://github.com/HKUDS/nanobot/pull/5085) 实现了一个贴心的功能：在桌面环境下首次安装后自动打开 WebUI，而 SSH/无头会话则保留设置向导。这显著优化了“开箱即用”的体验。

- **UI/UX 打磨**:
  - [#4696](https://github.com/HKUDS/nanobot/pull/4696) 实现了基于状态驱动的平滑视口运动，优化了 WebUI 流式输出的视觉体验，使内容滚动更自然、不卡顿。

- **Bug 修复与稳定性**:
  - [#4954](https://github.com/HKUDS/nanobot/pull/4954) 修复了 WebUI 中**子智能体（subagent）回复不可见**的问题，确保多智能体协作的结果能正确显示给用户。
  - [#1284](https://github.com/HKUDS/nanobot/pull/1284) 经过漫长讨论（自2月发起），今日终于合并。它引入了 CI/CD 管道、代码质量与覆盖率检查。这标志着项目工程化水平的重要提升，为后续代码质量和协作效率提供了保障。

#### 4. 社区热点

虽然今日没有评论数特别夸张的 Issue，但 PR 的密集度（10个）是社区活跃度的最直接体现。其中，围绕 **v0.3.0 版本发布**的一系列准备和收尾工作成为今日绝对热点。

- 热度最高的 PR 集群是 [#5081](https://github.com/HKUDS/nanobot/pull/5081) (版本发布准备) 和 [#5083](https://github.com/HKUDS/nanobot/pull/5083) (兼容性清理)，它们直接关系到新版本的生命周期管理。多位核心开发者（如 Re-bin, chengyongru, yu-xin-c）在此期间协同工作，显示出团队对于版本发布的重视。
- **潜在诉求**: 此次版本发布和兼容性窗口的关闭，传达了项目团队希望**加速迭代、甩掉历史包袱**的决心。社区贡献者应当关注这一信号，及时更新自己的代码和插件以适应新的 API 和标准。

#### 5. Bug 与稳定性

今日报告的 Bug 类 PR 主要集中在通信层面，严重程度为“高”，但均已存在修复方案。

- **严重程度: 高**
  - **[已修复]** [#4928](https://github.com/HKUDS/nanobot/pull/4928) **(Open)**: 修复统一会话（Unified Sessions）的心跳（heartbeat）路由问题。问题根源在于统一会话模式下，心跳可能未能路由到用户最后活跃的频道，导致用户可能收不到即时通知。
  - **[已修复]** [#4954](https://github.com/HKUDS/nanobot/pull/4954) **(Closed)**: 修复 WebUI 中子智能体输出丢失的问题。该 Bug 会影响使用了智能体编排功能的用户，导致部分对话结果不可见。
- **严重程度: 中**
  - **[待合并]** [#5084](https://github.com/HKUDS/nanobot/pull/5084) **(Open)**: 修复智能体在处理多用户消息时，丢失部分消息的运行时上下文（RequestContext）的问题。这可能导致智能体无法正确理解特定消息的意图。

#### 6. 功能请求与路线图信号

- **即将落实的功能**: 由 yu-xin-c 提交的 [#4625](https://github.com/HKUDS/nanobot/pull/4625) 提议为 `bwrap` 沙箱增加可配置的额外绑定根目录。这允许部署者将用户级工具目录（如 `~/.local/bin`）暴露给沙箱环境，同时保持默认限制。此 PR 处于 Open 状态，但已存在 25 天，表明其设计已相对成熟，很可能被纳入 v0.3.1 中。

#### 7. 用户反馈摘要

由于今日并无新开的活跃 Issue，主要反馈来自已关闭的 Issue #1131。该 Issue 虽然已于数月前关闭，但其内容与今日合并的 PR #1284 直接相关。
- **用户反馈**: 开发者 `fengxiaohu` 曾对项目的 CI 测试覆盖情况提出疑问，指出仓库虽有 `.github/workflows` 目录和 `tests/` 文件夹，但 CI 是否自动运行测试、具体检查哪些项目（单元测试、Lint）尚不明确。
- **项目回应**: 尽管回应迟来，但随着 PR #1284 的合并，这个问题得到了彻底解决。项目已经引入了自动化测试和代码质量检查流程。

#### 8. 待处理积压

- **[PR #4928](https://github.com/HKUDS/nanobot/pull/4928)**: 修复统一会话心跳路由。此 PR 自 7 月 14 日开启，标签为 `priority: p1`（最高优先级），且已存在修复方案，但仍然打开。这是一个影响即时通信体验的关键修复，建议维护团队加速其 Code Review 和合并流程。
- **[PR #4625](https://github.com/HKUDS/nanobot/pull/4625)**: 允许额外的 bwrap 绑定根目录。该 PR 自 7 月 1 日开启，时间较长，虽然功能设计明确，但迟迟未合并。如果其功能对当前路线图依然重要，建议安排评审。

---
**分析师总结**: 项目健康度 **优秀**。v0.3.0 的发布是项目成熟度的重要里程碑。开发团队展现出高效的合并能力和明确的版本管理策略。当前最优先的事项应是尽快合并并发布针对统一会话和运行时上下文的两个 `p1` 级别 Bug 修复，以巩固新版本的稳定性。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，以下是为您生成的 Hermes Agent 项目动态日报。

---

# Hermes Agent 项目动态日报 2026-07-26

## 1. 今日速览

今日 Hermes Agent 项目社区异常活跃，呈现出 **“高 Bug 修复密度 + 高社区反馈”** 的态势。当日共处理近 100 个 Issues 和 PR，其中包含多个严重级别为 **P0** 和 **P1** 的紧急 Bug 报告，且社区迅速提出了修复方案。项目核心贡献者针对桌面端启动循环、认证流程、数据库锁、技能权限等关键稳定性与安全性问题进行了密集的修复，显示出项目正在经历一轮重要的稳定性加固。尽管没有新版本发布，但代码库质量改进的节奏非常快。

## 2. 版本发布

- **无**。过去 24 小时内无新版本发布。

## 3. 项目进展

尽管没有版本发布，项目在核心稳定性和安全性方面取得了显著进展。最重要的进展包括：

- **修复桌面端连接远程网关的致命回退与启动循环**：针对长期存在的桌面端无法连接到认证网关的问题（#48434, #71491, #71305），多个 PR 被提出并关闭。其中 **PR #71714** 通过引导桌面端在健康检查被 401 拒绝时进行 OAuth 登录流程，从根本上解决了启动循环问题。这是解决社区反馈最强烈的桌面端可用性问题的关键一步。
- **强化技能和权限系统安全性**：**PR #71702** 确保在无法验证技能所有者身份时，写入操作会“失败关闭”，防止潜在的数据损坏或恶意写入。同时，**PR #71723** 禁止安装未签名的技能索引中的危险技能作为内建技能，提升了内建技能的安全性。
- **核心状态管理修复**：**PR #71724** 解决了 `hermes sessions optimize` 命令可能因自身代码导致的 SQLite 数据库锁冲突和损坏问题，这对于保障长期运行的网关和 CLI 会话的数据完整性至关重要。
- **供应商适配器优化**：社区已针对 Anthropic 和 Gemini 等关键供应商的适配器中的 token 统计错误（#71242）和并行流式处理冲突（#54355）提出了修复，确保成本统计的准确性。

## 4. 社区热点

今日社区讨论焦点主要集中在**桌面端的可用性问题**和**核心功能（如时间感知）的缺失**上。

1.  **【热点 Issue #10421】回合级实时时间上下文**：这是一个持续获得大量关注（13条评论，9个 👍）的功能请求。用户希望 Agent 在每个对话回合都能“知道”当前的准确时间、日期和星期，而不是依赖不定期的工具调用。这反映了社区对 Agent 情境感知能力（Situation Awareness）的深层次需求。链接：https://github.com/NousResearch/hermes-agent/issues/10421
2.  **【热点 Bug 集群】桌面端启动与连接失败**：多个 Issue（#71226, #48434, #71305, #71491）共同描述了 Windows 桌面端在更新后无法启动或连接到远程网关的问题。其典型表现是陷入“网关连接失败”和“401 认证错误”的循环中。这是今日社区反馈最集中的问题，也驱动了核心修复 PR #71714 的诞生。相关链接：#71226 (https://github.com/NousResearch/hermes-agent/issues/71226)

## 5. Bug 与稳定性

今日报告的 Bug 数量多且严重等级高，主要集中在桌面端和复杂供应商适配器上。好消息是，大部分高优先级 Bug 已有对应的修复 PR。

| 严重程度 | 问题描述 | Issue 链接 | 是否有 Fix PR |
| :--- | :--- | :--- | :--- |
| **P0** | Nous Portal 对 Anthropic 模型不应用供应商粘性路由，导致缓存命中率从 100% 降至 39%，成本增加约 2.3 倍。 | [#71576](https://github.com/NousResearch/hermes-agent/issues/71576) | 否 |
| **P1** | Windows 桌面端启动后陷入 WebSocket 连接中断的重置循环。 | [#71226](https://github.com/NousResearch/hermes-agent/issues/71226) | 否 (但 #71714 解决了类似问题) |
| **P2** | 桌面端配置文件中的 `${VAR}` 环境变量引用未在网关层解析（#71710），已通过 PR #71722 修复。 | [#71710](https://github.com/NousResearch/hermes-agent/issues/71710) | **是** ([#71722](https://github.com/NousResearch/hermes-agent/pull/71722)) |
| **P2** | 由于自身代码导致的 SQLite 锁冲突，可能导致 `state.db` 损坏。已通过 PR #71724 修复。 | (隐含于 #71724) | **是** ([#71724](https://github.com/NousResearch/hermes-agent/pull/71724)) |
| **P2** | Anthropic 适配器在统计成本时丢弃了缓存读取/创建 Token，导致 MoA 聚合器成本低估约 7 倍。 | [#71242](https://github.com/NousResearch/hermes-agent/issues/71242) | 否 (有讨论) |
| **P2** | ACP 对话模式可能在某些场景下挂起。 | [#39245](https://github.com/NousResearch/hermes-agent/issues/39245) | 否 |
| **P2** | CLI 模式下，流式输出文本会被后续的工具执行日志覆盖。 | [#40693](https://github.com/NousResearch/hermes-agent/issues/40693) | 否 |

## 6. 功能请求与路线图信号

- **高优先级功能请求：回合级时间上下文 (#10421)**：社区以高票数表达了对 Agent 具备“当前时间”感知的强烈需求。这很可能被纳入下一个版本的路线图。
- **潜在大功能：Claude Agent SDK 作为一等运行时 (#65982)**：一个大型 PR 提议将 Anthropic 官方的 Claude Agent SDK 作为 Hermes 的第一类后端集成。如果被合并，将显著扩展 Hermes 的能力边界，为用户提供更多选择。这是路线图上值得关注的信号。
- **UX 微调：** 社区呼吁提供选项来移除或配置 `hermes chat` 输出的缩进 (#41917)，以及恢复旧的 Ctrl+G 编辑器行为 (#56485)。这显示了用户对命令行工具体验的细致要求。

## 7. 用户反馈摘要

- **桌面端体验是最大痛点**：大量用户反馈在 Windows 上更新后，桌面应用无法启动或连接到远程网关 (如 #71226, #48434)。这是目前影响最广、最令用户沮丧的问题。
- **对“智能化”的期待**：用户希望 Agent 能“更聪明”，例如 Issue #10421 中提出的无需特殊工具就能感知当前时间。这表明社区不满足于 Agent 仅仅执行命令，而是希望其具备更自然、更类人的交互能力。
- **对成本敏感**：关于 Anthropic 缓存 Token 统计的 Bug (#71242) 被用户曝光，显示社区对 AI 使用成本非常敏感，希望项目能精确计量每一分钱。
- **对复杂供应商的支持**：用户在使用非官方或自定义的 API 供应商（如 NewAPI 转发 #45908）时遇到了流式处理和兼容性问题，表明用户的使用环境多样，对供应商适配器的健壮性有较高要求。

## 8. 待处理积压

- **长期 Issue #25016**：关于 LSP 子进程在长期运行的网关中未被回收，导致内存持续增长（约 200 MB/服务器）的问题。这是一个影响服务器长期运行稳定性和资源消耗的关键问题，但至今无修复。链接：https://github.com/NousResearch/hermes-agent/issues/25016
- **长期 Issue #45328**：关于辅助客户端缓存回收时，异步关闭操作未被 `await` 的警告问题。虽然不致命，但长期存在，表明代码健壮性有待提升。链接：https://github.com/NousResearch/hermes-agent/issues/45328
- **P0 性能问题 #71576**：Nous Portal 的粘性路由问题导致巨大的成本浪费，目前尚无修复 PR，亟需维护者关注。链接：https://github.com/NousResearch/hermes-agent/issues/71576

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

# PicoClaw 项目动态日报 | 2026-07-26

---

## 1. 今日速览

过去 24 小时项目活跃度中等偏低：共产生 2 条 Issue（均为新开/活跃）、4 条 PR（其中 3 条已合并/关闭，1 条待合并）。无新版本发布。社区讨论集中在 Matrix 同步稳定性和配置模型列表展示问题上；修复类 PR 已快速合入，但关键 Bug 修复后仍有待验证。整体项目健康度良好，Bug 修复响应及时，但部分历史 PR 等待合并时间较长。

---

## 2. 版本发布

无新版本发布。

---

## 3. 项目进展

今日合并/关闭了 3 个 PR，分别涉及稳定性修复、新功能集成与平台扩展：

- **[PR #3295] fix(channels): prevent SplitMessage hang on oversized fence headers**  
  已关闭（推测已合并）。修复了 `SplitMessage` 在处理过大的围栏代码信息字符串时导致的永久挂起问题，增加了降级逻辑和回归测试。  
  [链接](https://github.com/sipeed/picoclaw/pull/3295)

- **[PR #339] Added Email Tool, Calendar Integration and System Stats Overview Tool**  
  已关闭（创建于 2026-02-17，今日状态更新）。集成了 Google 日历、增强邮件轮询与内容获取，并新增 GitHub 工具和系统统计工具，属于较大的功能增强。  
  [链接](https://github.com/sipeed/picoclaw/pull/339)

- **[PR #3205] fix: support 9router gateway responses and add Linux ARMv7 build target**  
  已关闭。修复了在树莓派 3 B+ 上使用 9router 网关时的响应解析问题，并为启动器增加了 ARMv7 构建目标，拓展了硬件支持范围。  
  [链接](https://github.com/sipeed/picoclaw/pull/3205)

此外，仍有 1 个 PR 处于待合并状态：
- **[PR #3193] Added simplex channel type**（创建于 2026-06-27，更新于 2026-07-25）  
  [链接](https://github.com/sipeed/picoclaw/pull/3193)

总体来看，今日项目在消息分割稳定性、工具链集成和硬件兼容性上均有实质性推进。

---

## 4. 社区热点

- **[Issue #3203] [BUG] Matrix sync loop has no reconnection logic — silent death after network/server disruption**  
  评论数 6，赞数 2，是今日讨论最活跃的议题。用户反馈 Matrix 长轮询 `/sync` 在发生网络中断或 HomeServer 重启后永久死亡且无自动重连，且由于主进程保持存活，systemd 的 `Restart=on-failure` 不触发，导致服务静默失效。社区对此修复需求强烈。  
  [链接](https://github.com/sipeed/picoclaw/issues/3203)

- **[Issue #3294] /list models only shows the current model instead of all configured models**  
  新开 Issue，虽然暂无评论，但直接关系到用户日常使用体验（查看所有配置模型），可能引发后续讨论。  
  [链接](https://github.com/sipeed/picoclaw/issues/3294)

- **[PR #3295] fix(channels): prevent SplitMessage hang** —— 虽然今日才创建并关闭，但该修复直接针对消息分割长时挂起，对用户感知明显，也是社区关注的热点修复。

---

## 5. Bug 与稳定性

按严重程度排列：

| 严重程度 | Issue/PR | 描述 | 状态 |
|----------|----------|------|------|
| **严重** | [#3203](https://github.com/sipeed/picoclaw/issues/3203) | Matrix 同步无重连逻辑，网络或服务中断后静默死掉（无报错、无自动恢复） | Issue 开放，暂无关联 Fix PR |
| **中** | [#3295](https://github.com/sipeed/picoclaw/pull/3295) | `SplitMessage` 在超大 fence 信息字符串时永久挂起，导致消息发送卡住 | 已修复（今日 PR 已合并/关闭） |
| **低** | [#3294](https://github.com/sipeed/picoclaw/issues/3294) | `/list models` 命令仅显示当前模型而非所有配置模型，功能与命令说明不符 | Issue 开放，暂无修复 |

**特别提示**：`#3203` 为持续存在的严重 Bug（自 7 月 2 日创建），至今无修复 PR 关联，建议维护者优先处理。

---

## 6. 功能请求与路线图信号

- **新通道支持**：PR [#3193](https://github.com/sipeed/picoclaw/pull/3193)（待合并）添加了 `simplex` 通道类型，该项目已存在近一个月，可能被纳入下一个小版本。
- **工具链扩展**：PR [#339](https://github.com/sipeed/picoclaw/pull/339)（今日关闭）集成了邮件、日历、系统统计等工具，显示社区对增强 AI 助手实用工具的需求。
- **硬件兼容性**：PR [#3205](https://github.com/sipeed/picoclaw/pull/3205) 增加了 Linux ARMv7 构建目标，为树莓派等低功耗设备提供原生支持，符合边缘部署趋势。
- **模型列表展示**：Issue [#3294](https://github.com/sipeed/picoclaw/issues/3294) 要求 `/list models` 正确列出所有配置模型，属于 UI/UX 改进，实现难度较低，可能被快速采纳。

---

## 7. 用户反馈摘要

- **Matrix 通道稳定性**（来自 #3203 评论）：用户指出矩阵同步无重连导致服务“静默死亡”，且没有日志或告警。用户期待实现指数退避重连或心跳检测机制，以增强生产环境的可靠性。
- **模型配置可见性**（来自 #3294）：用户配置了多个模型，但 `/list models` 仅显示当前使用的一个，感到困惑。期望命令行为与描述一致，方便管理和切换。
- **PR #3295 修复认可**：虽然无用户评论，但该修复解决了消息分片时潜在的“假死”问题，对使用长消息或代码块的用户体验提升明显。

---

## 8. 待处理积压

- **[Issue #3203] Matrix sync loop no reconnection**（创建 2026-07-02，更新 2026-07-25）  
  严重 Bug 已存在近四周，至今无关联 Fix PR。建议维护者安排修复规划。  
  [链接](https://github.com/sipeed/picoclaw/issues/3203)

- **[PR #3193] Added simplex channel type**（创建 2026-06-27，更新 2026-07-25）  
  新功能 PR 已开放近一个月，尚未收到 maintainer 的合并或 review 反馈，可能因其他优先事项而搁置。  
  [链接](https://github.com/sipeed/picoclaw/pull/3193)

- **[PR #3205] 9router + ARMv7** 虽然今日已关闭，但该 PR 从 7 月 2 日创建到关闭历时 23 天，提示项目对较老的 PR 处理周期较长。建议设立更明确的 TTL 管理机制。

---

> **日报说明**：数据来源于 PicoClaw 项目 GitHub 仓库（[sipeed/picoclaw](https://github.com/sipeed/picoclaw)），采集时间为 2026-07-26。所有链接均指向对应 Issue/PR。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，这是根据您提供的 NanoClaw 项目数据生成的 2026-07-26 项目动态日报。

---

### NanoClaw 项目动态日报 | 2026-07-26

**日报分析师:** AI 智能体与个人 AI 助手开源项目分析师
**数据来源:** GitHub (github.com/qwibitai/nanoclaw)
**分析时段:** 2026-07-25 至 2026-07-26

---

### 1. 今日速览

项目今日处于高强度开发与问题修复的活跃期。过去24小时内，共有 **13** 项更新（2个Issue + 11个PR），其中 **10** 个 Pull Request 处于待合并状态，表明社区贡献积极，但维护团队面临较大的合并积压压力。值得关注的是，今日所有新开的Issue都有对应的修复PR，显示出项目对用户问题的响应速度极快，尤其是 `#3134` 和 `#3132` 两个核心功能Bug已得到精准修复。总体而言，项目健康度良好，社区参与度高，但需要加快PR审查与合并节奏，避免阻塞其他工作进展。

### 2. 项目进展

今日合并/关闭了一个重要的安全加固 PR，同时大量修复性 PR 已提交，项目整体稳定性和安全性正在稳步提升。

- **[merged/closed] 安全加固：容器安全加固 (PR #2748)** [`89d92f`]
  由 boazdori 提交的 `security: harden agent containers` 终于被合并。该 PR 为每个会话生成的 Agent 容器添加了默认的深度防御策略，包括 `--cap-drop=ALL`、`--security-opt no-new-privileges:true` 和 `--pids-limit 2048`。这一改动显著降低了因 Agent 容器被攻破或逃逸而导致的主机安全风险，是项目迈向生产级安全的重要一步。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/2748)

- **[open, 已提交 Fix PR] 核心上下文缺失问题修复 (PR #3135)**
  针对 Issue #3134，brianjcohen 提交了修复：`fix: mirror host-sent messages into the agent's context`。修复了主机代表 Agent 发送的消息（如审批卡片、拒绝提示等）未被写入 Agent 记忆上下文的关键缺陷，保证了 Agent 推理过程中信息的一致性。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/3135)

- **[open, 已提交 Fix PR] 轮询逻辑缺陷修复 (PR #3133)**
  针对 Issue #3132，buzali 提交了修复：`fix(container): gate the follow-up poll on trigger=1 too`。修复了 `poll-loop.ts` 中一个分支缺少 `trigger` 门控检查的Bug，该Bug会导致无效的 `trigger=0` 消息意外触发轮询，造成资源浪费和潜在异常。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/3133)

### 3. 社区热点

今日社区讨论热点集中于**Agent 上下文一致性与容器稳定性**问题。虽然目前相关 Issue 和 PR 的评论数较少，但这两个问题的严重性较高，反映了用户在真实使用场景中遇到的痛点。

- **热点 Issue #3134: 主机代表发送的消息在 Agent 上下文中丢失** [`未解决`]
  该问题直接点出一个核心逻辑缺陷：Agent 无法感知主机代表它发送的消息（如审批卡）。这强烈影响了用户对 Agent 控制能力的感知，因此作者 brianjcohen 在创建 Issue 后立即提交了修复 PR，形成了高效的“问题-修复”闭环。
  [查看Issue](https://github.com/qwibitai/nanoclaw/issues/3134)

- **热点 Issue #3132: `follow-up poll` 绕过累积门控** [`已修复`]
  buzali 报告了一个关于 `poll-loop.ts` 轮询机制的逻辑Bug，它可能导致消息被错误地推送至活跃查询中。这个问题的发现和修复过程展示了项目对内部复杂逻辑的严谨性。该 PR 已被正确标记。
  [查看Issue](https://github.com/qwibitai/nanoclaw/issues/3132)

- **[长期活跃] PR #2211: Tool Visibility 技能增强** [`长期未合并`]
  由 robbbyczgw-cla 提交的长期 PR 今日被更新并重新同步了上游代码。该 PR 旨在为开发者提供实时工具调用预览能力，对开发和调试体验提升巨大，已累计在 Fork 上运行三个月。虽然项目组未发表评论，但该 PR 的持续活跃和作者自述的“三个月的生产使用”表明其具备较高的成熟度和社区需求。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/2211)

### 4. Bug 与稳定性

过去24小时内报告了 **2** 个 Bug，均为核心功能缺陷，且均已得到修复性 PR 的响应。Bug 严重程度均为“高”。

- **严重 Bug #1：Agent 上下文丢失**
  - **概述:** `#3134`: 主机发出的消息不进入 Agent 的 `messages_in` 和历史记录，导致 Agent 无法感知自己的输出或与主机的互动。
  - **影响域:** 核心对话逻辑，影响 Agent 的自我认知和连续对话能力。
  - **状态:** 已由 **PR #3135** 修复。
  - [查看Issue](https://github.com/qwibitai/nanoclaw/issues/3134)

- **严重 Bug #2：轮询逻辑绕过门控**
  - **概述:** `#3132`: `poll-loop.ts` 中一条消息消费路径（`setInterval`）未检查 `trigger=1`，导致 `trigger=0` 的无效消息也可能触发轮询。
  - **影响域:** 系统资源消耗，可能引发不必要的 API 调用和状态更新。
  - **状态:** 已由 **PR #3133** 修复。
  - [查看Issue](https://github.com/qwibitai/nanoclaw/issues/3132)

### 5. 功能请求与路线图信号

今日未收到全新的功能请求。但从打开的 PR 来看，项目社区正在为产品添加一些有价值的增强，这可能是未来版本演进方向的信号：

- **安全加固已完成:** PR #2748 的合并标志着项目已默认启用容器安全策略。这是迈向企业级部署的关键基础设施，为后续的多租户、高合规性场景打下基础。
- **运维自动化增强:** PR #3131 (移除镜像)、PR #3129 (挂载安全) 等 PR 表明维护者团队正在系统地加固和优化 Agent 的运行时环境。
- **社区技能生态扩张:** PR #3128 (航班值机技能) 是社区提交的全新容器技能，说明项目生态正在逐步建立，社区开发者积极贡献实用场景。
- **开发者体验改进:** PR #2211 (Tool Visibility) 即使未被合并，但其高更新频率表明它是社区关注的重要特性，预计会在后续版本中优先被考虑。

### 6. 用户反馈摘要

由于今日暂无新增的 Issue 评论，因此无法从评论中提炼用户反馈。但从已报告的 Issue 本身可以推断：

- **用户在要求更精准的控制:** Issue #3134 的用户痛点在于，他们需要 Agent 完整知道主机代表其发布了什么信息，否则无法进行复杂的、需要多步协调的任务。
- **用户在检测到隐晦的性能问题:** Issue #3132 的用户通过代码审计发现了隐晦的逻辑缺陷，表明项目拥有具有深度技术背景的用户或贡献者，他们对系统健壮性有较高要求。

### 7. 待处理积压

以下 PR 长期未获得关注或合并，可能会影响贡献者的积极性，建议维护团队优先关注。

- **PR #2211: feat: add tool-visibility skill** [`创建于 2026-05-03`]
  该 PR 已积压近三个月，作者近期主动进行了代码同步。这是一个增强开发者体验（DX）的重大特性，它的长期搁置可能会让社区感觉项目对新功能的接纳速度较慢。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/2211)

- **PR #3122: fix(opencode): main compatibility, custom-endpoint transport, memory parity** [`创建于 2026-07-23`]
  来自 glifocat 的又一个修复 PR，虽然仅存在数日，但作者贡献了多项重要修复，包括对 opencode 的兼容性、自定义端点传输以及内存一致性。建议在审查 #3135 等新 PR 后，尽快评估并处理该 PR。
  [查看PR](https://github.com/qwibitai/nanoclaw/pull/3122)

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，以下是基于您提供的 IronClaw 项目数据生成的 2026-07-26 项目动态日报。

---

## IronClaw 项目动态日报 — 2026-07-26

### 1. 今日速览

IronClaw 项目在过去24小时内保持 **高活跃度**。核心团队及社区贡献者在 **WebUI 性能优化**、**Model Reborn 架构** 和 **错误恢复能力** 等关键领域均有显著进展。合并/关闭的 PR 数量（8条）与新开/活跃的 Issue 数量（7条）基本持平，显示出良好的问题处理节奏。然而，有超过10条待合并的 PR 和一系列关于集成（Slack/Telegram/GitHub）的用户体验阻塞问题亟待解决，这表明项目在快速推进核心架构的同时，也需要加强对边缘场景和外部集成的打磨。总体项目健康度 **良好**，但存在一定的 **技术债务和用户体验摩擦**。

### 2. 版本发布

**无**

过去24小时内没有新的版本发布。

### 3. 项目进展

过去24小时合并/关闭的 PR 主要聚焦于 **WebUI 体验修复** 和 **核心架构清理**，说明团队在快速迭代新功能后，正集中精力解决 UI/UX 的遗留问题并规范化后端架构。

- **WebUI 用户体验大幅提升**：
    - **[`#6632`]**:  合并了 **路由级代码拆分** 和 **Tree-Shaking优化**，将初始JS包大小从 **1,227 kB 降低至 377 kB（压缩后从 349 kB 降至 116 kB）**，显著提升了首屏加载速度。
    - **[`#6624`]**:  修复了扩展配置弹窗无法获取/恢复键盘焦点的问题，提升了无障碍体验。
    - **[`#6627`]**:  修复了取消运行失败后，聊天界面状态显示错误（重新变为空闲态）的问题。
    - **[`#6626`]**:  修复了自动化列表在不同过滤器间切换时，闪出全屏加载骨架屏的问题。

- **核心架构清理与规范化**：
    - **[`#6670`]**:  清理了11个过时的 Reborn 架构文档，将活跃指南整合到 `ProductSurface` 和 `ChannelAdapter` 上，减少了技术债务。
    - **[`#6669`]**:  将 `extension host` 的所有权从 `composition` 包中移出，改善了模块化设计。
    - **[`#6673`]**:  新增了针对生产代码中死代码的静态检查门禁，确保未来新代码的质量。

### 4. 社区热点

**最活跃 Issue：`#6284**` —— *[EPIC] error-recoverability endgame — the model recovers from 100% of the errors it sees*

- **链接**: [Issue #6284](https://github.com/nearai/ironclaw/issues/6284)
- **分析**: 作为一个史诗级任务，该 Issue 获得了 **6条评论**，是今日最受关注的话题。它仍处于 **开放** 状态，说明社区和开发者都在密切关注模型的错误恢复能力。这不仅是单纯修复bug，而是在构建一套完备的错误恢复协议。相关PR **[`#6677`]** 已经为此建立了强制性的可恢复性合规矩阵，表明这是项目当前阶段的 **核心攻坚目标**。

**最受赞同 Issue：`#6675**` —— *Centralize Shared Rust Dependencies with [workspace.dependencies]*

- **链接**: [Issue #6675](https://github.com/nearai/ironclaw/issues/6675)
- **分析**: 虽然只有0条评论，但获得了 **2个👍**，是今日最受社区“点赞”的 Issue。这表明社区贡献者（`catusax`）和用户关注项目的 **工程化最佳实践**。统一依赖管理能减少版本冲突、简化维护，代表了社区对项目长期健康度的关切。

### 5. Bug 与稳定性

今日报告的 Bug 主要集中在 **集成体验** 和 **用户引导** 方面，多为中低严重级别，但影响用户体验。

- **严重级别：中**
    - **[`#6671`]**: **Telegram 配置死胡同** —— 用户通过代理或扩展页面配置 Telegram 时，会因“需管理员配置”而卡住，只有通过特定路径（扩展→频道→滚动到底部）才能完成设置。**无 Fix PR**。
    - **[`#6667`]**: **GitHub PAT认证循环** —— 用户使用无效的 GitHub Token 认证时，系统不会报错，而是无限循环提示输入凭据。**无 Fix PR**。
    - **[`#6620`]**: **取消运行失败状态不一致** —— （已修复，通过 PR `#6627` 解决）取消请求失败后，后端可能继续运行，但前端显示为空闲状态。

- **严重级别：低**
    - **[`#6668`]**: **Slack连接引导缺失** —— 智能代理无法理解“连接 Slack”的指令，用户需要通过菜单层层查找才能找到配置入口。**无 Fix PR**。
    - **[`#6621`]**: **扩展配置弹窗焦点管理** —— （已修复，通过 PR `#6624` 解决）键盘用户无法在弹窗内进行 Tab 导航。
    - **[`#6622`]**: **自动化列表过滤闪白** —— （已修复，通过 PR `#6626` 解决）切换过滤器时出现不必要的全屏加载效果。

### 6. 功能请求与路线图信号

今日的 Issue 和 PR 显示了清晰的路线图信号，主要围绕以下几个方向：

- **错误恢复强制合约化**：`#6284` (EPIC) 及相关 PR `#6677` 表明，项目正在将“模型必须能从所有错误中恢复”这一目标编程化、规则化。这是一个 **深度架构级** 的演进。
- **WebUI 极致性能**：`#6628` (EPIC) 和已合并的 `#6632` 表明，在提供丰富功能的同时，项目正在将 UI 加载性能和渲染性能作为 **v1 发布的关键标准**。
- **核心模块职责明确化**：`#6669` (已合并) 和 `#6675` (Issue) 体现了项目在持续进行 **模块解耦** 和 **依赖关系清理**，这是项目走向成熟和稳定的必经之路。
- **签名与认证能力**：`#6672` (PR) 提出的“签名意图”和“每Agent密钥生命周期”是 **Ledger集成计划**的一部分，这表明项目正在为需要高安全性和审计的场景（如 Defi 或企业级应用）铺路。

### 7. 用户反馈摘要

从今日的 Issue 中，我们可以提炼出以下用户痛点：

- **配置路径不清晰**：用户尝试配置 Telegram (`#6671`) 和 Slack (`#6668`) 时，遇到了明显的引导缺失问题。他们期望智能代理或UI能提供更直观的指引，而不是让用户自己猜测或搜索。这严重影响了新用户的上手体验。
- **认证错误提示不友好**：在 GitHub 认证 (`#6667`) 失败时，系统没有给出任何具体错误（如“Token无效/已过期”），而是陷入无意义的重复提示。用户无法从当前状态中理解发生了什么，也无法知道如何纠正，这直接导致“死锁”式的糟糕体验。
- **自动化功能体验不佳**：用户在使用自动化列表时，切换过滤条件会触发不必要的全屏加载骨架 (`#6622`)，虽然已修复，但说明之前的设计没有考虑感知性能和状态保持。

### 8. 待处理积压

- **`#5598`**:  `chore: release` PR (size: M)。此 PR 自 **2026-07-03** 起已开放 **23天**，且由 `ironclaw-ci[bot]` 发起。这表明一次包含重大更改（`ironclaw_common` 和 `ironclaw_skills` 的 API 破坏）的版本发布被严重 **卡住**。这可能是由于发布流程问题、代码审查僵局或对破坏性变更的决策困难所致。持续未发布的版本会阻塞下游用户获取新功能。
- **`#6640`**: `build(deps)` 依赖更新 PR (size: XL)。此 PR 计划一次更新 **31个依赖**，已开放 **2天**。如此大规模的依赖更新合并风险较高，需要仔细审查，但长期搁置会增加安全风险和兼容性问题。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

好的，作为 LobsterAI 开源项目的分析师，根据您提供的 GitHub 数据，我已为您整理好 2026-07-26 的项目动态日报。

---

# LobsterAI 项目动态日报 | 2026-07-26

## 今日速览

项目在今日呈现出极高的活跃度，主要特征为**集中性的“清淤”行动**，大量历史遗留的 Issues 和 PR 被批量清理和合并。虽然未发布新版本，但社区积累的 UX 优化建议（如消息时间戳、会话分组、方向键回溯等）已被全部合并，标志着产品体验进入精细化打磨阶段。同时，新的用户反馈（如文件夹附件支持）开始涌现，成为下阶段关注的重点。整体项目健康度非常健康，迭代节奏迅速。

## 版本发布

无

## 项目进展

今日项目进展主要体现为对积压了 3 个月的旧 Issues 和功能请求的集中响应。共 **11 个 PR 被成功合并或关闭**，大幅降低了项目债务。核心进展包括：

- **功能增强合并兑现**：此前由社区成员 `MaoQianTu` 提交的 8 个 UX 增强建议，其对应的 8 个 PR 在此次全部被合并/关闭。这表明 LobsterAI 团队从上一季度开始规划的用户体验大版本更新已全部落地。
    - **伙伴（Cowork）模块增强**：实现了工具调用块批量展开/折叠 (#1327)、会话错误状态红点提示 (#1331)、会话列表时间分组 (#1338)、消息时间戳 (#1340)、输入框方向键历史回溯 (#1342) 和导出 Markdown (#1345)。
    - **任务计划与 MCP 增强**：新增了定时任务的“工作日”选项 (#1335)，以及 MCP 服务器配置的 JSON 粘贴导入功能 (#1336)。
    - **国际化修复**：修复了附件标签、Escape 键关闭、删除确认等多语言问题 (#1333)。
- **稳定性与兼容性提升**：
    - **Windows 平台**：修复了 Windows 安装程序的根目录防护问题 (#2383) 并强化了安装与更新恢复机制 (#2384)。
    - **新模型支持**：增加了对 Kimi K3 模型的支持 (#2381)，进一步扩大了模型生态兼容性。

这些 PR 的集中合并，使得该项目在用户体验和基础稳定性上迈出了坚实的一步，产品完成度显著提高。

## 社区热点

- **唯一活跃 Issue #2385：对话框无法添加文件夹** [链接](https://github.com/netease-youdao/LobsterAI/issues/2385)
  - 这是过去24小时中唯一新开的且处于活跃状态的 Issue。
  - **诉求分析**：用户 `gouff98` 提出了一个关键的交互限制，即无法像 Cline、Cursor 等同类产品一样，在对话窗口中通过 `@` 符号引用一个文件夹。这反映了用户期望复现代理调试领域的最佳实践，即能够将整个项目目录作为上下文提供给 AI Agent，从而实现更精准的代码理解和修改。

## Bug 与稳定性

今日无新增的严重 Bug 报告。主要的稳定性提升来自于基础设施的改进：

- **Windows 平台修复 (严重程度: 高)**：通过 PR [#2383](https://github.com/netease-youdao/LobsterAI/pull/2383) 和 [#2384](https://github.com/netease-youdao/LobsterAI/pull/2384) 修复了 Windows 安装程序可能存在的“根目录外来内容保护”问题，并增强了安装和更新恢复的健壮性。这对于 Windows 用户，尤其是使用企业版或安装了安全软件的设备，是重要的稳定性保障。
- **遗留 Bug 批量关闭**：此前报告的多个功能性 Bug（如 #1329 定时任务通知渠道缺失）在今天被批量关闭，表明这些问题已被修复或在后续版本中解决。

## 功能请求与路线图信号

近期用户功能请求主要集中在**提升用户体验**和**补齐功能差距**上，这些信号很可能指引着下一个版本的开发方向。

- **路径图已兑现**：此前由 `MaoQianTu` 提出的一系列“功能缺失”请求（#1337 列表分组、#1339 时间戳、#1341 历史回溯、#1343 全文搜索、#1345 导出等）在今天全部交付，这表明项目路线图完全采纳了这些高频社区反馈，并纳入了核心体验优化中。
- **下阶段强信号点**：
    - **文件交互能力升级**：新 Issue [#2385](https://github.com/netease-youdao/LobsterAI/issues/2385) 要求的“@文件夹” 功能，是当前与主流 Agent 产品功能对齐的关键短板。这很可能成为下一个版本的重点特性。
    - **搜索能力增强**：虽然还未合并，但此前 Issue #1343 提出的“全文搜索”需求（当前已关闭）说明用户对信息和上下文检索的要求越来越高。结合 #2385 的文件交互，一个强大的全文搜索和文件系统集成是未来的核心痛点。

## 用户反馈摘要

- **积极反馈（隐含）**：从批量关闭的 Issues 和 PR 可以看出，用户对社区参与度很高，并且提出的功能请求（如批量展开/折叠、时间戳、分组）都被团队采纳并实现。虽然没有直接的“满意”评论，这种高效的“Issue -> PR -> Merge”的闭环本身就是对用户体验和项目管理的最强肯定。
- **痛点反馈**：
    - **工作流效率**：用户 `MaoQianTu` 在其多个 Issue 中表达的核心诉求是“效率低下”和“操作繁琐”，例如逐一点击工具块、手动输入历史指令、无时间戳回溯等。这说明专业用户对 Cowork 工作流中的操作流畅度有很高要求。
    - **功能完整性**：用户 `gouff98` 的反馈 (#2385) 指出了与竞品在核心 Agent 交互能力上的差距。用户希望 LobsterAI 能支持 `@folder` 这种更高级的上下文管理方式，而不仅仅是单个文件。

## 待处理积压

- **唯一未解决的问题 #2385**：[对话框添加文件只能添加文件，不能添加文件夹](https://github.com/netease-youdao/LobsterAI/issues/2385)
  - **状态**：OPEN
  - **分析**：这是目前唯一悬而未决的 Issue。虽然今日没有其他 PR 或维护者回复，但考虑到它触及其余所有同类产品的核心交互模式，很有希望被快速提上日程。建议维护者优先评估其技术实现复杂度，并给出初步响应。

---
*声明：本日报由 AI 根据 GitHub 仓库数据自动生成，仅供参考。*

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是为您生成的 Moltis 项目 2026-07-26 动态日报。

---

### Moltis 项目日报 2026-07-26

#### 1. 今日速览

项目今日无新 Issue 产生，但 Pull Request 活动活跃（6 条），开发重心明显转向集成与扩展。今日合并了 2 项 PR，包括一项关键的 Slack 交互体验优化（消息确认反应）和一个文档规范，同时有 4 个重要功能 PR 处于待合并状态，覆盖 Nostr 协议、ACP 服务端角色、Slack 高级交互及新向量数据库内存后端。整体来看，项目处于**功能密集开发期**，活跃度中高，社区贡献与核心开发同步推进。

#### 2. 版本发布

无。

#### 3. 项目进展

今日合并/关闭的 2 项 PR 推进了项目在**用户体验规范**和**即时消息反馈**方面的基础能力：
- **[#1165 (已合并) feat(slack): acknowledge messages with reactions and add reaction triggers](https://github.com/moltis-org/moltis/pull/1165)**：修复了线程回复中的错误消息 Bug，并为 Slack 渠道增加了消息确认反应和入站反应触发器。这解决了 Slack 机器人无法显示“正在输入”状态时，用户无法感知消息已被接收和处理的问题，显著提升了基础可靠性。
- **[#1167 (已关闭) docs: forbid Claude session URLs in commits and PRs](https://github.com/moltis-org/moltis/pull/1167)**：这是一项文档/工作流规范变更，明确禁止在提交和 PR 描述中包含 AI 助手会话链接。此举旨在确保 Git 提交历史的纯净性和可审计性，体现了项目对代码来源和协作规范的高度重视。

项目基础设施正在变得更加健壮，并且核心团队在持续通过小步快跑的方式优化用户即时反馈体验。

#### 4. 社区热点

今日虽然无公开评论数据，但从 PR 内容来看，最受关注和讨论潜力最大的当属以下几项，它们触及了项目发展的核心方向：

- **[PR #1168 (开放) feat(nostr): add NIP-29 group chat support for Buzz channels](https://github.com/moltis-org/moltis/pull/1168)**
  - 作者: `penso`，该项目核心维护者，持续推动于外部平台集成。
  - **背后诉求**：将 Moltis 从仅支持 Nostr 基础协议（NIP-01）升级为支持群聊（NIP-29），直接打通与 Block 公司开源工作空间 [Buzz](https://github.com/block/buzz) 的集成。这表明项目正致力于将 AI Agent 无缝嵌入人类协作的聊天场景中，而非仅作为独立工具。

- **[PR #1166 (开放) feat(slack): per-message acknowledgment reactions, phases, reconnect supervision, and Block Kit](https://github.com/moltis-org/moltis/pull/1166)**
  - 作者: `penso`
  - **背后诉求**：基于已合并的 #1165 进一步深化 Slack 集成。社区对 Slack 机器人有着极高的“可靠性”和“反馈及时性”期望。此 PR 引入消息分阶段确认（排队、处理、完成）、连接重连监督和富文本渲染（Block Kit），旨在满足专业用户对精细化和稳定交互的高要求。

#### 5. Bug 与稳定性

今日未报告新的 Bug。但通过已合并的 PR 可以看出，项目在持续修复并预防潜在问题：
- **(已修复) 线程回复错误消息 Bug** (PR #1165)：修复了 Slack 渠道中线程回复可能指向错误消息的严重性问题。这属于并发或状态管理问题，直接影响交互正确性，现已随 #1165 合入主分支。

#### 6. 功能请求与路线图信号

今日虽无新功能请求 Issue，但新提交的 PR 本身就是最强的路线图信号：
- **ACP 协议角色扩展 (PR #1169)**：[feat(acp): expose Moltis as an ACP agent over stdio](https://github.com/moltis-org/moltis/pull/1169)概述：Moltis 此前仅为 ACP（Agent Communication Protocol）客户端，该 PR 将其转变为服务端，使其能被 Zed、Buzz-ACP 等外部工具调用为其 agent。这标志着 Moltis 从“使用其他 agent”到“成为 agent”的架构转变，极有可能成为下一版本的核心功能之一。
- **Nostr 群聊集成 (PR #1168)**：如社区热点分析，此 PR 将直接决定 Moltis 能否顺利接入 Buzz 平台。考虑到 Buzz 的背景和潜力，此功能大概率会快速被审查并合并。
- **向量数据库内存后端 (PR #1158)**：[feat(memory): add zvec vector database memory backend](https://github.com/moltis-org/moltis/pull/1158) 这是一项社区贡献（`demyanrogozhin`），使用 Zvec 和 Redb 作为内存后端的实验性实现。这表明社区对更轻量、更灵活的记忆存储方案有兴趣，可能成为未来下游路线图的一部分或作为可选特性。

#### 7. 用户反馈摘要

今日无用户评论。但通过 PR 摘要可以推断出一些用户痛点：
- **Slack 交互模糊**：用户无法从 Slack 机器人得到即时处理反馈（无打字指示器），导致不确定消息是否正在被处理。
- **可靠性需求**：在消息排队、故障取消、网络断连等真实条件下，用户需要清晰、准确的信号来判断消息状态。

项目团队正在积极回应这些痛点，通过 #1165 和 #1166 提供更完备的交互反馈和稳定性保障。

#### 8. 待处理积压

对于长期未合并的关键 PR，请维护者关注：
1. **[PR #1158 (开放) feat(memory): add zvec vector database memory backend](https://github.com/moltis-org/moltis/pull/1158)**
   - 创建于 2026-07-17，已开放 9 天。作为一项由社区成员（`demyanrogozhin`）贡献的完整功能，涉及核心的记忆系统。建议维护者尽快审查，给出反馈或决定是否合并，以避免挫伤社区贡献者积极性。

2. **[PR #1166 (开放)](https://github.com/moltis-org/moltis/pull/1166) 以及 [PR #1168 (开放)](https://github.com/moltis-org/moltis/pull/1168)**
   - 均为重量级功能，虽开放时间不长，但覆盖面广，建议评估它们与现有主干 (master) 的兼容性及与其他待合并的 PR 的冲突情况，规划合并顺序。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

# CoPaw 项目动态日报（2026-07-26）

## 1. 今日速览

过去 24 小时内 CoPaw 项目活跃度较高：共处理 7 个新 Issue（均为待响应状态）和 7 个 Pull Request（其中 2 个已合并关闭，5 个仍在审核）。无新版本发布。社区反馈集中在 **MCP 驱动传输协议硬编码 Bug** 和 **Edge+Wayland 下高 CPU 占用** 等稳定性问题，同时有 2 个关于内存搜索重排器的 PR 成功合并，表明 reranker 功能正稳步推进。整体项目健康状况良好，但关键 Bug 的修复进展需要加速。

## 2. 版本发布

本周无新版本发布。

## 3. 项目进展

今日共有 **2 个 PR 被合并/关闭**，均为已合并状态：

- **[PR #5691] feat(console): add reranker config UI for reme0.4 memory search** (已合并)  
  为 reme0.4 内存搜索添加了重排器（Reranker）视觉配置界面，支持用户从 Web UI 设置模型名称、Base URL、API Key、温度等参数，并完整支持中英文国际化（16 个 key）。  
  [链接](https://github.com/agentscope-ai/QwenPaw/pull/5691)

- **[PR #5692] feat(memory): add reranker for search results on reme0.4** (已合并)  
  在 reme0.4 的混合检索（BM25+向量）流程后增加了重排阶段，允许调用外部 Reranker API 对 top-K 结果重新排序，显著提升检索质量。  
  [链接](https://github.com/agentscope-ai/QwenPaw/pull/5692)

这两个 PR 共同完善了 **ReMeLightMemoryCard** 组件的重排器支持，标志着内存检索功能向生产级迈出了重要一步。

此外，还有 **5 个待合并 PR** 正在审核中（见第 8 节积压部分）。

## 4. 社区热点

今日讨论最活跃的 Issue 集中在 **MCP 驱动传输协议硬编码缺陷**（#6470、#6469、#6468），由同一用户 `JohnyLe` 反复提交，虽然内容几乎一致（均指控 `mcp_stateful_client.py` 硬编码 `sse_client` 忽略 `streamable_http` 配置），但反映出该问题严重影响了多名用户的 MCP 服务器部署。每条 Issue 都有 1 条评论，无人点赞，说明可能尚未引起广泛关注，但问题本身具有强破坏性。

- **#6470** [Bug]: MCP driver ignoring transport config — hardcoded SSE client breaks streamable_http servers  
  [链接](https://github.com/agentscope-ai/QwenPaw/issues/6470)

另一个高活跃 Issue 是 **#6460**（QwenPaw 首页在 Edge+Wayland 下单标签高 CPU 占用），有 2 条评论，用户 `dayofyear` 详细描述了触发条件（大结果集渲染/WebSocket 推送），属于性能瓶颈类问题。

- **#6460** [OPEN] QwenPaw 2.0.1 首页/会话在 Edge+Wayland 下单标签高 CPU 占用  
  [链接](https://github.com/agentscope-ai/QwenPaw/issues/6460)

社区关注点：**MCP 驱动兼容性** 和 **前端性能优化** 是当前用户最迫切的需求。

## 5. Bug 与稳定性

按严重程度排列今日报告的 Bug：

| 严重程度 | Issue | 描述 | 是否有修复 PR |
|----------|-------|------|---------------|
| **严重** | #6470/#6469/#6468 | MCP 驱动硬编码 SSE client，导致配置了 `streamable_http` 传输协议的 MCP 服务器完全无法工作，工具加载失败。影响所有使用 Streamable HTTP 的用户。 | 无 |
| **严重** | #6464 | QwenPaw v2.0.1 在 AgentScope Platform 上无法连接任何模型，测试全部返回“API error”，模型下拉列表为空。涉及核心后端连接。 | 无 |
| **中等** | #6460 | Linux + Wayland + Edge 环境下单标签页 CPU 持续高占用，疑似大结果集渲染或 WebSocket 推送触发。影响使用 QwenPaw 管理 ComfyUI 工作流的用户。 | 无 |
| **低** | #6467 | 用户提问“翻墙节点搭建失败”，属于使用疑问，非代码 Bug。 | 无 |

**关键发现**：MCP 驱动 Bug 是设计级硬编码错误，修复需要修改 `mcp_stateful_client.py` 的 `_setup_transport` 方法。目前无关联 PR 提及，项目维护者应优先响应。

## 6. 功能请求与路线图信号

今日唯一明确的新功能请求：

- **#6466** [Feature]: Allow agent to send clickable folder/file path buttons in chat  
  用户希望在 agent 返回文件/文件夹路径时，能直接输出可点击按钮打开资源管理器。这是一个提升用户体验的小功能，但实现涉及前端 UI 组件和后端消息格式，可能被纳入下一版本的路由图。  
  [链接](https://github.com/agentscope-ai/QwenPaw/issues/6466)

此外，正在审核中的 PR **#6399**（添加 Reranker UI 配置面板）是对已合并的 #5691 的补充，旨在将重排器配置移入 `ReMeLightMemoryCard` 组件，预计会在近期合并。

**路线图信号**：CoPaw 正在加强内存搜索的定制化能力（reranker），同时社区开始关注聊天交互的便利性（可点击路径）。

## 7. 用户反馈摘要

从 Issues 评论中提炼的真实用户痛点与场景：

- **工作流集成场景**：用户 `dayofyear`（#6460）使用 QwenPaw 管理 ComfyUI 工作流，跨设备访问时遭遇高 CPU 占用，影响日常生产。其描述详细，说明该 Bug 在真实复杂场景中容易被触发。
- **部署稳定性**：用户 `albertfengjiajun`（#6464）在 AgentScope Platform 上部署 v2.0.1 后无法连接任何模型，导致服务完全不可用，该用户可能是一个团队或部署者，对平台可靠性要求高。
- **配置兼容性**：用户 `JohnyLe`（#6470）指出 MCP 驱动忽略用户显式配置，属于违反“配置即代码”原则的缺陷，影响对自定义 MCP 服务器依赖性强的开发者用户。
- **社区支持不足**：用户 `izr9`（#6467）反馈“去群里咨询也没人理我”，反映新用户入门指导渠道存在响应延迟，建议维护者加强文档或社区机器人协助。

## 8. 待处理积压

今日有 **5 个待合并 PR** 尚未完成审核，其中部分已停留数天：

| PR | 标题 | 创建时间 | 最后活跃 | 重要性 |
|----|------|----------|----------|--------|
| #6365 | fix(console): run test scripts on Windows | 7月22日 | 7月25日 | **中等** — 首次贡献者修复 Windows 测试脚本兼容性 |
| #6276 | feat(browser): unified browser — one SDK, any backend | 7月20日 | 7月25日 | **高** — 统一浏览器控制 SDK，架构级改进，已停留 5 天 |
| #6399 | feat: add reranker UI config panel to ReMeLightMemoryCard | 7月23日 | 7月25日 | **中等** — 补全已合并 reranker 的 UI 配置 |
| #6463 | feat(ci): deploy the website from the release orchestrator | 7月25日 | 7月25日 | **高** — 解决公共站点发布失效问题 |
| #6462 | docs(sandbox): clarify native Windows sandbox support | 7月25日 | 7月25日 | **低** — 文档修正，提升善 |

**特别提醒**：PR #6276（统一浏览器 SDK）涉及控制平面/执行平面分离，架构影响大，且已近一周未合并，建议维护者尽快安排 code review。此外，#6463 修复了网站部署 pipeline 的触发问题，直接影响官网更新，应优先处理。

---

*本日报基于 GitHub 公开数据自动生成，仅供内部参考。*

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

# ZeroClaw 项目动态日报 — 2026-07-26

## 1. 今日速览

ZeroClaw 在过去 24 小时内保持高活跃度：共产生 19 条 Issue 更新（新开/活跃 16 条，关闭 3 条）和 50 条 PR 更新（待合并 48 条，合并/关闭 2 条）。项目目前处于 **v0.8.4 维护列车** 冲刺阶段，多个大型特性 PR（Matrix single‑message、Telegram multi‑message、OpenAI 端点、密钥管理提取）仍在等待合并，但同时也暴露了多个高严重性 Bug（WhatsApp 安全配置绕过、运行时测试稳定性、cron 输出丢失等），社区需要加强对安全与稳定性的关注。

## 2. 版本发布

无新版本发布。当前最新稳定版为 v0.8.3，v0.8.4 维护列车（#8357）目标日期为 2026‑07‑31，相关发布 PR（#9376）已提交，正在进行 crates.io 发布准备。

## 3. 项目进展

- **已合并/关闭的 PR：**  
  - [#9123](https://github.com/zeroclaw-labs/zeroclaw/pull/9123) `fix(plugins): host‑stamp channel plugin routes` – 修复插件渠道路由宿主标记问题，增强渠道实例身份隔离。  
  - [#9270](https://github.com/zeroclaw-labs/zeroclaw/pull/9270) `fix(web/deps): resolve npm audit advisories` – 升级 `@redocly/openapi-core`、`js‑yaml` 等依赖，消除三个高/严重性安全风险。

- **已关闭的 Issue 对应修复：**  
  - [#9285](https://github.com/zeroclaw-labs/zeroclaw/issues/9285) `nested set_prop masks invalid values` – 配置值错误路径泄露问题已修复。  
  - [#9235](https://github.com/zeroclaw-labs/zeroclaw/issues/9235) `npm audit failed` 通过依赖升级解决。  
  - [#8962](https://github.com/zeroclaw-labs/zeroclaw/issues/8962) `zeroclaw‑runtime tests flake` – 部分并行测试波动已修复，但后续出现新的测试问题（见 #9357）。

> 整体而言，项目在 **依赖安全**、**插件渠道** 和 **配置解析** 上取得明确进展，但稳定性修复仍然滞后于新功能开发。

## 4. 社区热点

- **#9348 [WhatsApp 安全配置绕过]** – 评论 6 条，热度最高。用户 `belumume` 报告 `mode = business` 下 `allowed_groups` 空值导致智能体回复所有群组；该配置看上去严格但实际完全开放，被标记为 **P1 安全风险**。社区呼吁立即增加验证/警告，已有跟进 PR #9354 仅添加警告，尚未彻底修复。  
  链接：[#9348](https://github.com/zeroclaw-labs/zeroclaw/issues/9348)

- **#6489 [“一切皆插件”路线图]** – 评论 5 条，长期关注。该 RFC 提议将集成（渠道、AI 提供商等）和插件（Wasm 组件）统一为单一插件目录，是项目未来架构的核心方向。当前仍处于接受状态，无具体实施 PR。  
  链接：[#6489](https://github.com/zeroclaw-labs/zeroclaw/issues/6489)

- **#9330 [AI 辅助 PR 预审 RFC]** – 评论 2 条，社区对改进开发流程感兴趣，提议利用 CI 结果自动触发 AI 初审，保留人类终审权限。  
  链接：[#9330](https://github.com/zeroclaw-labs/zeroclaw/issues/9330)

## 5. Bug 与稳定性

| 严重程度 | Issue | 概述 | 状态 | 关联 PR |
|--------|-------|------|------|--------|
| **S1 - 安全风险** | [#9348](https://github.com/zeroclaw-labs/zeroclaw/issues/9348) | WhatsApp Web 空 `allowed_groups` 实际允许所有群组（business 模式下） | **待修复** | #9354（仅警告，未解决根本） |
| **S2 - 降级行为** | [#9357](https://github.com/zeroclaw-labs/zeroclaw/issues/9357) | `cargo test -p zeroclaw‑runtime --lib` 在 master 上 19/20 次失败；全局互斥锁中毒 | **待修复** | 无 |
| **S2 - 降级行为** | [#9328](https://github.com/zeroclaw-labs/zeroclaw/issues/9328) | verifiable-intent 约束评估未验证凭证链（安全架构缺陷） | **待修复** | 无 |
| **S2 - 降级行为** | [#9340](https://github.com/zeroclaw-labs/zeroclaw/issues/9340) | CLI 创建的 cron job 输出硬编码为 `none`，运行结果被丢弃 | **待修复** | 无 |
| **S2 - 降级行为** | [#9373](https://github.com/zeroclaw-labs/zeroclaw/issues/9373) | peer-agent 交付路径缺失成本跟踪上下文，预算不执行 | **待修复** | 无 |
| **S2 - 降级行为** | [#9363](https://github.com/zeroclaw-labs/zeroclaw/issues/9363) | ZeroCode 和 Web 的配置元数据不随语言本地化 | **待修复** | #9377（i18n 翻译 PR） |
| **S3 - 小问题** | [#9374](https://github.com/zeroclaw-labs/zeroclaw/issues/9374) | `CLI run()` 在 12 条退出路径上未正确发送 `AgentEnd` | **待修复** | 无 |
| **S3 - 小问题** | [#9366](https://github.com/zeroclaw-labs/zeroclaw/issues/9366) | WhatsApp Web 接受但不使用 `approval_timeout_secs` | **待修复** | 从 #9348 分离 |

> 今日新增 Bug 集中在运行时生命周期、成本跟踪和配置一致性上，整体健康度因 S1/S2 数量较多而偏低，需维护者优先处理 #9348 和 #9357。

## 6. 功能请求与路线图信号

- **v0.8.4 维护列车（#8357）** – 距离目标日期（7 月 31 日）仅剩 5 天，包含多项修复和增强，需关注未完成的项目是否按时合并。  
  链接：[#8357](https://github.com/zeroclaw-labs/zeroclaw/issues/8357)

- **#8583 [channel/source 边界清理]** – 渠道与源架构重构跟踪，计划统一生命周期、流式、信任、配置等模块，当前标记为 in‑progress。  
  链接：[#8583](https://github.com/zeroclaw-labs/zeroclaw/issues/8583)

- **#7130 [workspace 全局 forbid(unsafe_code)]** – 提议仅在 `aardvark‑sys` 中允许 unsafe，提升安全性。已接受 50 天，尚无 PR。  
  链接：[#7130](https://github.com/zeroclaw-labs/zeroclaw/issues/7130)

- **大型特性 PR 等待合并（均标记为 needs-author-action 或待审）：**  
  - [#8443](https://github.com/zeroclaw-labs/zeroclaw/pull/8443) Matrix single‑message 进度草稿（size:XL）  
  - [#8561](https://github.com/zeroclaw-labs/zeroclaw/pull/8561) Telegram multi_message 流模式（size:XL）  
  - [#8486](https://github.com/zeroclaw-labs/zeroclaw/pull/8486) OpenAI chat completions 端点（size:XL）  
  - [#9194](https://github.com/zeroclaw-labs/zeroclaw/pull/9194) 密钥提取 KeySource trait（size:XL）  
  - [#7821](https://github.com/zeroclaw-labs/zeroclaw/pull/7821) 沙箱策略配置（size:XL）

  这些功能将显著增强渠道能力、安全基线和互操作性，但均因作者未响应或审核进度缓慢而停滞，可能无法赶上 v0.8.4。

## 7. 用户反馈摘要

- **痛点：**  
  - WhatsApp Web 配置误导（#9348）：用户强调 “empty allowed_groups permits all groups” 是严重安全隐患，期望至少添加警告或拒绝启动。  
  - CLI cron 输出丢失（#9340）：用户期望 cron 任务能够通过 `delivery` 配置输出结果，而非静默丢弃。  
  - 配置错误消息混乱（#9239）：`config patch --json` 在某些路径下输出纯文本而非 JSON 错误，影响工具集成。  
  - 国际化不足（#9363）：非英语用户发现配置元数据未翻译，导致操作困难。

- **正向反馈：**  
  - #9330 RFC 得到初步正面响应，社区认可 AI 辅助审阅的价值，但同时强调人类最终控制权。  
  - #9377 提供了完整的中文（zh）翻译 PR，证明社区对 i18n 的积极贡献。

## 8. 待处理积压

以下 Issue 或 PR 已长时间无实质进展，提醒维护者重点关注：

| 类型 | 编号 | 描述 | 长期未响应时长 | 优先级 |
|------|------|------|---------------|-------|
| Issue | [#7130](https://github.com/zeroclaw-labs/zeroclaw/issues/7130) | workspace 全局 forbid(unsafe_code) | 53 天 | P2 |
| Issue | [#6489](https://github.com/zeroclaw-labs/zeroclaw/issues/6489) | 一切皆插件路线图 RFC | 81 天 | P2 |
| PR | [#7821](https://github.com/zeroclaw-labs/zeroclaw/pull/7821) | featsandbox policy config | 39 天（needs-author-action） | 高 |
| PR | [#8438](https://github.com/zeroclaw-labs/zeroclaw/pull/8438) | feat(cron): shell_output_format | 28 天（needs-author-action） | 高 |
| PR | [#9194](https://github.com/zeroclaw-labs/zeroclaw/pull/9194) | feat(secrets): KeySource trait | 6 天（needs-author-action） | 高（XL） |
| PR | [#8561](https://github.com/zeroclaw-labs/zeroclaw/pull/8561) | Telegram multi_message | 26 天（needs-author-action） | 高（XL） |
| PR | [#8486](https://github.com/zeroclaw-labs/zeroclaw/pull/8486) | OpenAI endpoints | 27 天（needs-author-action） | 高（XL） |

> 多项 XL 级 PR 因作者未响应而阻塞，建议维护者统一联系贡献者，决定是否接管或关闭，避免影响 v0.8.4 发布窗口。同时 #9340、#9348 等高严重性 Bug 尚无直接修复 PR，应优先分配资源。

---

*数据来源：[ZeroClaw GitHub Repository](https://github.com/zeroclaw-labs/zeroclaw)，统计时间窗口 2026-07-25 00:00 UTC 至 2026-07-26 00:00 UTC。*

</details>

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*