# OpenClaw 生态日报 2026-06-30

> Issues: 352 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-06-30 11:30 UTC

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

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据您提供的 OpenClaw 项目数据，现生成 2026-06-30 的项目动态日报。

---

## OpenClaw 项目动态日报 | 2026-06-30

### 1. 今日速览

今日 OpenClaw 项目**极其活跃**，但呈现出典型的“高负载低产出”健康度状态。过去24小时内，社区提交了352条 Issue 和500条 PR，然而被合并或关闭的 PR 仅有24条（占4.8%），大量工作积压在待处理队列中。同时，0个新版本发布，且无最新的Release信息，表明项目可能处于密集开发或紧急修复的“攻坚期”。讨论热点从 session 状态丢失、消息截断等核心稳定性问题，到安全权限、API 兼容等生产环境关切，反映出社区对项目稳定性和安全性的焦虑与强诉求。

### 2. 版本发布

无 (过去24小时内无新版本发布或Release信息)。

### 3. 项目进展

过去24小时内，虽然新增了大量 PR，但已合并/关闭的 PR 数量较少（24条），主要聚焦于小范围修复和自动化流程。以下为几个关键进展：

- **关键问题修复**: PR [#98079](https://github.com/openclaw/openclaw/pull/98079) 修复了 Ollama 扩展中的流读取器资源泄漏问题；PR [#98048](https://github.com/openclaw/openclaw/pull/98048) 与 PR [#98047](https://github.com/openclaw/openclaw/pull/98047) 为 Minimax 和 OpenRouter 扩展中的音乐生成功能增加了对畸形数据帧的容错处理，提升了服务稳定性。
- **平台兼容性**: PR [#98093](https://github.com/openclaw/openclaw/pull/98093) 修复了 Windows 平台上 `isExecutableFile` 函数无法正确继承调用者环境变量 `PATHEXT` 的问题，改善了对 Windows 原生工具链的支持。
- **渠道修复**: 部分针对 Telegram ([#94970](https://github.com/openclaw/openclaw/pull/94970)) 和 Feishu ([#73399](https://github.com/openclaw/openclaw/pull/73399)) 渠道的修复 PR 已被合并，持续优化了多平台消息路由与展示体验。

项目整体在**稳定性修补**和**生态扩展**方面有小幅推进，但面对庞大的 Issue 和 PR 积压，推进速度显然跟不上社区反馈的速度。

### 4. 社区热点

今日社区讨论热度极高，多个 Issue 和 PR 获得了大量评论和点赞，反映出用户在使用中遇到的普遍痛点：

- **`#94518` [DeepSeek 缓存命中率下降](https://github.com/openclaw/openclaw/issues/94518)**: 获得 **8个赞**，评论6条。用户反馈从 v5.28 升级到 v6.x 后，DeepSeek 的提示缓存命中率从高位暴跌至<10%。这直接导致了 API 调用成本飙升和响应速度下降，是社区最关心的问题之一。核心矛盾在于新的“边界感知缓存”机制破坏了前缀匹配。
- **`#84569` [WhatsApp 会话因长模型调用而卡死](https://github.com/openclaw/openclaw/issues/94518)**: 获得 **3个赞**，评论6条。用户报告在长时间模型调用（120-240秒）期间，WhatsApp 会话会陷入“stalled”状态并有几率丢失消息。这暴露了在非持久连接渠道（如 WhatsApp）上处理长耗时 LLM 请求时的 session 管理缺陷。
- **`#84256` [插件更新命令降级问题](https://github.com/openclaw/openclaw/issues/84256)**: 获得 **3个赞**，评论4条（已关闭）。用户发现 `openclaw plugins update --all` 命令会主动**降级**那些已被用户手动更新的 npm 插件。这是一个令人沮丧的UX问题，社区对“更新”命令抱有“更新到最新”的预期，而非“回滚至初始”。
- **`#84527` [呼吁集成 Antigravity CLI](https://github.com/openclaw/openclaw/issues/84527)**: 获得 **10个赞**，评论3条。此功能请求获得了极高的社区共鸣。由于 Google 宣布 Gemini CLI 即将退役并转向 Antigravity CLI，用户迫切希望 OpenClaw 能跟上官方步伐，将 `agy` 作为新的 CLI 后端，避免服务中断。这直接反映了项目对上游生态变化的响应速度要求。

### 5. Bug 与稳定性

今日报告的 Bug 主要集中在**状态丢失、消息截断、会话崩溃**等生产级 P1 问题上，以下按严重程度排列：

- **P1 级别**
    - **`#84516` [Codex 应用服务器长回复被无声截断](https://github.com/openclaw/openclaw/issues/84516)**: 即使 `stop=null` 且未发生中止，长度超过1000-1100字符的回复也会被截断。**严重性极高**，直接影响用户与大模型的交互完整性。_当前无 fix PR。_
    - **`#83959` [Codex 应用服务器启动重试耗尽可能耗尽](https://github.com/openclaw/openclaw/issues/83959)**: 在替换服务器就绪前，启动重试机制可能已耗尽，导致 `crash-loop`。**稳定性风险高**，影响服务可用性。_有关联的 fix PR 打开中 (`linked-pr-open`)。_
    - **`#92433` [子代理完成时，父代理处理流程被悄无声息丢弃](https://github.com/openclaw/openclaw/issues/92433)**: 当子代理完成时，如果父代理的运行已经结束，任务会被静默丢弃。这是多代理协作模型下的一个严重架构缺陷。_当前无 fix PR。_
    - **`#84536` [预占上下文溢出会静默杀死嵌入会话](https://github.com/openclaw/openclaw/issues/84536)**: 会话因上下文溢出而被静默销毁，用户无感知。_当前无 fix PR。_

- **P2 级别**
    - **`#81913` [暴露稳定的插件 SDK 表面](https://github.com/openclaw/openclaw/issues/81913)**: 第三方插件开发者必须依赖内部API，稳定性无法保障。_该功能请求因**安全审查**而阻塞，但已有打开的 PR。_
    - **`#97877` [`empty-error-retry` 被`hadPotentialSideEffects` 阻塞](https://github.com/openclaw/openclaw/issues/97877)**: 临时性5xx错误在会话执行过任何工具调用后无法重试，导致静默失败。
    - **`#83968` [macOS 上 Gateway 因断言失败崩溃](https://github.com/openclaw/openclaw/issues/83968)**: 特定版本（`2026.5.18`）的回归问题，导致 macOS 上的 Gateway 无法启动。

### 6. 功能请求与路线图信号

除社区热点的 `agy` 集成外，以下功能请求反映了用户对项目发展方向的期待：

- **`#81913` 稳定插件 SDK**: 该项请求已从简单功能提升为“影响：安全”级别的议题，并关联了打开的 PR。这表明项目方可能已在推进插件生态的基础设施建设，有望在下一版本中看到官方指引。
- **`#82450` 为盲人用户提供无障碍线性持久工作区模式**: 一位全盲用户提出了一个高质量的功能请求。这不仅是可访问性问题，也反映了用户希望更稳定、可预测的工作区交互模式。是否纳入路线图反映了项目对社会责任的考量。
- **`#27482` 支持直接上传视频到 LLM**: 这是多模态能力的明确需求。考虑到主流LLM都已支持视频，该请求被纳入未来版本的可能性很高。

### 7. 用户反馈摘要

从今日评论区中，可以提炼出以下几点用户心声：

- **痛点最突出的是“静默失败”**：用户对 `#84516` (句子被截断而不报错)、`#84536` (会话被杀死而不通知) 以及 `#92433` (子代理任务丢失) 感到沮丧。他们期望系统要么成功，要么清晰告知失败原因。
- **对“更新/升级”动作的恐惧**：多个 Issue（如 `#84256` 与 `#94518`）表明，“更新”操作对用户而言充满了不确定性，可能导致降级、锁死或性能灾难。社区急需一个可靠的回滚机制和更透明的更新日志。
- **对上游生态变化的敏感**：`#84527` 的高点赞量表明，社区期望 OpenClaw 能紧跟如 Google等大厂的技术栈变迁，否则会因“搬家”而带来巨大的迁移成本。
- **对安全配置的困惑**：`#97970` (更新导致 `gateway.bind` 与 `auth.mode` 冲突) 和 `#81917` (dashboard 日志暴露 token) 表明，配置项间的隐性逻辑和默认值变更让用户感到困惑和安全焦虑。

### 8. 待处理积压

以下 Issue 和 PR 长期未得到有效响应或解决，需要维护者重点关注：

- **`#81913` [Feature: Expose stable plugin SDK](https://github.com/openclaw/openclaw/issues/81913)**: 该 Feaure Request 从 2026-05-14 提出，社区讨论了6次，关联 PR 也已打开，但状态处于 **needs-security-review** 已近三周，阻碍了第三方生态发展。
- **`#81525` [Bug: media-understanding 模型验证缺失](https://github.com/openclaw/openclaw/issues/81525)**: 该 bug 报告于 2026-05-13，虽已关闭但无人解决，其影响范围（将无视觉功能的模型错误用于图像处理）具有普遍性，可能频繁影响用户。
- **`#83736` [Gateway 不应因节点版本小差异而拒绝升级](https://github.com/openclaw/openclaw/issues/83736)**: 此问题的存在意味着分布式场景下的运维升级流程非常脆弱。从提报到现在已超40天，仍处于 **needs maintainer review**，是生产环境部署的一个隐患。
- **PR `#80453` [修复 env 文件中的 GH_TOKEN 传播](https://github.com/openclaw/openclaw/pull/80453)**: 该PR旨在解决操作员凭证安全管理的实际问题，创建于5月初，修改范围不小，但已近两个月处于 **waiting on author** 状态，亟需维护者介入推动。

---

## 横向生态对比

好的，这是基于您提供的各项目动态日报，综合生成的横向对比分析报告。

---

### AI 智能体与个人 AI 助手开源生态横向对比分析报告 (2026-06-30)

**报告日期:** 2026-06-30
**分析范围:** OpenClaw, NanoBot, Hermes Agent, PicoClaw, NanoClaw, NullClaw, IronClaw, LobsterAI, CoPaw, ZeroClaw 等10个核心项目

---

#### 1. 生态全景

2026年6月30日，个人 AI 助手与自主智能体开源生态呈现出 **“大平台攻坚，小项目创新”** 的蓬勃态势。整体生态正处于从“可用”向“稳定、高效、安全”过渡的关键阶段，社区对 **稳定性、Token 消耗、多通道集成** 的焦虑成为普遍痛点。大型项目（如 OpenClaw, ZeroClaw）正面临海量 PR/Issue 积压的“幸福的烦恼”，而中小型项目（如 Nanobot, NullClaw）则在特定功能（自动化、CLI体验）上快速迭代，展现出强大的社区驱动力。安全（SSRF、凭证泄露）和可观测性（OTel、诊断日志）成为所有项目的共同投资领域。

#### 2. 各项目活跃度对比

| 项目名称 | Issues (24h) | PRs (24h) | 新版本发布 | 健康度评估 | 活跃度评级 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 352 (新) | 500 (新) / 24 (合并) | 无 | 🟡 **中等** (高负载，积压严重) | 🔥🔥🔥🔥🔥 |
| **NanoBot** | 5 (新) / 8 (关闭) | 54 (新) / 31 (合并) | 无 | 🟢 **良好** (迭代快，修复及时) | 🔥🔥🔥🔥🔥 |
| **Hermes Agent** | 50 (新) | 50 (新) | 无 | 🟢 **良好** (安全修复集中，Client优化) | 🔥🔥🔥🔥 |
| **PicoClaw** | 6 (新) | 7 (新) | **有** (Nightly) | 🟡 **中等** (潜在回归问题) | 🔥🔥🔥 |
| **NanoClaw** | 2 (新) | 6 (新) / 1 (合并) | 无 | 🟢 **良好** (功能扩展期) | 🔥🔥🔥 |
| **NullClaw** | 1 (新) | 4 (新) / 1 (合并) | 无 | 🟢 **良好** (大型功能待合并) | 🔥🔥 |
| **IronClaw** | 16 (新) | 50 (新) | 无 | 🟡 **中等** (测试筑基，Bug并发) | 🔥🔥🔥🔥 |
| **LobsterAI** | 12 (新) | 16 (新) / 13 (合并) | **有** (`2026.6.29`) | 🟡 **中等** (性能瓶颈争议) | 🔥🔥🔥🔥 |
| **CoPaw** | 众多 | 75 (总计) / 23 (合并) | 无 | 🟢 **良好** (社区贡献活跃) | 🔥🔥🔥🔥 |
| **ZeroClaw** | 50 (新) | 50 (新) / 9 (合并) | 无 | 🟢 **良好** (基建完善，功能收尾) | 🔥🔥🔥🔥🔥 |

#### 3. OpenClaw 在生态中的定位

- **核心参照地位稳固，但面临挑战**: OpenClaw 凭借其庞大的社区基础和功能广度，仍是生态中无可争议的“参照系”。其日处理 **352个Issue** 和 **500个PR** 的规模，远超其他项目，体现了其生态系统的深度和广度。
- **社区规模与治理压力并存**: 相较于其他项目，OpenClaw 拥有最庞大的贡献者群体和最活跃的社区。然而，这也带来了严重的“高负载低产出”问题（仅合并4.8%的PR），**积压工作**是其最大的挑战。相比之下，NanoBot、Hermes Agent 等项目在修复速度和社区响应上表现得更为敏捷。
- **技术路线与目标用户**: OpenClaw 定位为功能全面的**通用平台**，覆盖从多模型支持、插件系统到复杂渠道的方方面面。其优势在于“大而全”，但也因为功能耦合度高，导致修复和迭代速度慢。其他项目如 NanoClaw 则通过**Agent模板**系统，在易用性和复用性上进行差异化竞争。

#### 4. 共同关注的技术方向

多个项目不约而同地涌现出以下共同需求，表明这已是生态共识：

1.  **稳定性与异常处理（涉及：OpenClaw, NanoBot, Hermes Agent, IronClaw, LobsterAI）**:
    - **具体诉求**: 解决“静默失败”（消息截断、会话丢失、Token消耗异常）。OpenClaw (P1: 消息截断)、Hermes Agent (DashScope死循环)、LobsterAI (Token消耗暴涨2000x)、IronClaw (多工具调用协议违规) 均反映了此问题。
    - **趋势**: 用户对 Agent 行为的**可预测性**和**透明度**要求急剧上升，模糊的错误提示已无法接受。

2.  **成本与资源优化（涉及：NanoBot, LobsterAI）**:
    - **具体诉求**: NanoBot 的“推理努力级别自动升级”、LobsterAI 的“Token消耗异常”都指向了**智能化资源调度**。用户希望 Agent 能根据任务复杂度动态调整 Token 或推理成本，而非无差别地“烧钱”。
    - **趋势**: 从“跑通”到“跑得省”，成本意识成为影响用户选择的重要指标。

3.  **多通道与端到端安全（涉及：PicoClaw, NullClaw, ZeroClaw）**:
    - **具体诉求**: PicoClaw (SimpleX/Tox)、NullClaw (Telegram空闲断连)、ZeroClaw (MCP工具TUI不可见)。用户希望 Agent 能无缝、稳定地接入各种通信协议，并保证端到端的安全性。
    - **趋势**: 去中心化、隐私保护的通信协议（如SimpleX）开始进入社区视野，预示更广泛的应用场景。

4.  **可观测性与诊断能力（涉及：OpenClaw, IronClaw, CoPaw）**:
    - **具体诉求**: OpenClaw (社区期待透明更新日志)、IronClaw (E2E测试失败、诊断日志)、CoPaw (用户要求日志中明确修复方案)。开发者需要更精细的遥测数据来定位问题。
    - **趋势**: OTel 和 专用的诊断API 将成为下一代平台的标配。

#### 5. 差异化定位分析

| 项目 | 功能侧重 | 目标用户 | 关键差异点 |
| :--- | :--- | :--- | :--- |
| **OpenClaw** | **全能平台** | 追求功能全面的开发者、企业用户 | **最庞大的生态系统**，插件/渠道最丰富，但复杂度高，迭代慢。 |
| **NanoBot** | **自动化工作流引擎** | 希望快速构建自动化Agent的用户 | **自动化体系（cron+script triggers）** 是核心亮点，轻量级代码库，社区反馈“易于理解”。 |
| **Hermes Agent** | **安全与Client体验** | 注重安全和高频CLI/Desktop用户 | **强安全（IDOR/SSRF修复）**，重视CLI和Desktop的交互体验优化。 |
| **PicoClaw** | **嵌入式/边缘AI网关** | NanoKVM等硬件设备用户 | **硬件形态绑定**（NanoKVM），聚焦于小型化、低功耗的AI网关场景。 |
| **NanoClaw** | **易用性与快速部署** | 入门级开发者、中小团队 | **Agent模板系统** 极大降低门槛，渠道扩展（Discord, WeChat）迅速。 |
| **NullClaw** | **CLI与自动化基石** | 重度CLI用户、运维开发者 | **大型功能（Cron子代理）** 稳步推进，CLI体验打磨细致。 |
| **IronClaw** | **质量与可测试性** | 企业级用户、对稳定性要求严苛的团队 | **极致的测试投入**（E2E、压力测试、QA框架），质量保障是其差异化优势。 |
| **LobsterAI** | **协作（Cowork）** | 协同工作场景的团队 | **深度集成协作功能**（cowork模块），但同时面临性能优化的核心挑战。 |
| **CoPaw (QwenPaw)** | **中文生态与实用Agent** | 中文开发者、钉钉/飞书用户 | **中文IM深度集成**（钉钉@功能、飞书），社区贡献者有明确的中文场景需求。 |
| **ZeroClaw** | **架构治理与可观测性** | 技术架构师、追求标准化流程的团队 | **重视治理（RFC、CI安全）**，推动标准化和可观测性，是走向成熟项目的标志。 |

#### 6. 社区热度与成熟度

- **快速迭代阶段 (🔥🔥🔥🔥🔥)**: **NanoBot**, **Hermes Agent**, **ZeroClaw**。这些项目PR/Issue处理效率高，对社区反馈响应快，正在积极扩展新功能和巩固基础设施，呈现出极高的开发活力。
- **质量巩固阶段 (🔥🔥🔥🔥)**: **OpenClaw**, **IronClaw**, **CoPaw**。项目体量较大，正处于从快速扩展转向稳定发布的“攻坚期”。团队精力集中在修复大量Bug、补齐测试、优化CI/CD上，为下一个重大版本做准备。
- **功能扩展与探索阶段 (🔥🔥🔥)**: **PicoClaw**, **NanoClaw**, **NullClaw**。项目活跃度稳定，社区积极贡献新渠道和功能，但项目成熟度和治理流程仍在发展中，部分大型功能或安全补丁存在积压。

#### 7. 值得关注的趋势信号

1.  **“自动化”是下一个核心战场**: NanoBot 对自动化框架的重构，以及 NullClaw 的 “Cron 子代理” 大型PR，都表明行业正从简单的对话式 Agent 向 **“可编排、可自动化执行的智能工作流引擎”** 演进。这将是决定个人 AI 助手能否真正“解放生产力”的关键。
2.  **“零信任”安全模型下沉到Agent架构**: 从 Hermes Agent 的IDOR修复，到 IronClaw 的SSRF防护，再到 CoPaw 的凭证泄露修复，安全已不仅仅是网络层的问题，而是深入到 Agent 的**身份验证、授权、数据隔离和插件安全**的方方面面。未来的 Agent 平台必须具备原生的安全治理能力。
3.  **开发者体验（DX）成为关键竞争力**: 当基础功能趋同后，**易用性、清晰的错误信息、详尽的诊断日志和简便的配置流程** 将成为项目脱颖而出的关键。NanoBot 因“轻量级代码库易于理解”而获得用户好评，而 OpenClaw 和 LobsterAI 则因复杂的配置和模糊的错误提示受到了社区批评。
4.  **硬件与软件加速融合**: PicoClaw 与 NanoKVM 的结合，以及 ZeroClaw 对硬件抽象层（`aardvark-sys` crate）的讨论，预示着未来AI Agent将不再局限于纯软件形态，而是会与**边缘计算设备、嵌入式系统**形成更紧密的物理-数字融合生态。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

# 🤖 NanoBot 项目动态日报 | 2026-06-30

---

## 1. 🌟 今日速览

今日项目活跃度极高。过去 24 小时内，共处理了 **13 条 Issue**（关闭 8 条，新开 5 条）和 **54 个 Pull Request**（合并/关闭 31 个，待合并 23 个）。社区提交和核心贡献者反馈均保持强劲势头。项目在自动化框架重构、内存/Dream 系统优化、代理稳定性加固（上下文溢出保护）以及 Windows 平台兼容性方面取得了显著进展。同时，多个由社区驱动的 Bug 修复（如 MCP 凭证泄露、服务重启崩溃、会话数据中毒）已被快速关闭，体现了项目维护的高效与严谨。

---

## 2. 📦 版本发布

**无**

---

## 3. 🚀 项目进展

今日合并/关闭了大量重要 PR，项目整体向前迈进了关键一步，主要集中在以下三大方向：

### 3.1 自动化与调度体系重构
- **PR #4330** `[enhancement, valid, webui] feat(webui): add automation management view`：为 WebUI 新增了独立的自动化管理视图（排序、搜索、编辑、启停、删除），统一了 cron 与脚本触发的流程。这是将系统从“计划任务”升级为“自动化引擎”的核心节点。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4330)
- **PR #4382** `[enhancement] feat(automation): add script triggers`：将 cron 任务重构成了 `nanobot.automations.*` 架构，并引入了由脚本触发的自动化能力，标志着自动化体系的正式模块化。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4382)

### 3.2 内存与 Dream 系统优化
- **PR #4359** `fix(agent): refresh goal continuation context`：修复了长周期目标（long_task）中，后续提示无法引用当前轮次创建的目标的问题，提升了持续性任务的上下文感知能力。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4359)
- **PR #4369** `[valid] Explain empty Dream runs`：将原本无反馈的 `/dream` 操作替换为有恢复建议的提示，改善了用户与 Dream 系统的交互体验。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4369)
- **PR #4370** `[valid] Enable idle auto-compact by default`：将自动压缩的默认时间从 **0（禁用）** 改为 **15 分钟**，默认开启即无需用户额外配置即可获得更好的上下文管理效果。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4370)

### 3.3 稳定性与兼容性修复
- **PR #4349** `[valid] fix(session): preserve user turns in replay-window history`：修复了重放窗口截断导致长用户轮次内 LLM 回复从中间开始的问题，提升了重放可靠性。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4349)
- **PR #4578** `[valid] feat(providers): support provider-scoped proxy config`：为 OpenAI 兼容提供商和 Codex 增加了 Provider 级别代理配置支持，解决了企业环境中需绕过全局代理访问特定 API 的需求。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4578)
- **PR #4545** `[invalid, fix] fix(exec): default Windows commands to PowerShell`：修复了 Windows 环境下单行命令默认使用 cmd.exe 导致的跨盘 `cd` 失败和语法不兼容问题，统一使用 PowerShell 且允许自定义 shell 参数。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4545)
- **PR #4609** `fix(webui): keep idle compaction out of session recency`：修复了 WebUI 中空闲压缩会错误刷新会话时间戳的问题，避免因后台维护操作导致会话排序错乱。 [查看 PR](https://github.com/HKUDS/nanobot/pull/4609)

---

## 4. 🔥 社区热点

| 项目 | 标题 | 评论数 | 链接 |
|------|------|--------|------|
| Issue #4419 | `[OPEN]` Feature: Automatic reasoning effort escalation | 4 | [查看](https://github.com/HKUDS/nanobot/issues/4419) |
| Issue #4418 | `[CLOSED]` Feature Request: Heartbeat tasks should deliver results to the channel... | 4 | [查看](https://github.com/HKUDS/nanobot/issues/4418) |

**背后的诉求**：
- **#4419（推理努力级别自动升级）**：用户提出推理模型（如 OpenAI、Claude）现已支持不同“推理深度”参数，但 Nanobot 目前只支持全局默认配置。社区希望系统能根据任务复杂度（如简单问答 vs. 复杂分析）**自动调整推理努力级别**，以减少不必要的计算消耗。该项目反映了用户对“智能化资源调度”的深度需求。
- **#4418（心跳任务结果投递到指定频道）**：用户抱怨当前 Heartbeat 任务的结果总会投递到**最近活跃的聊天频道**，而非任务被添加时的原始频道。在多频道多场景下，这导致信息错位的严重用户困惑。该问题已关闭，说明维护者已纳入考量或已合并相关 PR 拓扑。

---

## 5. 🐛 Bug 与稳定性

### 严重程度：高

1. **Issue #4595** `[CLOSED] Bug: apply_final_call_ids overwrites correct tool_call ids for non-file-edit tools`  
   - **问题**：`StreamingFileEditTracker` 中的 `apply_final_call_ids()` 错误地将流式 Delta 状态中的旧 ID 覆盖了所有类型的工具调用（包括 read_file、web_search 等）的正确 ID，导致**会话状态永久中毒**，后续回调全部错位。  
   - **状态**：已关闭，已有针对性的修复。  
   - **链接**：[#4595](https://github.com/HKUDS/nanobot/issues/4595)

2. **Issue #4513** `[CLOSED] [bug] 使用 nssm 把 nanobot 设置为系统服务，执行 /restart 重启程序的异常问题`  
   - **问题**：Windows 下使用 nssm 将 Nanobot 注册为系统服务后，通过 `/restart` 重启时出现端口被占用（Restart 模式）或进程存活但服务已停止（Oneshot 模式）的异常。  
   - **状态**：已关闭，有 PR 跟踪修复。  
   - **链接**：[#4513](https://github.com/HKUDS/nanobot/issues/4513)

### 严重程度：中

3. **Issue #4599** `[CLOSED] [bug] Bug: Install script crash issue`  
   - **问题**：Linux 默认安装脚本在 TUI 界面时瞬时崩溃，用户未进行任何操作即退出。  
   - **状态**：已关闭。  
   - **链接**：[#4599](https://github.com/HKUDS/nanobot/issues/4599)

4. **Issue #1023** `[CLOSED] Provider login tokens not persisted + config refresh drops unknown providers`  
   - **问题**：`provider login` 执行 OAuth 流程成功后未保存 Token；同时配置刷新时会删除未识别的 Provider 配置。  
   - **状态**：已关闭，但属长期遗留问题。  
   - **链接**：[#1023](https://github.com/HKUDS/nanobot/issues/1023)

### 严重程度：低

5. **Issue #4592** `[OPEN] ExecTool path extraction misses absolute paths after equals sign`  
   - **问题**：`restrictToWorkspace` 启用时，路径提取正则未将 `=` 作为有效分隔符，导致类似 `output=/tmp/foo` 的路径绕过安全检查。  
   - **状态**：OPEN，暂无关联 PR。  
   - **链接**：[#4592](https://github.com/HKUDS/nanobot/issues/4592)

---

## 6. 📋 功能请求与路线图信号

| 请求 | 来源 | 对路线图的影响 | 已有在途 PR |
|------|------|--------------|-------------|
| **Anthropic OAuth 支持** | Issue #4604 | 高 —— 随着 Claude 在企业中广泛应用，OAuth 认证成为刚需 | 无 |
| **外部脚本触发动作** | Issue #4605 | 高 —— 呼应已合并的自动脚本触发（PR #4382），属同一能力谱系 | 可能由同一路线图推进 |
| **基于等级的推理努力自动升级** | Issue #4419 | 中 —— 智能推测 + 节约 Token | 无 |
| **搜索历史只读工具** | Issue #4440 | 中 —— 增强记忆召回的可编程性 | PR #4439 在途 |
| **GitHub Copilot for Business 支持** | Issue #4220 | 中 —— 企业级 API 端点差异 | 无 |
| **子进程 Conda 环境支持** | Issue #4580 | 低 —— 主要影响需要虚拟环境的执行场景 | PR #4588 在途（上下文压缩） |

**路线图信号**：自动化框架（cron + script triggers）和内存系统（Dream + auto-compact）的系列合并，暗示 2.0 版本的“智能工作流引擎”方向正在成型。

---

## 7. 💬 用户反馈摘要

- **正面**：用户在 [#4605](https://github.com/HKUDS/nanobot/issues/4605) 中高度评价项目：“与 OpenClaw 相比，Nanobot 的轻量级代码库使得阅读和理解源代码变得轻松，我非常欣赏这一点。” 用户已基于此构建了 Gmail 邮件分类技能，并希望扩展外部触发能力。
- **痛点**：用户反馈 [#4418](https://github.com/HKUDS/nanobot/issues/4418) 中心跳任务结果错投到错误频道，是**多频道运营用户**的常见痛点。另外 [#4595](https://github.com/HKUDS/nanobot/issues/4595) 中“会话状态中毒”的严重性让用户对长期运行会话的可靠性产生疑虑。
- **期待**：用户希望 Nanobot 能提供“高级推理努力自动升级”和“Conda 虚拟环境支持”，反映了专业用户对**资源精细化管理**和**运行环境隔离**的明确需求。

---

## 8. ⏳ 待处理积压

### 8.1 长期未响应的重要 Issue

- **Issue #1023** `Provider login tokens not persisted + config refresh drops unknown providers`  
  - **创建**：2026-02-22 | **最后更新**：2026-06-30  
  - **原因**：虽近期有关闭动作，但 Token 持久化和配置冲突问题是新 Provider 接入的持续痛点。  
  - **链接**：[#1023](https://github.com/HKUDS/nanobot/issues/1023)

- **Issue #4220** `Add GitHub Copilot for Business / GitHub Enterprise support`  
  - **创建**：2026-06-06 | **最后更新**：2026-06-30  
  - **原因**：企业用户无法使用基于公共 API 的 Copilot，此为阻却性问题。  
  - **链接**：[#4220](https://github.com/HKUDS/nanobot/issues/4220)

### 8.2 需特别关注的未合并 PR

- **PR #4545** `fix(exec): default Windows commands to PowerShell (allow shell parameter)`  
  - **风险**：虽已合并相关讨论，但 Windows 平台稳定性升级需要尽快合入。  
  - **链接**：[#4545](https://github.com/HKUDS/nanobot/pull/4545)

- **PR #4608** `fix(agent): add emergency tool result truncation to prevent context overflow`  
  - **风险**：多工具调用引起的上下文溢出是实际运行中最常见的中毒事故，该 PR 提供了紧急截断策略以阻断灾难性扩展。  
  - **链接**：[#4608](https://github.com/HKUDS/nanobot/pull/4608)

---

**报告日期**：2026-06-30  
**数据来源**：GitHub Repository [HKUDS/nanobot](https://github.com/HKUDS/nanobot)

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据提供的 Hermes Agent GitHub 数据，现生成 2026-06-30 的项目动态日报。

---

## Hermes Agent 项目动态日报 | 2026-06-30

### 1. 今日速览

Hermes Agent 项目今日进入高活跃度状态，过去 24 小时内共产生 50 个 Issue 和 50 个 PR，更新密集。核心开发团队正在集中精力解决稳定性与安全性问题，特别是针对 **MoA (Mixture of Agents) 架构**、**DeepSeek 提供商兼容性** 及 **SSRF/IDOR 等安全漏洞** 的修复工作取得了显著进展。社区热点聚焦于 **Telegram 富消息** 新功能和对 **OpenAI Codex 提供商** 崩溃的反馈。此外，大量针对 CLI、Desktop 和 TUI 客户端的体验优化 PR 正在快速推进，表明项目正从基础设施构建转向打磨最终用户体验。

### 2. 版本发布

无新版本发布。

### 3. 项目进展

今日项目核心进展体现在多个重要 Bug 的修复和关键功能的合并上，显著提升了系统的稳定性与安全性。

- **关键安全漏洞修复：**
    - **[IDOR 防护]**：PR #52355 成功合入，限制了 `/resume` 和 `/sessions` 接口的访问范围，防止授权用户越权访问其他用户的会话，这是一项关键的授权修复。
    - **[敏感信息泄露]**：PR #55576 已合并，现 `hermes status --all` 命令能够正确遮盖 API 密钥，方便用户安全地分享配置状态。
    - **[任意文件读取]**：Issue #8733 中报告并通过 PR（推测）修复了 WeCom 适配器中的一个路径遍历漏洞，该问题会导致攻击者通过 `file://` 协议读取服务器任意文件。

- **核心 Agent 稳定性和兼容性修复：**
    - **[Assistant 消息合并]**：PR #49162 和 PR #29168 已成功合并。这两个 PR 解决了 DeepSeek 等严格 OpenAI 兼容提供商的一个核心问题：当 Agent 并行产生多个 `tool_calls` 时，存储的多个连续 `assistant` 消息会导致 API 调用返回 400 错误。现在这些消息会被正确合并后再发送，极大地提高了与 DeepSeek 的兼容性。
    - **[MoA 架构路由修复]**：PR #54425 和 PR #55605 也已合并，修复了在 MoA 模式下，代理调用对辅助提供商（auxiliary providers）身份和 `base_url` 的错误识别问题，解决了 MoA 参考模型调用时可能遇到的 400 错误。

- **开发者体验改进：**
    - **文件写入安全优化**：PR #55615 已合并。该补丁区分了 “写入目标超出安全目录” 和 “尝试写入受保护的凭证文件” 两种错误情况，现在会给出更清晰的错误提示，避免用户被误导。

### 4. 社区热点

今日社区讨论热度最高的话题主要集中在技术兼容性与新功能期待上。

1.  **[Issue #44428] 支持 Telegram Bot API 10.1 富消息**
    - **热度**: 9 条评论，7 个 👍
    - **分析**: 这是今日最受社区欢迎的功能请求。用户 `Destinyrrj` 提出希望支持 Telegram 最新引入的富消息格式（如标题、列表、表格等）。这反映了社区对提升聊天 UI 体验的强烈需求，用户期望 Agent 能输出更结构化、更美观的内容。链接：[Issue #44428](https://github.com/NousResearch/hermes-agent/issues/44428)

2.  **[Issue #51587] MCP 服务器工具连接后无法在 Agent 会话中生效**
    - **热度**: 8 条评论
    - **分析**: 这是一个 P1 优先级的 Bug，用户 `itsAlice92` 反应配置 MCP（Model Context Protocol）服务器后，其工具虽然在配置中显示启用，但 Agent 在实际对话中无法调用。这阻碍了社区通过 MCP 扩展 Agent 能力，是影响插件生态健康的关键问题，引起了广泛关注。链接：[Issue #51587](https://github.com/NousResearch/hermes-agent/issues/51587)

3.  **[Issue #33932] OpenAI Codex 提供商因 `'NoneType' object is not iterable` 崩溃**
    - **热度**: 10 条评论
    - **分析**: 尽管已被标记为重复 `duplicate`，但此 Bug 依然获得了最多的评论。用户在使用 OpenAI Codex 提供商（型号：`gpt-5.5`）时，Agent 网关直接崩溃。这表明 Codex 集成路径可能存在不稳定的核心问题，或与新版模型 API 响应结构不兼容。链接：[Issue #33932](https://github.com/NousResearch/hermes-agent/issues/33932)

### 5. Bug 与稳定性

今日报告的 Bug 数量较多，主要集中于提供商兼容性、网关连接以及桌面客户端体验。

**高优先级 (P1):**

| Issue | 描述 | 状态 | 严重性 | Fix PR |
| :--- | :--- | :--- | :--- | :--- |
| [#55546](https://github.com/NousResearch/hermes-agent/issues/55546) | DashScope/Qwen 提供商在 `max_tokens` 超限后无法识别错误信息，导致死循环。 | **已关闭 (CLOSED)** | 严重，导致对话无响应 | 已有，已合入 |
| [#48445](https://github.com/NousResearch/hermes-agent/issues/48445) | Desktop 客户端在长时间任务中 WebSocket 断开，导致前端与后端会话分离。 | **已关闭 (CLOSED)** | 中等，影响桌面用户体验 | 已有 |
| [#27095](https://github.com/NousResearch/hermes-agent/issues/27095) | Cli环境下 `NODE_ENV=production` 导致 Web UI 构建失败 (缺失 `devDependencies`)。 | **开放中 (OPEN)** | 中/高，影响 VPS/CI 部署 | 待定 |
| [#27455](https://github.com/NousResearch/hermes-agent/issues/27455) | Desktop 通过 SSH 隧道连接远程网关时，发送消息报错 `sessions.patch` 未实现。 | **开放中 (OPEN)** | 中等，阻断远程连接使用场景 | 待定 |

**中优先级 (P2):**

| Issue | 描述 | 状态 | Fix PR |
| :--- | :--- | :--- | :--- |
| [#52914](https://github.com/NousResearch/hermes-agent/issues/52914) | QQBot 适配器缺少 `is_reconnect` 参数，导致无限重连循环。 | 开放中 | 待定 |
| [#55551](https://github.com/NousResearch/hermes-agent/issues/55551) | Groq STT 提供商忽略 `language` 参数，非英语音频转录质量差。 | 开放中 | **已有** ([#55608](https://github.com/NousResearch/hermes-agent/pull/55608)) |
| [#55607](https://github.com/NousResearch/hermes-agent/issues/55607) | 安全目录外写入，错误地报告为凭证文件保护，造成用户困惑。 | 开放中 | **已有** ([#55615](https://github.com/NousResearch/hermes-agent/pull/55615)) |

### 6. 功能请求与路线图信号

- **高热度请求**：[Issue #44428](https://github.com/NousResearch/hermes-agent/issues/44428) 提出的 **Telegram 富消息** 支持，获得了 7 个 👍，是当前社区最希望看到的功能。虽然无对应 PR，但大概率会在后续版本中优先考虑。
- **生态集成**：[Issue #47435](https://github.com/NousResearch/hermes-agent/issues/47435) 提议将 Hermes Agent 注册到 ACP（Agent Client Protocol）注册表，以支持与 Zed、JetBrains 等 IDE 的一键集成。这是向更广泛开发者生态迈出的关键一步，未来可期。
- **插件能力增强**：[Issue #23739](https://github.com/NousResearch/hermes-agent/issues/23739) 请求允许 `pre_llm_call` 插件在运行时动态覆盖模型、提供商等配置。这是一个对高级用户和插件开发者非常有吸引力的特性，可能会影响未来插件系统的架构设计。

### 7. 用户反馈摘要

- **满意点**：
    - 社区对 **MoA 架构的修复** 表示期待，因为这直接关系到复杂任务的处理质量。
    - 用户对开发者快速响应并修复 **安全漏洞**（如 IDOR 和文件读取）表示认可，增强了对项目安全性的信心。
    - **消息合并** 功能修复解决了 DeepSeek 用户长期以来的痛点，提升了 Agent 的可用性。

- **不满意/痛点**：
    - **使用门槛高**：新用户（如 `rodboev`）在配置文件和权限方面遇到困惑，如错误提示不明确 (Issue #55607)。
    - **集成不稳定**：OpenAI Codex (Issue #33932)、QQBot (Issue #52914) 等特定商家的集成存在稳定性问题，影响特定用户群体的体验。
    - **功能缺失**：用户明确表示无法从 GUI 创建 WhatsApp 定时任务 (Issue #52445) 以及无法自动触发技能 (Issue #4589) 是不方便的。
    - **语言支持**：非英语用户（如希伯来语）在使用 Groq STT 时体验较差 (Issue #55551)。

### 8. 待处理积压

- **重要请求长期未响应**：
    - **[Issue #4589]**：创建于 4 月 2 日，请求 Agent 能根据用户消息自动触发技能。这个核心的智能交互功能请求至今仍为 “open” 状态，期待维护者给予更多关注和回应。
    - **[Issue #23739]**：创建于 5 月 11 日，请求增强 `pre_llm_call` 插件的能力。

- **长期开放的 PR**：
    - **[PR #21977]**：创建于 5 月 8 日，旨在增加 WhatsApp 的引用回复和状态同步功能。虽然是一个有价值的社区贡献，但目前仍未被合并。
    - **[PR #27908]**：创建于 5 月 18 日，请求添加 Requesty AI 网关作为一级提供商。此 PR 长期未合，可能因为维护者资源有限或需要更多评估。

这些积压项反映了社区对更智能、更易用的 Agent 的期望，值得项目维护团队在后续迭代中优先审视。

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，这是为您生成的 PicoClaw 项目动态日报。

---

# PicoClaw 项目动态日报 | 2026-06-30

## 1. 今日速览

今日项目活跃度较高，主要体现为社区反馈密集和内部修复持续推进。过去24小时内，共有6个 Issue 和7个 PR 更新，显示社区参与度稳定。新版 `nightly` 构建已发布，集成至最新代码。值得注意的是，集中出现了多个关于OAuth登录和模型兼容性的 Bug 报告，可能指向 v0.2.9 版本中的一个回归问题。开发侧，重点在于修复SSRF安全问题、改进提供者认证错误提示，并探索远端代理模式与AW S Bedrock 提示缓存等新功能。

## 2. 版本发布

- **Nightly 构建: v0.3.1-nightly.20260630.52320f48**
  - 这是一个自动化构建版本，可能包含不稳定的新特性。它与 `main` 分支保持同步。
  - **变更日志**: [v0.3.1...main](https://github.com/sipeed/picoclaw/compare/v0.3.1...main)
  - **注意**: 此版本为夜间构建，仅供测试，不建议用于生产环境。

## 3. 项目进展

- **SSRF 安全加固已修复**: PR [#3143](https://github.com/sipeed/picoclaw/pull/3143) `fix(web): block private IPv4 embeds in ISATAP literals` 已被合并。该修复解决了 Issue [#3074](https://github.com/sipeed/picoclaw/issues/3074) 报告的绕过 `web_fetch` SSRF 防护的漏洞，通过增强IP分类器识别嵌入私有/回环 IPv4 地址的 ISATAP IPv6 字面量，提升了系统的安全性。
- **用户友好的认证错误提示**: PR [#3198](https://github.com/sipeed/picoclaw/pull/3198) `fix(providers): surface friendly auth error messages` 已合并。当 API 密钥、Token 或提供者权限失败时，用户将不再收到晦涩的错误信息，而是会得到更清晰的指引，显著改善了用户体验。

## 4. 社区热点

- **[@Damian-o2](https://github.com/Damian-o2) 提出的功能请求**：[#3093](https://github.com/sipeed/picoclaw/issues/3093) I need SimpleX or tox。该 Issue 在创建近20天后依然获得了4条评论，反映了社区对在 PicoClaw 中集成端到端加密通信协议（如 SimpleX、Wire 或 Tox）的强烈兴趣。这表明用户不满足于单一的 OpenAI 接口，希望将 PicoClaw 作为更通用的、去中心化的 AI 交互网关。
- **[@jp39](https://github.com/jp39) 提出的远程 WebSocket 模式**：[#3118](https://github.com/sipeed/picoclaw/pull/3118) Add remote Pico WebSocket mode。此 PR 虽未合并，但获得了持续关注。它提出了通过 WebSocket 远程连接 PicoClaw Agent 的能力，开辟了在硬件受限设备（如 NanoKVM）上分离代理逻辑与用户界面的可能性。这若被合并，将极大扩展 PicoClaw 在边缘计算和嵌入式场景下的部署灵活性。

## 5. Bug 与稳定性

- **严重：OAuth 登录问题**
  - [Issue #3197](https://github.com/sipeed/picoclaw/issues/3197) 和 [Issue #3196](https://github.com/sipeed/picoclaw/issues/3196) 报告了相同的 Bug：在 PicoClaw 0.2.9 版本中，`Codex` 和 `antygravity` 两个提供商的 OAuth 登录功能失效。这是新报告的问题，尚未有修复 PR 或评论。***（推测这可能是一个重要的回归问题）***
- **严重：OpenAI GPT 在 NanoKVM 上无法工作**
  - [Issue #3195](https://github.com/sipeed/picoclaw/issues/3195) 报告在使用 NanoKVM 2.4.0 内置的 PicoClaw 功能时，即使按文档配置，也无法通过默认配置使用 `gpt-5.4` 模型。这可能是兼容性问题或文档与实际情况不符。
- **中：火山引擎豆包模型工具调用异常**
  - [Issue #3153](https://github.com/sipeed/picoclaw/issues/3153) 报告当使用 `doubao-seed-2.0-pro` 模型时，工具调用偶尔会失败，并以原始文本 `<seed:tool_call>` 的形式泄露给用户。这可能影响依赖该模型进行自动化任务的用户。

## 6. 功能请求与路线图信号

- **新的网关/协议支持**：[#3093](https://github.com/sipeed/picoclaw/issues/3093) 提出的 SimpleX/Tox 支持，以及已有的 PR [#3063](https://github.com/sipeed/picoclaw/pull/3063) `feat: add deltachat gateway`，共同指向了一个方向：用户希望 PicoClaw 成为一个连接 AI 与多种去中心化、安全的通信网络的“万能接口”。这是一个重要的路线图信号。
- **AWS Bedrock 提示缓存**：PR [#3163](https://github.com/sipeed/picoclaw/pull/3163) `feat(bedrock): leverage Converse prompt caching` 正在推动在 Bedrock 集成中利用提示缓存以降低成本并提升响应速度。这显示项目正在积极优化云服务的集成体验。
- **更细粒度的 Token 用量追踪**：PR [#3156](https://github.com/sipeed/picoclaw/pull/3156) `feat(pico): emit per-turn LLM token usage` 旨在通过 Pico 通道上报每次对话的 Token 消耗，这为开发者构建用量监控、成本分摊等功能提供了数据基础。

## 7. 用户反馈摘要

- **痛点**：用户 `[@ms8great](https://github.com/ms8great)` 在 Issue [#3153](https://github.com/sipeed/picoclaw/issues/3153) 中详细描述了火山引擎模型工具调用偶尔失败，导致原始文本泄露的问题，影响了实际使用体验。
- **使用场景**：用户 `[@rtadams89](https://github.com/rtadams89)` 在 Issue [#3195](https://github.com/sipeed/picoclaw/issues/3195) 中描述了在 NanoKVM 上使用 PicoClaw 的场景，这是 PicoClaw 作为 KVM 设备 AI 助手功能的新兴用例，但遇到了兼容性问题。
- **满意/不满意**：PR [#3198](https://github.com/sipeed/picoclaw/pull/3198) 的合并是对用户之前遇到认证错误时无从下手的一次积极回应，这将提升新用户的首次体验。然而，v0.2.9 版本出现的新 OAuth 错误（Issue [#3197](https://github.com/sipeed/picoclaw/issues/3197)）可能会降低用户对版本稳定性的满意度。

## 8. 待处理积压

- **长期未合并的 PR**：
  - [#3063](https://github.com/sipeed/picoclaw/pull/3063) `feat: add deltachat gateway`：创建于6月8日，距今已超过三周。该功能需求与社区热点 Issue [#3093](https://github.com/sipeed/picoclaw/issues/3093) 高度相关，建议维护者评估并推进。
  - [#3118](https://github.com/sipeed/picoclaw/pull/3118) `Add remote Pico WebSocket mode`：也是一个重要的架构改进，创建超过两周。它能够解决 Issue [#3195](https://github.com/sipeed/picoclaw/issues/3195) 中提到的部分设备兼容性问题（通过分离 Agent 运行）。
- **未解决的 Bug**：
  - [#3153](https://github.com/sipeed/picoclaw/issues/3153) `Volcengine Doubao Seed tool calls leak`：此问题已存在一周，会影响火山引擎用户的使用，建议尽快分配修复。
  - [#3197](https://github.com/sipeed/picoclaw/issues/3197) 及 [#3196](https://github.com/sipeed/picoclaw/issues/3196) `OAuth 登录问题`：最新报告的 Bug，似乎为回归问题，需优先级处理。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，这是根据您提供的 GitHub 数据生成的 NanoClaw 项目动态日报。

---

# NanoClaw 项目动态日报 (2026-06-30)

**项目名称:** NanoClaw
**数据日期:** 2026-06-30
**分析师:** AI 开源项目分析师

---

### 1. 今日速览

今日 NanoClaw 项目活跃度较高，尤其在 Pull Request 方面表现突出，共有 6 个新提交等待合并。社区关注点集中在 **渠道适配** (Discord, Slack, WeChat) 和 **开发者体验** (Agent 模板) 上。虽然有一个关于 Discord 附件处理的 Bug (#2888) 被报告，但社区已迅速提交了对应的功能修复 PR (#2884)。项目整体处于功能快速迭代与扩展阶段，社区贡献活跃。

---

### 2. 版本发布

**无**

今日无新版本发布。

---

### 3. 项目进展

今日共有 1 个重要修复被合并，另有 2 个新增功能等待合入，项目在**平台集成**和**开发者效率**方面取得了实质性进展：

- **已合并/关闭的 PR:**
    - **`#2886`:** 修复了单提供商安装时，新渠道注册代理可能因继承默认提供商 (Claude) 而导致 **401 认证失败**的问题。这是一个关键的稳定性修复，确保了使用单一 AI 提供商配置的用户在连接新渠道时不会出错。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2886)

- **关键待合并 PR:**
    - **`#2884`:** **新增了 Discord 渠道适配器**，并修复了 Gateway 模式下批准按钮路由错误。该 PR 直接回应了社区对 Discord 支持的核心需求。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2884)
    - **`#2890`:** 引入了 **Agent 模板**概念，允许用户从预置的指令、MCP 工具和技能包中快速创建和部署 Agent。这将显著降低新用户的入门门槛，并促进最佳实践的分享。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2890)

---

### 4. 社区热点

- **热门 PR: `#2889` - feat: daily-news-agent for Andy group + WeChat channel**
    - **作者:** wangzx5521-wq
    - **热度分析:** 该 PR 包罗万象，不仅新增了一个实用的 `daily-news-agent`，还带来了 **WeChat 渠道适配器**，并配套了 33 个 Vitest 单元测试，展现了极高的贡献质量。这表明社区不仅在使用项目，还在利用其框架构建完整的、可复用的解决方案。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2889)

- **热门 Issue: `#2888` - Discord (and likely other url-only chat-sdk adapters) drop image/file attachments**
    - **作者:** eagansilverpathmarketing
    - **热度分析:** 该 Issue 精确地定位了 Discord 渠道中附件无法被 Agent 读取的问题，并给出了根因分析（`messageToInbound` 函数未下载附件）。该问题精准地指出了 Chat SDK 桥接模式的通用缺陷，社区迅速呼应，并已在 `#2884` PR 中提供了修复方案。[[链接]](https://github.com/nanocoai/nanoclaw/issues/2888)

---

### 5. Bug 与稳定性

| 严重程度 | Bug 描述 | 是否已有 fix PR | 链接 |
| :--- | :--- | :--- | :--- |
| **高** | **Discord 渠道中，Agent 无法接收图片/文件附件**，仅能看到元信息。这会完全破坏基于图像或文件输入的多模态 Agent 功能。 | 是 (PR `#2884`) | [Issue #2888](https://github.com/nanocoai/nanoclaw/issues/2888) |
| **高** | **安全漏洞：符号链接逃逸。** 攻击者可通过在 Agent 容器内放置符号链接，诱导 Host 写入任意文件 (CWE-59)。影响到所有启用了 Attach-write 的渠道。 | 是 (PR `#2880`, 待合并) | [PR #2880](https://github.com/nanocoai/nanoclaw/pull/2880) |
| **中** | **单提供商安装时，新渠道注册代理失败 (401)。** 影响使用单一 API Key 的用户添加新渠道。 | 已解决 (PR `#2886` 已合并) | [PR #2886](https://github.com/nanocoai/nanoclaw/pull/2886) |
| **低** | **引导流程缺少 Slack Socket 模式选项。** 虽功能已开发，但未被整合到主分支的交互式设置流程中，导致用户体验割裂。 | 是 (PR `#2885`, 待合并) | [PR #2885](https://github.com/nanocoai/nanoclaw/pull/2885) |

---

### 6. 功能请求与路线图信号

- **渠道扩展 (强信号):**
    - **Discord 渠道:** Issue `#2888` 暴露了问题，而 PR `#2884` 是直接的解决方案，表明 Discord 支持是社区的刚需，很可能在下一个版本中上线。
    - **WeChat 渠道:** PR `#2889` 提交了完整的 WeChat 适配器，进一步丰富了非 Telegram、Slack 渠道生态。
    - **Slack Socket 模式:** PR `#2885` 请求将 Socket 模式集成到安装引导中，体现了社区对高级 Slack 功能的期望。

- **开发者体验增强 (强信号):**
    - **Agent 模板系统:** PR `#2890` 提出的模板化加载方案，是提升 Agent 复用性和降低开发门槛的重要尝试，有望成为下一个版本的核心特性之一。

- **自动化与实用 Agent (中等信号):**
    - **每日新闻 Agent:** PR `#2889` 中的 `daily-news-agent` 案例展示了用户利用 NanoClaw 框架构建自动化工作流的潜力，可能激发更多类似功能的社区贡献。

---

### 7. 用户反馈摘要

- **主要痛点:** **渠道兼容性问题**是当前用户最直接的痛点。特别是 Discord 渠道，用户期望 Agent 能像在 Telegram 中一样正常处理图片和文件附件，目前的缺陷严重影响了用户体验。
- **积极反馈:** 虽然 Issue `#2888` 是负面反馈，但社区积极贡献修复代码，并提供了详细的根因分析，侧面反映了项目社区的专业和活跃。
- **新用例:** PR `#2889` 的贡献者展示了如何构建一个集成 RSS 抓取、LLM 摘要和定时触发的 Agent，这表明用户正在将 NanoClaw 用于**信息聚合与自动化报告生成**等更复杂的场景。

---

### 8. 待处理积压

- **安全修复 PR (已延迟 2 天):**
    - **`#2880`:** 针对 **符号链接逃逸** (CWE-59) 的安全修复。该 PR 于 `2026-06-28` 创建，至今尚未合并。鉴于其严重性（任意文件写入），建议维护者优先处理。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2880)

- **Slack 功能对齐 PR (已延迟 1 天):**
    - **`#2885`:** 请求将 **Slack Socket 模式** 合并入主分支。该功能是对早前开发的未完成集成，建议尽快合并，以确保主分支体验与开发功能保持一致。[[链接]](https://github.com/nanocoai/nanoclaw/pull/2885)

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

# NullClaw 项目日报 (2026-06-30)

## 1. 今日速览
项目今日活跃度中等偏上，主要由 **Pull Request 活动** 驱动（4 条 PR，其中 1 条已合并/关闭）。社区提交了一个重要的 **Bug Issue**（Telegram channel 空闲后无响应），但尚无评论或修复 PR。值得注意的是，编号 #783 的“Cron 子代理”大型功能 PR 在搁置近 3 个月后于今日获得更新，显示该功能可能接近合并。整体看，项目处于 **功能开发与稳定性修复并行** 的健康状态，但社区对特定 Bug 的响应需求较急迫。

## 2. 版本发布
无

## 3. 项目进展
- **#960 [CLOSED] fix(cli): handle arrow keys in agent REPL** (@vernonstinebaker，6月17日-6月29日)  
  **状态**: 已合并/关闭  
  **意义**: 该 PR 为 `nullclaw agent` 的交互式 REPL 添加了小型的零分配行编辑器，支持方向键历史导航、光标移动、Home/End 等快捷键。此前用户使用方向键会输出控制字符，影响交互体验。  
  **影响**: 直接提升了 CLI 用户的操作流畅度，是命令行工具的显著体验优化。  
  [PR #960](https://github.com/nullclaw/nullclaw/pull/960)

- **#783 [OPEN] feat(cron): cron subagent, run history, JSON output, security hardening** (@yanggf8，4月7日-6月30日)  
  **状态**: 待合并（今日更新）  
  **意义**: 该 PR 引入了一套完整的 Cron 子代理引擎，包括 DB 驱动的调度器、运行历史记录表、任务队列机制、多种任务类型支持（skill/agent/shell），以及 JSON 输出和安全加固。**今日更新显示维护者仍在 review 或进行最终调整，可能在近期合并。**  
  **影响**: 一旦合并，将极大扩展 `nullclaw` 的任务调度能力，使其成为一个更全面的自动化平台。  
  [PR #783](https://github.com/nullclaw/nullclaw/pull/783)

## 4. 社区热点
**今日唯一 Issue #972 成为关注焦点**
- **#972 [OPEN] [bug] telegram channel stop respond after some idle time** (@i11010520)  
  **链接**: [Issue #972](https://github.com/nullclaw/nullclaw/issues/972)  
  **分析**: 用户报告 Telegram channel 在空闲一夜后停止响应，尽管后端 `nullclaw agent` 运行正常。目前 **0 评论、0 点赞**，但问题描述清晰，包含后端日志证明系统仍在工作。该问题可能影响所有使用 Telegram 集成的长时间运行部署，属于 **中等严重性** 的功能性 Bug，尤其对于希望 7x24 运行的用户是一个阻碍。  
  **建议**: 维护者应尽快确认是否可复现，并提醒用户检查 Telegram Webhook 或长轮询超时配置。

## 5. Bug 与稳定性
| 严重程度 | Issue/PR | 描述 | 是否有 Fix PR |
|----------|----------|------|---------------|
| **中等** | [#972](https://github.com/nullclaw/nullclaw/issues/972) | Telegram Channel 空闲一夜后停止响应，后端正常。疑似连接超时或心跳丢失。 | 无 |
| **低** | [PR #970](https://github.com/nullclaw/nullclaw/pull/970) | （对应已关闭的 #960）REPL 中方向键处理修复，已合并。 | 已修复 ✅ |

## 6. 功能请求与路线图信号
- **Streaming 原生工具调用** [PR #971](https://github.com/nullclaw/nullclaw/pull/971) (@vernonstinebaker)  
  意图将原生工具调用与 SSE 流式响应解耦，使得支持原生工具的模型在流式输出时能够正常调用工具。这是 **流式交互体验的关键优化**，若能合并，将提升与 GPT-4o、Claude 等模型的兼容性。  
  判断：**高概率纳入下一版本**，因为该 PR 已获创建者 2 天，且与方向键 PR 出自同一贡献者，显示作者正在系统性地优化代理交互层。

- **Cron 子代理** [PR #783](https://github.com/nullclaw/nullclaw/pull/783)  
  如上所述，是当前最大的功能推进。若合并，将标志着 `nullclaw` 从“聊天机器人”向“自动化代理平台”的转型。

## 7. 用户反馈摘要
- **👍 Telegram 用户真实痛点**: i11010520 明确表示“Channel dies after idle”，而后台 `nullclaw agent` 仍能 `ping` 成功。这表明问题可能出在 **Telegram 长连接/Webhook 超时机制** 而非 Agent 核心。用户期望“无人值守一夜后仍可响应”，是典型的 **无人值守机器人** 使用场景。
- **📝 CLI 体验提升**: 结合 #960/#970 的合并，说明有多位用户对 REPL 交互感到不满（方向键输出乱码），社区主动贡献了修复。这暗示 **NullClaw 的 CLI 用户基数在增长**，且使用场景正向“深度交互式操作”转变。

## 8. 待处理积压
| 类别 | 条目 | 创建时间 | 最后更新 | 备注 |
|------|------|----------|----------|------|
| **Open Bug** | [#972](https://github.com/nullclaw/nullclaw/issues/972) | 2026-06-30 | 2026-06-30 | 尚无回复，需维护者尽快处理 |
| **Stalled Feature PR** | [#783](https://github.com/nullclaw/nullclaw/pull/783) (`feat(cron)`) | 2026-04-07 | 2026-06-30 | 虽然今日更新，但已在 review 近 3 个月，建议加速合并决策 |
| **Open PR (功能性)** | [#971](https://github.com/nullclaw/nullclaw/pull/971) (Streaming tools) | 2026-06-29 | 2026-06-29 | 2 天无更新，但内容较完整，建议本周内启动 review |

---

**整体项目健康度评估**: 🟢 **良好**。虽有 Bug 报告，但修复力度（PR 合并）与开发节奏（大型功能更新）保持平衡。需重点关注 Telegram 连接的稳定性问题及 #783 Cron PR 的合并时机。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，这是根据您提供的 IronClaw 项目数据生成的 2026-06-30 项目动态日报。

---

# IronClaw 项目日报 - 2026-06-30

## 1. 今日速览

今日项目活跃度较高，共处理 16 个 Issue 和 50 个 PR，社区讨论热烈。核心进展集中在 **Reborn WebUI 的测试覆盖和质量保障** 上，大量 PR 和 Issue 围绕 E2E 测试、QA 框架改进和测试结果分析展开。同时，**自动化任务通知功能** 已进入代码实现阶段，是今日最受关注的功能性进展。但项目也暴露出一些严重的 **多租户配置与状态管理 Bug**，例如通知路由全局化和工作流协议冲突，这些问题可能会影响用户核心体验，需要优先关注。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

今日项目主要精力放在巩固和优化 Reborn 版本的测试基础设施与 WebUI 功能上。以下是今日合并的重要 PR：

- **测试与 CI 基础设施加固**:
    - [#5442 - ci: use canonical Reborn live QA harness for PR canaries](https://github.com/nearai/ironclaw/pull/5442) 重构了 CI 流程，确保 PR 的冒烟测试使用标准化的 QA 工具集，避免了因测试脚本版本不一致导致的误报，提升了 CI 的可靠性。
    - [#5424 - Link failed Reborn QA cases to artifacts](https://github.com/nearai/ironclaw/pull/5424) 在失败报告中增加了失败用例的详细调试工件链接，极大地方便了开发人员定位和分析测试失败原因。
    - [#5313 - tools: add storage stress harness](https://github.com/nearai/ironclaw/pull/5313) 新增了一个针对存储后端的压力测试工具，为后续优化系统在高负载下的稳定性提供了数据支持。

- **WebUI 功能与修复**:
    - [#5375, #5374, #5373] 核心贡献者 `ilblackdragon` 合并了一系列 PR，将 Reborn WebUI 的**项目设置、扩展管理、频道配对**等关键流程的浏览器测试覆盖从旧平台迁移至新平台，确保了这些功能的稳定性和可回归性。
    - [#5395 - Fix Web Access Exa content fetch](https://github.com/nearai/ironclaw/pull/5395) 修复了 Web 搜索中通过 Exa 获取内容失败的问题，并优化了网络权限，确保零配置体验部分功能正常运行。

**项目向前迈进总结**: 今日项目的主要推进在于 **“运维与测试工程化”** 。通过标准化 QA、增强诊断信息和压力测试，项目正在系统性提升 Reborn 版本的交付质量和长期可维护性。虽然功能上无重大更新，但基础架构的稳固为后续快速迭代扫清了障碍。

## 4. 社区热点

今日讨论最热烈的 Issue 是 **#5420**，关于自动化任务通知路由的全局化问题。

- **#5420 [bug, scope: channel/web] Routine delivery target is a global per-user default, not per-routine** ([链接](https://github.com/nearai/ironclaw/issues/5420))
    - **背景**: 用户发现，为一个自动化任务（Routine）设置 Slack 通知后，账户下所有其他自动化任务（如邮件摘要）的交付目的地也会被同步修改为 Slack。这与用户期望的“每个任务独立配置”行为严重不符。
    - **诉求分析**: 该 Issue 揭示了当前系统在状态管理和配置隔离上的设计缺陷。社区用户的核心诉求是**配置的粒度和可预测性**。他们希望在创建一个自动化任务时，所有的设置（尤其是关键的通知路由）都只作用于该任务本身，不产生全局副作用。这种行为不仅导致功能异常，还可能造成用户信息泄露或不必要的噪声。

## 5. Bug 与稳定性

今日报告的 Bug 较多且严重，部分问题已有对应修复 PR 或正在解决中。

| 严重程度 | Issue | 描述 | 状态 |
| :--- | :--- | :--- | :--- |
| **P1 (最高)** | [#5415](https://github.com/nearai/ironclaw/issues/5415) | **多工具工作流（Google Sheets）协议违规**：执行较长的工具调用链（18-25步）时，系统一致性报错 | 未解决 |
| **P1 (最高)** | [#5437](https://github.com/nearai/ironclaw/issues/5437) | **基准测试大规模失败**：`pinchbench` 有146个用例因模型 HTTP 400 错误而全部失败 | 正在定位 |
| **P2** | [#5420](https://github.com/nearai/ironclaw/issues/5420) | **通知路由全局化**：配置一个自动化任务的通知，会修改所有任务的通知设定 | 未解决 |
| **P2** | [#5417](https://github.com/nearai/ironclaw/issues/5417) | **技能选择错误**：搜索 Hacker News 时激活了错误的“tech-debt-tracker”技能 | 未解决 |
| **P2** | [#5416](https://github.com/nearai/ironclaw/issues/5416) | **状态矛盾**：应用连接 Gmail 时，系统状态混乱，告知用户连接成功后又要求认证 | 未解决 |
| **P3** | [#5418](https://github.com/nearai/ironclaw/issues/5418) | **消息顺序错乱**：工具调用后，Agent 回复消息显示位置错误 | 未解决 |
| **P3** | [#5419](https://github.com/nearai/ironclaw/issues/5419) | **缺少重命名功能**：用户无法修改自动化任务的名称 | 未解决 |
| - | [#5421](https://github.com/nearai/ironclaw/issues/5421) | **Web搜索非零配置**：即使Chat功能正常，Web搜索仍需用户手动输入NEAR AI API Key | 未解决 |
| - | [#5429](https://github.com/nearai/ironclaw/issues/5429) | **Web搜索需要API Token**：类似#5421，强调生产环境下的配置问题 | 未解决 |
| - | [#5426](https://github.com/nearai/ironclaw/issues/5426) | **无法创建自动化任务**：报错“系统驱动器不可用” | 未解决 |
| - | [#5428](https://github.com/nearai/ironclaw/issues/5428) | **MCP测试层代码缺陷**：重构时发现的测试代码错误，已分离出来追踪 | 未解决 |
| - | [#5413](https://github.com/nearai/ironclaw/issues/5413) | **OAuth刷新静默失败**：Token刷新失败时不报错，难以排查问题 | **已关闭** |

**补充说明**:
- **#5415** 标记为 P1，因为它涉及到核心的功能完整性，多次工具调用失败将导致用户无法完成复杂任务。
- **#5437** 标记为 P1，因为基准测试的大规模失败直接反映了系统与特定模型后端（DeepSeek）的兼容性问题。
- **#5413** 虽然是已关闭的 Issue，但其修复方 PR 很可能已包含在项目中。该问题的严重性在于“静默失败”，它会掩盖底层错误，增加调试难度，是软件稳定性的常见隐患。

## 6. 功能请求与路线图信号

今日最值得关注的功能请求是 **#5443**，并且已有对应的实现 PR。

- **#5443 [Feature]: Add header notifications for newly triggered automation tasks** ([链接](https://github.com/nearai/ironclaw/issues/5443))
    - **请求**: 为自动化任务的触发结果添加一个明确的头部通知入口（如小铃铛图标），而不是让用户被动地在侧边栏或Automations页面发现。
    - **对应PR**: [#5441 - feat(webui): add header notifications for automation runs](https://github.com/nearai/ironclaw/pull/5441)
    - **路线图信号**: 该功能从 Issue 提出到 PR 合并几乎是同步进行的，这强烈表明 **提升自动化任务的可发现性和用户感知**是 Reborn 版本的核心优化方向之一。这有望在下一个版本中落地，显著改善用户体验。

此外，Issue #5420 中关于**通知路由配置隔离**的需求虽然是一个 Bug，但背后也隐含着对“配置专业化”和“可预测性”的强烈诉求。项目团队在修复此 Bug 时，需要将这个问题视为一个设计原则来考虑。

## 7. 用户反馈摘要

从今日的 Issues 评论中，可以提炼出以下真实用户痛点：

- **“我的配置被污染了”**: 用户在 #5420 中反映，设定一个例行任务的通知，导致所有任务的通知都被重定向。这是一个典型的“副作用”问题，用户操作一个功能，却意外影响全局，极易引发信任危机。
- **“你在逗我吗？”**: 用户在 #5416 中描述了一个矛盾的使用体验：“请连接Gmail”，系统回复“已经连接”，当用户质疑时，系统又改口说“只是安装了但没激活”。这种前后矛盾的反馈让用户感到困惑和沮丧。
- **“我无法选择，无法整理”**: 用户在 #5419 中抱怨无法重命名自动化任务，系统自动生成的任务名称过长、含义不清。这表明用户希望对他们的工作区有更多**控制权**和**个性化定制**的能力。
- **“它失败了，但我不知道为什么”**: #5415 中的“协议冲突”错误，#5437 中的HTTP 400错误，#5413 中的静默失败，都指向一个共同痛点：**错误信息对用户不友好**。用户期望得到更具体、可操作的错误提示，而不是一个模糊的符号或状态码。

## 8. 待处理积压

以下为长期未响应或可能被忽视的 Issue/PR，建议维护者关注：

- **#4108 [OPEN] Nightly E2E failed** ([链接](https://github.com/nearai/ironclaw/issues/4108))
    - **重要性**: 高。该 Issue 从 2026-05-27 起持续更新，指出Nightly E2E测试持续失败。虽然昨日有更新，但 Issue 仍处于 Open 状态。如果这是一个常态化失败，它将严重削弱 CI/CD 管道的信心，并可能掩盖真正的回归问题。
    - **建议**: 强烈建议项目组对 Nightly E2E 的失败根因进行系统性分析，并将其修复或降级为 `flaky`。

- **#4841 [OPEN] reborn: no run-borking failures — failure explanation + retryable failed runs** ([链接](https://github.com/nearai/ironclaw/pull/4841))
    - **重要性**: 高。这是一个旨在提升系统稳定性和错误恢复能力的大 PR，从 2026-06-13 开始至今仍在 Open 状态。其目标（消除致命性运行错误，提供可重试机制）与用户反馈中指出的“错误信息模糊”和“系统脆弱”问题高度相关。
    - **建议**: 作为提升系统健壮性的关键改进，该项目应被优先评估和合并，以系统性解决多个用户痛点。

- **#5440 [OPEN] test(reborn): PR-E1 seam constructors for integration coverage** ([链接](https://github.com/nearai/ironclaw/pull/5440))
    - **重要性**: 中。此 PR 是为了解锁后续集成测试的框架基础 PR。虽然它本身是技术债务的清理，但如果长期搁置，会阻碍后续所有需要此框架的测试开发。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

好的，我是 LobsterAI 项目的 AI 智能体与个人 AI 助手领域开源项目分析师。根据您提供的 2026-06-30 的 GitHub 数据，现为您生成以下项目动态日报。

---

# LobsterAI 项目动态日报 | 2026年6月30日

## 1. 今日速览

今日项目活跃度**高**。过去24小时处理了12条 Issue 和16个 PR，并发布了新版本 `2026.6.29`。核心开发团队主要集中在 `cowork` 模块的稳定性修复和 UI 优化上，同时对 `openclaw` 引擎进行了关键性的后台任务执行逻辑修复。社区反馈活跃，部分历史遗留的 `[stale]` 标签 Issue 在今日获得了社区和官方的关注。整体而言，项目处于积极的开发迭代与社区共建阶段。

## 2. 版本发布

- **[版本]**：`LobsterAI 2026.6.29`
- **[发布说明摘要]**：
  - `fix(openclaw)`: 通过权限路由插件批准。
  - `fix(cowork)`: 清理导航栏预览。
- **[分析]**：本次发布主要聚焦于 `openclaw` 和 `cowork` 两个核心功能区的 Bug 修复。具体修复细节可查看合并到该版本的 PR，它解决了插件审批流程和用户界面预览体验的问题。建议用户升级以获得更好的稳定性。
- **[链接]**：[查看发布详情](https://github.com/netease-youdao/LobsterAI/releases/tag/2026.6.29)

## 3. 项目进展

今日官方共合并/关闭了13个 PR，推进了以下关键领域的进展：

- **核心引擎稳定性 (openclaw)**：
    - **[PR #2234 (进行中)]**：修复了 `cron` 定时任务中子 agent（代理）完成后无法驱动父 agent 继续执行的重大问题，覆盖了多种并发执行场景。这是对 `openclaw` 编排能力的重要增强。
    - **[PR #2231 (已合并)]**：修复了 `openclaw` 网关客户端初始化时机问题，确保了定时任务列表和运行历史在应用启动时能正确加载，解决了“空状态”的假死问题。
    - **[PR #2232 (已合并)]**：为 Anthropic 格式的 OpenClaw 提供商添加了内置的最大 Token 数 fallback 机制，增强了网络或配置异常时的健壮性。
    - **链接**: [PR #2234](https://github.com/netease-youdao/LobsterAI/pull/2234), [PR #2231](https://github.com/netease-youdao/LobsterAI/pull/2231), [PR #2232](https://github.com/netease-youdao/LobsterAI/pull/2232)

- **协作会话界面与导航 (cowork)**：
    - **[PR #2235 (已合并)]**：修复了调整 artifacts（工件）面板大小时，prompt 工具栏被压缩覆盖的问题。**链接**: [PR #2235](https://github.com/netease-youdao/LobsterAI/pull/2235)
    - **[PR #2218 及关联 PR #2222-#2226 (已合并)]**：团队对 `conversation rail`（对话轨道）进行了“回退 -> 重新应用”的操作，最终将修复整合进 `release/2026.6.29` 和 `main` 分支，确保了导航栏预览、悬停样式和懒加载功能的正确性。
    - **[PR #2229 (已合并)]**：新增了 Cowork 和 OpenClaw 流程的诊断日志，有助于未来排查生产环境问题。**链接**: [PR #2229](https://github.com/netease-youdao/LobsterAI/pull/2229)

- **分析与隐私**：
    - **[PR #2233 (已合并)]**：从提示词事件分析中移除了意图类型、子类型等字段，以保护用户输入语义的隐私。这是一个值得注意的、对用户隐私友好的改进。**链接**: [PR #2233](https://github.com/netease-youdao/LobsterAI/pull/2233)

- **里程碑回顾**：
    - **发布分支合并**：[PR #2228](https://github.com/netease-youdao/LobsterAI/pull/2228) 将 `release/2026.6.29` 合并到 `main`，标志着该版本功能全部就绪。

## 4. 社区热点

今日社区讨论热度最高的议题集中在**性能与 Token 消耗**上，引发了开发者的强烈共鸣。

- **热点 Issue**: **[#2230] 同一个模型在 LobsterAI 比 CodeBuddy 慢很多**（作者: woxinsj）
    - **分析**: 此 Issue 是今天的新建问题，但迅速成为社区焦点。用户提供了非常详尽的对比数据：同样的模型和提示词，CodeBuddy 耗时2分24秒、消耗 67,610 Token，而 LobsterAI 耗时25分钟、消耗高达 **60M Token**。这揭示了存在严重的性能瓶颈或 Token 浪费问题，直接影响了用户的核心体验和成本。背后是用户对AI Agent 运行效率的极度关切。
    - **链接**: [Issue #2230](https://github.com/netease-youdao/LobsterAI/issues/2230)

- **活跃讨论 Issue**: **[#2121] 对一个现象的疑问（怀疑是bug）**（作者: nbjoe）
    - **分析**: 该 Issue 与 #2230 反映的问题同源，用户观察到会话中存在重复输出文字的现象，并质疑这是否是“吃掉 Token”的元凶。这表明用户社区已经开始集体反馈和探讨性能与 Token 消耗问题，形成了明确的痛点共识。
    - **链接**: [Issue #2121](https://github.com/netease-youdao/LobsterAI/issues/2121)

## 5. Bug 与稳定性

- **【严重】** **性能与Token消耗问题** ([#2230](https://github.com/netease-youdao/LobsterAI/issues/2230))
    - **描述**: 特定模型（DBX）下，LobsterAI 处理任务的耗时和Token消耗断崖式高于同类工具 CodeBuddy。
    - **状态**: **未修复**。这是今日报告的最严重 Bug，可能根植于 Agent 的执行逻辑或内部架构。

- **【中等】** **执行结果窗口滚动假死** ([#2079](https://github.com/netease-youdao/LobsterAI/issues/2079))
    - **描述**: 在最新版本中，执行结果窗口滚动到顶端时会假死，现象可复现。
    - **状态**: **未修复**。已存在超过一个月，需确认是否已在新的渲染优化中解决。

- **【低】** **同模型响应速度慢** ([#2230](https://github.com/netease-youdao/LobsterAI/issues/2230))
    - **描述**: 用户抱怨“同一个模型在 LobsterAI 比 CodeBuddy 慢很多”。
    - **状态**: 未修复，但与性能Bug直接关联。

- **【修复】** **定时任务列表加载为空** ([PR #2231](https://github.com/netease-youdao/LobsterAI/pull/2231))
    - **描述**: 启动时定时任务历史记录显示为空。
    - **状态**: **已修复**。

- **【修复】** **Chat Rail UI 回退** ([PR #2226](https://github.com/netease-youdao/LobsterAI/pull/2226))
    - **描述**: 对话轨道导航功能因代码合并错误被意外移除。
    - **状态**: **已修复**。

## 6. 功能请求与路线图信号

- **【高潜力】** **使用体验与运行效率**：
    - **Issue #2120**: 用户建议借鉴 Workbuddy 实现任务预输入，提升任务运行连续性；并希望延长单次任务运行时长，避免脚本监控中途终止。
    - **Issue #1381**: 建议定时任务不要新开会话窗口，而是持续在同一个会话内呈现结果。
    - **分析**: 结合今日已合并的 `cron` 相关 PR ([#2234](https://github.com/netease-youdao/LobsterAI/pull/2234))，项目组已经在改进任务编排。这些Issue表明， **“任务执行连续性”和“运行时长”** 是下一版本需要重点优化的方向。

- **【中等潜力】** **新 Agent 支持**：
    - **Issue #2131**: 用户询问是否计划支持 `hermes agent`。
    - **分析**: 当前无关联PR，但作为开源项目，扩展 Agent 支持是保持竞争力的关键。

- **【低潜力】** **UI/UX 优化**：
    - **Issue #2120 第3点**: 用户建议在全屏模式下，技能展示界面从双列改为三列，以获得更好的视觉效果。这是一个相对简单的 UI 调整。

## 7. 用户反馈摘要

- **满意点**：社区对 `openclaw` 引擎的改进表现出认可，特别是对定时任务修复和子Agent逻辑的增强表示期待。
- **主要痛点**：
    - **Token浪费与性能焦虑**：`#2121` 和 `#2230` 的创建者和评论者共同表达了因重复输出或未知原因导致的 Token 大量消耗和响应速度慢的强烈不满，这直接关系到用户的使用成本和信心。
    - **功能易用性欠缺**：`#1381` 和 `#2120` 反映了用户希望任务管理更灵活、连续，而当前设计（新开会话、任务时长限制）增加了操作负担。
    - **Bug 反复**：`#2079` 的长期存在和对话轨道的回退合并问题（`#2224`），让部分用户对版本稳定性产生疑虑。

## 8. 待处理积压

- **重要且长期未关闭**：
    - **[Issue #1382] 导出日志-红色提示建议**（2026-04-03）：已经3个月未获得开发团队回应。涉及 UI 设计友好性，虽不致命，但仍建议社区维护者或核心成员予以回应。
    - **[Issue #1383] 微信机器人-重复提问只同步一个**：Wx Bot 的一个功能性Bug，影响特定用户群的使用体验。

- **重要但已标记**：
    - **[Issue #2079] 执行结果窗口滚动假死**（2026-05-30）：已存在一个月，用户可复现。虽未在今日更新中提及，但与 PR [#2235](https://github.com/netease-youdao/LobsterAI/pull/2235) 的UI渲染区域修复有关联，建议优先排查。
    - **[PR #1372] 修复会话中多文件选择只保留最后一个文件**（2026-04-02）：一个等待合并的“Stale” PR，解决了社区已报告的Bug，其本身已通过单元测试，不应持续搁置。

---
*报告完毕*

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于 CoPaw (github.com/agentscope-ai/CoPaw) 项目数据生成的 2026-06-30 项目动态日报。

---

# CoPaw 项目动态日报 | 2026-06-30

## 1. 今日速览

今日项目活跃度极高，总计处理了 **75 项** Issues 与 PR 动态。核心看点集中在 **大量 Bug 修复的收尾工作** 以及 **针对 v2.0.0 版本的功能增强**。社区贡献者（First-time contributors）活跃，提交了多项关键功能的 PR。没有新版本发布，但多个待合并 PR 和积压问题显示项目正处于从快速迭代向稳定发布过渡的关键阶段。

- **活跃度评估：** **非常高**。Bug 修复与功能开发齐头并进，社区参与度高，但大规模 PR 和 Issue 的合并/解决压力较大。

## 2. 版本发布

**无新版本发布。**

## 3. 项目进展

今日有 **23 个 PR 被合并/关闭**，推动了多个关键领域的进展：

- **钉钉（DingTalk）通道体验优化：**
    - PR [#5590](https://github.com/agentscope-ai/QwenPaw/pull/5590) 已合并，为 `channels send` 和 API 添加了 `@mention` 支持，解决了多 Agent 协作场景下的关键需求。
    - PR [#5654](https://github.com/agentscope-ai/QwenPaw/pull/5654) 已合并，修复了钉钉主动/定时消息的静默发送失败问题，提升了通道可靠性。
- **前端与用户体验修复：**
    - PR [#5664](https://github.com/agentscope-ai/QwenPaw/pull/5664) 已合并，增加了非拥有者标签页的提示 Banner，明确了多标签页发送机制，提升了交互清晰度。
    - PR [#5656](https://github.com/agentscope-ai/QwenPaw/pull/5656) 已合并，修复了侧边栏会话列表在不同模式下的滚动问题。
- **技能管理优化：**
    - PR [#5639](https://github.com/agentscope-ai/QwenPaw/pull/5639) 已合并，实现了“技能（Skill）自动同步”功能，将技能池中的技能自动同步到选定的 Agent，简化了 Agent 配置流程。
- **文档与 CI 改进：**
    - 多个文档相关的 PR 已合并，包括：[#5666](https://github.com/agentscope-ai/QwenPaw/pull/5666) 修正通道文档，[#5665](https://github.com/agentscope-ai/QwenPaw/pull/5665) 优化 README，以及 [#5653](https://github.com/agentscope-ai/QwenPaw/pull/5653) 新增架构说明页面（中英文）。
    - PR [#5662](https://github.com/agentscope-ai/QwenPaw/pull/5662) 优化了 PR 模板，提升了协作效率。

- **功能推进：** `Loop Engineering` (PR [#5665](https://github.com/agentscope-ai/QwenPaw/pull/5665)) 和 `Windows Native Sandbox` (PR [#5525](https://github.com/agentscope-ai/QwenPaw/pull/5525)) 等大型功能 PR 仍在开放讨论与评审中，表明项目正稳健地向 v2.0 迈进。

## 4. 社区热点

- **最受关注 Issue：** **#5588 [[Feature]: 记忆搜索支持专用 Reranker 模型实现两阶段检索](https://github.com/agentscope-ai/QwenPaw/issues/5588)**
    - 该 Issue 探讨了当前记忆搜索“无精排环节”和“reME 的 LLM-based rerank 未启用”的痛点，并提出了两阶段检索的改进方案。4条评论均来自深度技术讨论，反映了社区中对 Agent 长期记忆能力提升的强烈渴望。

- **讨论最活跃 Issue：** **#5401 [[Bug]: Console: session with large tool-use history fails to render](https://github.com/agentscope-ai/QwenPaw/issues/5401)**
    - 虽然已被关闭，但该问题引起了 6 条评论。根本原因在于后端 API 返回的 DataContent 类型与前端渲染组件不兼容，导致大量工具调用历史的会话白屏。社区对此类影响核心使用体验的 Bug 非常敏感。

- **潜在高需求 PR：** **PR [#5665](https://github.com/agentscope-ai/QwenPaw/pull/5665) feat: Loop Engineering — Composable Gate Architecture & Frontend Settings**
    - 该 PR 由核心贡献者 rayrayraykk 提交，引入了可组合的门控架构用于循环工程，旨在解决 Agent 陷入无限循环的问题。虽然刚提交但热度很高，直击 Agent 应用的稳定性痛点。

- **用户核心诉求：** 从多个评论中可以看出，用户的核心诉求正从“能用”转向“好用”，具体表现在：
    - **稳定性：** 对心跳任务被打断、模型连接报错、会话白屏等稳定性问题容忍度低。
    - **通道体验：** 要求钉钉、飞书等通道的交互更流畅，如流式输出速度、文件处理、`@`功能等。
    - **精细化配置：** 希望更灵活地控制 Agent 行为，如绕过 debounce（Issue [#5663](https://github.com/agentscope-ai/QwenPaw/issues/5663)）和定时任务模型覆盖（Issue [#5638](https://github.com/agentscope-ai/QwenPaw/issues/5638)）。

## 5. Bug 与稳定性

今日报告了 **11 个 Bug 相关 Issue**，按严重程度排列如下：

| 严重程度 | Issue 编号 & 标题 | 状态 | 是否有 Fix PR |
| :--- | :--- | :--- | :--- |
| **严重** | [#5658](https://github.com/agentscope-ai/QwenPaw/issues/5658) 无法连接9router转发的模型请求 | 待处理 | 否 |
| **严重** | [#5616](https://github.com/agentscope-ai/QwenPaw/issues/5616) 自动化任务莫名其妙终止 | 待处理 | 否 |
| **高** | [#5587](https://github.com/agentscope-ai/QwenPaw/issues/5587) Qwen-Image Tool 安装错误 | 待处理 | 否 |
| **高** | [#5624](https://github.com/agentscope-ai/QwenPaw/issues/5624) 工具调用结果卡片的计数始终显示 1 | 已关闭 | 已合并 (PR #5624) |
| **中** | [#5561](https://github.com/agentscope-ai/QwenPaw/issues/5561) Agent 链接飞书后长回复收不到 | 待处理 | 否 |
| **中** | [#5566](https://github.com/agentscope-ai/QwenPaw/issues/5566) cron 任务静默执行 & channels send 通知不可达 | 待处理 | 是 (PR #5654 已合并) |
| **低** | [#5663](https://github.com/agentscope-ai/QwenPaw/issues/5663) 建议增加“绕过 debounce”开关 | 已关闭 | 否 (作为功能建议) |

- **关键 Bug 修复：** 昨日报告的 `DeepSeek V4 thinking 模式 400 错误` (Issue [#5573](https://github.com/agentscope-ai/QwenPaw/issues/5573)) 和 `心跳任务执行失败` (Issue [#5539](https://github.com/agentscope-ai/QwenPaw/issues/5539)) 今日均已关闭，表明项目团队修复了模型兼容性和核心任务调度方面的两个关键问题。
- **稳定性风险：** **Issue [#5658](https://github.com/agentscope-ai/QwenPaw/issues/5658)** 描述了通过 9Router 转发的模型请求无法连接，这可能是一个常见的代理兼容性问题，需要后端适配。**Issue [#5616](https://github.com/agentscope-ai/QwenPaw/issues/5616)** 中“自动化任务无故终止”的问题比较模糊，需要更多日志信息，可能和内存泄漏或未捕获异常有关，是一个潜在的稳定性隐患。

## 6. 功能请求与路线图信号

- **高优先级候选功能：**
    - **Reranker 模型支持** (Issue [#5588](https://github.com/agentscope-ai/QwenPaw/issues/5588))：社区强烈期望的“两阶段检索”功能，可显著提升 Agent 长期记忆的精准度。
    - **循环检测机制** (Issue [#5657](https://github.com/agentscope-ai/QwenPaw/issues/5657))：与 PR [#5665](https://github.com/agentscope-ai/QwenPaw/pull/5665) 的 Loop Engineering 高度相关，是解决 Agent 工作流卡死的核心功能。
    - **Telegram 自定义 BaseURL** (Issue [#5630](https://github.com/agentscope-ai/QwenPaw/issues/5630))：对应 PR [#5651](https://github.com/agentscope-ai/QwenPaw/pull/5651) 已由社区贡献者提交，预计很快会被包含在下一版本中。

- **可能纳入 v2.0 的功能方向：**
    - **沙盒（Sandbox）**：PR [#5525](https://github.com/agentscope-ai/QwenPaw/pull/5525) 的 Windows 原生沙盒实现正在开发中，符合 Agent 安全运行的行业趋势。
    - **插件系统优化**：PR [#5661](https://github.com/agentscope-ai/QwenPaw/pull/5661) 加入的版本兼容性筛选，将提升插件市场的可用性和稳定性。
    - **工作区文件浏览器** (Issue [#5667](https://github.com/agentscope-ai/QwenPaw/issues/5667))：用户希望在聊天界面内直接浏览 Agent 生成的输出文件，这会是一个提升用户体验的重要功能。

## 7. 用户反馈摘要

- **正向反馈：**
    - 用户在提交 Bug 和功能请求时，普遍提供了详细的环境信息和复现步骤，体现了社区的成熟度和专业性。
    - 有贡献者主动修复了 DeepSeek V4 和钉钉通道的关键问题，并获得了维护者的认可。

- **亟待解决的问题（用户痛点）：**
    - **钉钉通道流式输出速度慢** (#5603)：用户在钉钉端体验“打字机动画”般的低效输出，与 Console 面板的秒出形成鲜明对比，已影响日常使用效率，是当前通道体验的最主要痛点。
    - **模型兼容性与连接稳定性** (#5658): 非官方 API 端点兼容性问题持续存在，影响了用户的模型选择和灵活性。
    - **企业微信文件处理仍存在问题** (#5554): 即使已关闭，但用户反馈核心问题（发送文件无回复，下载后未被处理）并未在日志中看到明确的修复方案，可能是一个回归或未被完全解决的核心问题。

## 8. 待处理积压

- **长期未响应的关键 Issue：**
    - **#2495** (2026-03-29 创建) **[Feature]: mcp配置后，支持看到mcp中有哪些工具**：这是一个高质量的功能请求，已存在 3 个月，仅被标记为 `enhancement` 但无后续进展。MCP 生态系统是社区关注热点，此项功能对于提升 MCP 插件配置的可观测性和易用性至关重要，建议维护者重点评估并排期。

- **长时开放的“关键” PR：**
    - **#5151** (2026-06-12 创建) **fix(GitPanel): fix tabs styles not applied due to incorrect class prefix**：修复 GitPanel 标签样式问题的 PR 已经开放超过两周，尚未合并。虽然是小 Bug，但长期积压可能影响开发者使用 Git 功能的界面体验。
    - **#5097** (2026-06-11 创建) **fix(security): fix Shield icon centering by fixing space-item child**：同样是关于安全设置页面 UI 的轻微样式修复，开放已近 20 天，建议尽快合并。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 ZeroClaw 项目的 AI 智能体与个人 AI 助手领域开源项目分析师，以下是为您生成的 2026-06-30 项目动态日报。

---

# ZeroClaw 项目动态日报 (2026-06-30)

## 1. 今日速览

项目在 2026-06-30 展现出极高的活跃度，截止目前共更新 50 条 Issue 和 50 个 PR，社区讨论与技术推进均十分密集。核心焦点集中在 **v0.8.3 版本的稳定化与功能收尾**，尤其是围绕 MCP 工具访问、Telegram 通道配置以及 OTel 内容捕获等关键模块的 Bug 修复与特性增强。尽管今日无新版本发布，但多个大型 PR（如 Matrix 流式消息、Inkbox 通道）处于开放与 Code Review 阶段，表明项目正为下一次发布积蓄力量。整体项目健康度良好，但高风险的 P1 级 Bug 较多，需关注其解决进度。

## 3. 项目进展

今日有 9 个 PR 被合并或关闭，标志着项目在多个方面取得了关键进展，具体如下：

- **会话生命周期与 Hook 机制完善**: **[PR #8003](https://github.com/zeroclaw-labs/zeroclaw/pull/8003)** [已关闭] 修复了 `session_end` Hook 从未被调用的核心问题。该项目此前存在一段“死代码”，即 `on_session_end()` 方法定义但未被任何会话终止路径调用，此 PR 将此机制正确接入 RPC 会话生命周期流程，使得开发者可以在此 Hook 中执行清理或日志记录逻辑，是基础设施层面的重要补丁。

- **流式请求的健壮性增强**: **[PR #8148](https://github.com/zeroclaw-labs/zeroclaw/pull/8148)** [已关闭] 修复了 Anthropic 提供商中以 `expect()` 方式处理请求序列化错误的问题，防止在特定情况下因序列化失败导致整个进程 `panic`，提升了流式请求构建的稳定性。

- **持续集成与安全基建推进**: **[PR #8157](https://github.com/zeroclaw-labs/zeroclaw/pull/8157)** [已关闭] 引入了 **Semgrep** 作为 PR 门的静态分析工具，以及 **CodeQL** 作为主分支和定时任务的深层 Rust 污点分析。这标志着 ZeroClaw 正在构建多层次的 CI 安全防御体系，是项目成熟度提升的重要信号。

此外，多个测试相关的 PR（如 `#8267`, `#8269`, `#8255`）被提交，覆盖了 RobotConfig、日志过滤器和工具 IO 截断等边缘场景，表明团队正在系统性地补齐单元测试空白。

## 4. 社区热点

今日最受关注的 Issue 和 PR 反映了社区对 **架构治理** 和 **开发者体验** 的强烈关注。

- **热点 Issue**: **[RFC: Work Lanes, Board Automation, and Label Cleanup (#6808)](https://github.com/zeroclaw-labs/zeroclaw/issues/6808)**
    - 评论数: 13 (最高)
    - **分析**: 这是一个关于项目治理与工作流程优化的 RFC。它提出要通过“Work Lanes”（工作通道）和“Board Automation”（看板自动化）来简化 Issue 和 PR 的流转，减少维护者的手动操作。13 条评论表明社区贡献者对项目协作流程的改进有着强烈诉求，希望减少繁琐的标签管理和状态切换工作，将精力集中在代码本身。

- **热点 PR**: **[feat(inkbox): add a native Inkbox channel ... (#8384)](https://github.com/zeroclaw-labs/zeroclaw/pull/8384)** 和 **[feat(matrix): add single-message streaming drafts (#8443)](https://github.com/zeroclaw-labs/zeroclaw/pull/8443)**
    - 这两个均为重量级（`size:XL`）的新功能 PR，虽然今日评论不多，但在整个 Issue 列表中是社区讨论的焦点。`Inkbox` 通道将带来邮件、短信、语音和 iMessage 的统一接入能力；而 `Matrix` 的流式消息草稿功能通过实时编辑而非发送多条消息的模式，显著提升了用户体验。这体现了社区对于 **多元化、高质量通信通道** 的持续需求。

## 5. Bug 与稳定性

今日报告的 Bug 中，高风险（`risk:high`）问题占比较高，值得关注。按严重程度排列如下：

1.  **S1 - 工作流阻塞**:
    - **[Bug]: Telegram channel cannot be configured (#8505)](https://github.com/zeroclaw-labs/zeroclaw/issues/8505)**: Telegram 通道无法通过 quickstart 或 zerocode 正确配置，导致 Bot 无响应。此问题直接堵死了 Telegram 用户的使用路径。
    - **[Bug]: MCP tools/tool_search missing from TUI sessions (#8193)](https://github.com/zeroclaw-labs/zeroclaw/issues/8193)**: MCP 工具在 TUI 界面中不可用，但网关却能正常发现。这是影响 zerocode 用户工作流的严重问题，有 **5 条评论** 表明多人受影响。

2.  **S2 - 功能降级**:
    - **[Bug]: SQLite is the default memory backend but quickstart never requires/prompts an embedding model ... (#8386)](https://github.com/zeroclaw-labs/zeroclaw/issues/8386)**: 默认配置导致混合搜索静默退化为关键词搜索。这是一个 **隐蔽的体验陷阱**，新用户按照 quickstart 上手后可能并未获得预期的 AI 记忆检索效果。
    - **[Bug]: Code history can send non-alternating Anthropic messages (#7804)**: 已关闭。长时间代码会话可能导致发送给 Anthropic API 的消息角色不交替，从而引发 400 错误。**Issue 虽已关闭，但根因和修复方案值得关注。**

3.  **其他高风险 Bug**:
    - **[Bug]: consecutive OOM in wsl2 (#5542)**: WSL2 环境下的连续内存溢出问题，标记为 `r:needs-repro`（需复现），已有 **6 条评论** 讨论。

目前 **高风险 (risk:high) Bug 尚无对应的 fix PR** 被合并，维护团队需优先处理 Telegram 配置和 MCP 工具缺失这两个阻碍用户使用的问题。

## 6. 功能请求与路线图信号

今日新增/讨论的功能请求中，以下三个方向可能被纳入 v0.8.3 或下一版本：

- **可观测性增强**: **[RFC: Runtime Policy for OTel LLM and Tool Content (#8462)](https://github.com/zeroclaw-labs/zeroclaw/issues/8462)** 正在讨论为 OTel 通用消息属性添加运行时策略控制。这呼应了 [#6642](https://github.com/zeroclaw-labs/zeroclaw/issues/6642)（已关闭）中对 LLM 调用内容捕获的需求，表明项目正在从“能不能捕获”向“如何安全、可控地捕获”深化。

- **Agent 多租户与环境隔离**: **[Feature]: support per-agent custom environment variables configuration (#8226)](https://github.com/zeroclaw-labs/zeroclaw/issues/8226)** 提议引入 `runtime_context` 和 `runtime_secrets` 配置块，以解决不同 Agent 在共享 MCP 或 Shell 工具时的身份与参数隔离问题。这是向企业级 Agent 平台演进的关键能力。

- **通道功能微调**: **[Feature]: Telegram channel multi-message mode (#8445)](https://github.com/zeroclaw-labs/zeroclaw/issues/8445)**: 建议为 Telegram 通道增加单 Agent 轮次单条消息模式，而非当前将所有轮次内容拼接为一条消息。这反映了用户对更细腻的通道交互行为的定制化需求，对应的 **[PR #8443](https://github.com/zeroclaw-labs/zeroclaw/pull/8443)** 已为 Matrix 实现了类似功能，基本逻辑可以复用。

## 7. 用户反馈摘要

从今日的 Issue 评论中，可以提炼出以下真实用户反馈：

- **对 Telelgram 通道的配置体验感到沮丧**: 用户 `AIWintermuteAI` 在 **#8505** 中报告“zeroclaw channels doctor claims the channels are not set up - even after setting them up”，并补充“The agent replies in CLI”但“The bot does not answer on TG”，这表明问题很可能存在于通道与客户端通信的特定环节，而非核心 Agent 能力。用户明确区分了“CLI 可工作”和“Telegram 不响应”这两种行为，为精准定位 Bug 提供了宝贵线索。
- **对默认配置的隐含陷阱表示不满**: Issue **#8386** 中，用户 `JordanTheJet` 描述了一个典型的“不良新手体验”：使用默认 SQLite 后端并按 quickstart 操作，导致记忆搜索功能静默降级。用户的反馈（“mutually inconsistent”）直接揭示了配置间缺乏联动校验的设计缺陷。
- **对 MCP 工具分发机制的困惑**: 在 **#8193** 中，用户报告 MCP 工具“connect and expose tools”但“TUI sessions do not receive the discovered MCP tools”。这表明用户对 MCP 工具的“发现-路由-展示”全链路有清晰的理解，并能准确指出断点出现在“TUI 展示”这一侧。这一问题可能涉及复杂的权限过滤或 session 上下文传递机制。

## 8. 待处理积压

以下 Issue 和 PR 长期处于响应或阻塞状态，提醒维护者关注：

- **PR 积压 (需要作者 action)**:
    - **[PR #7637](https://github.com/zeroclaw-labs/zeroclaw/pull/7637)**: fix(zerocode): auto-normalise agent alias input in quickstart
    - **[PR #7535](https://github.com/zeroclaw-labs/zeroclaw/pull/7535)**: feat(whatsapp-web): implement add_reaction and remove_reaction
    这两个 PR 均被标记为 `needs-author-action` 或 `stale-candidate`，存在因长期未响应而被自动关闭的风险。如果维护者认为有价值，应主动联系作者或考虑接手。

- **高风险功能请求 (缺少维护者裁决)**:
    - **[Issue #7952](https://github.com/zeroclaw-labs/zeroclaw/issues/7952)**: [Feature]: publish full-channel prebuilt assets alongside default prebuilts
    - **[Issue #8043](https://github.com/zeroclaw-labs/zeroclaw/issues/8043)**: RFC: Retire the standalone aardvark-sys crate (fold into zeroclaw-hardware)
    这两个 Issue 都处于 `status:blocked, needs-maintainer-review` 状态，依赖维护者的架构决策。尤其是 `aardvark-sys` crate 的合并，涉及硬件抽象层的重构，长期阻塞会影响硬件相关功能的开发进度。

</details>

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*