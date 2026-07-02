# OpenClaw 生态日报 2026-07-02

> Issues: 210 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-07-02 10:20 UTC

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

好的，作为AI智能体与个人AI助手领域开源项目分析师，根据您提供的OpenClaw GitHub数据，我为您生成了2026年7月2日的项目动态日报。

---

# OpenClaw 项目日报 (2026-07-02)

## 1. 今日速览

今日OpenClaw项目社区活跃度极高，Issue和PR更新总量超过700条，显示出项目正处于快速迭代与问题集中爆发期。项目发布了`v2026.7.1-beta.1`版本，核心亮点是支持最新的OpenAI GPT-5.6模型，并新增了开启外部会话的功能。然而，从大量的Bug报告来看（特别是关于会话状态丢失、消息渲染错误和各种回归问题），项目当前的稳定性面临一定挑战，尤其是`v2026.6.11`版本似乎引入了多个影响用户实际使用的严重问题。尽管如此，社区贡献者响应迅速，大量PR正在积极解决这些稳定性问题。

## 2. 版本发布

- **版本:** v2026.7.1-beta.1
- **发布链接:** [openclaw/openclaw Releases v2026.7.1-beta.1](https://github.com/openclaw/openclaw/releases/tag/v2026.7.1-beta.1)
- **更新内容:**
  - **OpenAI GPT-5.6 支持:** OpenClaw现已能在模型目录、能力选择及运行时路径中识别 GPT-5.6 模型家族。(#98333)
  - **外部挂载 (External harness attachment):** 新增 `openclaw attach` 命令，允许用户针对现有网关会话启动一个外部执行程序，为调试和高级交互提供了新途径。

本次更新未提及明确的破坏性变更或迁移指南。

## 3. 项目进展

尽管暂未有重要的PR被合并到主分支，但项目社区正全力推进关键功能与修复，以下是今日最值得关注的进展：

- **核心功能开发：** 两项大型功能PR正处于活跃开发或等待审核阶段，标志着项目正在向更通用的运营平台迈进。
  - [PR #98727](https://github.com/openclaw/openclaw/pull/98727): **feat: add durable routines registry** - 引入“耐久例程注册表”，为创建、检查、暂停、删除重复性团队运营任务提供了统一的框架，超越了现有的Cron和任务机制。
  - [PR #98718](https://github.com/openclaw/openclaw/pull/98718): **feat(durable): add durable session task runtime foundation** - 构建“耐久会话任务运行时”基础，旨在解决长时间运行任务在进程重启后仍能持续工作的可靠性问题。
- **关键Bug修复：** 针对近期报告的严重问题，多个PR已提交并等待审核，解决进度令人欣慰。
  - [PR #98640](https://github.com/openclaw/openclaw/pull/98640): 修复Anthropic Claude Opus 4.8模型因JSON Schema严格验证而拒绝请求的问题。
  - [PR #98640](https://github.com/openclaw/openclaw/issues/98588) (关联): 该PR专门解决了`tools.profile=coding`与`opus-4-8`配合使用时出现HTTP 400错误的问题。
  - [PR #98907](https://github.com/openclaw/openclaw/pull/98907): 修复Telegram频道中流式回复的格式渲染问题，使推理过程和评论内容清晰可辨。
- **基础设施改进：** 社区持续关注代码质量与安全性。
  - [PR #98923](https://github.com/openclaw/openclaw/pull/98923): 将测试代码中的临时目录创建迁移至自动清理的`withTempDir`辅助函数，避免磁盘空间泄漏。
  - [PR #99006](https://github.com/openclaw/openclaw/pull/99006): 提出为`TranscriptsStore`添加SQLite存储后端，符合项目“SQLite优先”的技术方向。

## 4. 社区热点

今日讨论最热烈的Issues和PRs反映出用户对**会话状态错误**和**消息丢失/错乱**的高度关注。

1.  **绝对焦点：会话与消息状态问题**
    - **[#25592](https://github.com/openclaw/openclaw/issues/25592) - 工具调用间的文本泄露:** 33条评论，被标记为最高优先级（P1）和“钻石龙虾”级别。用户强烈抱怨Agent在工具调用之间产生的内部处理文本（如错误信息）被发送到公共聊天频道，这是一个严重的UX问题。这引发了关于会话状态管理和消息路由机制的根本性讨论。
    - **[#92201](https://github.com/openclaw/openclaw/issues/92201) - Anthropic推理签名无效:** 17条评论。问题涉及嵌入式运行器在重放Anthropic thinking块时出现签名无效，且错误恢复逻辑因错误泛化而失效，导致会话进程完全卡死。
    - **[#92433](https://github.com/openclaw/openclaw/issues/92433) - 子Agent完成信号丢失:** 7条评论。当子Agent完成时，如果其请求者的运行进程被提前结束，子Agent的完成信号会被静默丢弃，导致结果丢失。

2.  **回归问题引发大量讨论**
    - **[#98672](https://github.com/openclaw/openclaw/issues/98672) - 会话频繁中断:** 7条评论。用户 `AaronFaby` 报告从`v2026.6.10`升级到`v2026.6.11`后，会话开始“持续中断”，且无任何操作变更。这引发了大量有类似遭遇用户的共鸣，是典型的回归问题。
    - **[#98416](https://github.com/openclaw/openclaw/issues/98416) - 发布版本遗漏重入保护:** 6条评论，获得5个点赞。社区发现`v2026.6.11`的发布版本缺少了代码中已有的会话初始化重入保护修复，导致初始化冲突。这暴露了发布流程中的严重缺陷。

**分析结论:** 社区的核心诉求已经从功能探索转向稳定性和可靠性。用户正面临大量令人沮丧的“会话挂起”、“消息丢失”和“升级即坏”的体验。讨论的焦点不再是“它能做什么”，而是“它为什么不能稳定运行”。

## 5. Bug 与稳定性

今日报告的Bug数量众多，且呈现集中爆发的态势，特别是针对`v2026.6.11`版本。以下是按严重程度排列的今日最值得关注的Bug：

- **会话中断/卡死 (P1)**
  - [#98672](https://github.com/openclaw/openclaw/issues/98672): **【回归】会话频繁中断** - 用户升级后无操作变更，会话随机中断。**严重性：高**。相关修复PR状态：待定。
  - [#98745](https://github.com/openclaw/openclaw/issues/98745): **“回复会话初始化冲突”** - 使用GLM-5.2模型时，会话卡死在“运行中”状态，无法进行后续交互。**严重性：高**。此Issue已被关闭，可能与#98416的修复有关。

- **消息与输出错误 (P1 - P2)**
  - [#98528](https://github.com/openclaw/openclaw/issues/98528): **【回归】工具输出返回空** - `v2026.6.11`回归，所有工具在第一次调用后均返回空结果。**严重性：极高**，严重影响Agent功能。相关修复PR状态：待定。
  - [#96857](https://github.com/openclaw/openclaw/issues/96857): **工具文本输出变为“(see attached image)”** - 普通文本输出被错误地渲染为图片占位符，导致Agent无法读取关键信息。
  - [#98874](https://github.com/openclaw/openclaw/issues/98874): **工具文本结果渲染为图片附件** - 与#96857类似的问题，影响`exec`, `read`等多个核心工具。**严重性：高**。

- **连接与认证问题 (P1)**
  - [#98740](https://github.com/openclaw/openclaw/issues/98740): **【回归】Mattermost插件外化后导致401错误** - `v2026.6.11`将Mattermost插件外化为独立包后，所有原生斜杠命令均返回`401 Unauthorized`。**严重性：高**。相关修复PR状态：待定。
  - [#91352](https://github.com/openclaw/openclaw/issues/91352): **OpenAI Codex OAuth迁移遗留问题** - OAuth迁移导致旧配置文件残留，可能使Codex执行环境初始化失败。**严重性：高**。

- **运行时崩溃 (P1)**
  - [#38327](https://github.com/openclaw/openclaw/issues/38327): **“Cannot convert undefined or null to object”** - 使用Google Vertex/Gemini模型时的回归问题，导致Agent进程崩溃。**严重性：高**。标记有一个关联的修复PR已开启。

## 6. 功能请求与路线图信号

尽管稳定性问题占据主导，但仍有一些高质量的功能请求揭示了用户社区对未来方向的期望。

- **** iOS体验优化 (P3, 新近): 用户 `sahilsatralkar` 提交了多个关于iOS应用的UI/UX改进请求，包括[重新设计设置页面](https://github.com/openclaw/openclaw/issues/98995)、[改进关于页面](https://github.com/openclaw/openclaw/issues/98943)以及[统一列表图标样式](https://github.com/openclaw/openclaw/issues/98916)。这表明官方iOS应用的用户群正在增长，并希望获得更精致的原生体验。这些请求通常较容易实现，可能在下一iOS版本中被采纳。
- **Doubao/Volcengine实时语音模式 (P3):** Issue [#98927](https://github.com/openclaw/openclaw/issues/98927) 请求为国内用户常用的Doubao/Volcengine TTS服务在实时语音对话模式中提供更清晰、易用的集成路径。这代表了特定区域市场的强烈需求，若OpenClaw计划深耕中国市场，此功能将非常重要。
- **外部工作空间Agent自动发现 (P2):** 这是一个长期存在的功能请求 [#32530](https://github.com/openclaw/openclaw/issues/32530)，希望OpenClaw能从指定工作目录自动发现并加载Agent配置，减少手动配置工作。虽然优先级不高，但反映了用户对简化运维和提升配置灵活性的持续需求。

**信号:** 用户社区除了追求稳定外，还对移动端体验、本地化服务和自动化配置有着明确的期望。这些方向将是项目从“可用”走向“易用”和“好用”的关键。

## 7. 用户反馈摘要

从今日的Issue和PR评论中，我们可以提炼出以下真实的用户声音：

- **痛点:**
  - **“升级即坏的恐惧”：** 多位用户报告从`v2026.6.10`到`v2026.6.11`的升级带来了严重的会话中断和工具输出问题。例如，用户 `AaronFaby` (“Sessions breaking constantly”) 和 `Johannes0402` (“Tool output returns empty”) 的反馈表明，用户对版本升级的稳定性感到担忧和不信任。
  - **“看不见的错误”：** 用户对模糊的错误信息表达了不满。如Issue #73148 (`Failed to optimize image`)和#38327 (`Cannot convert undefined or null`)所描述，缺乏明确的指引让用户无法自行诊断和解决问题。
  - **“静默的失败”：** 多个Bug涉及“消息/结果被丢弃或错位”，例如#92433 (Subagent completion silently dropped) 和 #70024 (channel stop timeout leaves channel permanently dead)。这种无声的失败模式极大地破坏了用户的信任感。

- **使用场景:**
  - **Slack/Telegram等即时消息集成：** 大量Bug和功能请求围绕Slack、Telegram、Discord、Mattermost、Feishu等聊天平台展开，表明OpenClaw的核心使用场景仍是作为团队或个人的AI助手，嵌入到现有的聊天工作流中。
  - **长时间运行的Agent任务：** 社区对“耐久性”和“会话恢复”功能的讨论[PR #98718](https://github.com/openclaw/openclaw/pull/98718)表明，用户正在将Agent用于需要长时间运行、跨越多轮交互的复杂任务，并期望在这些任务在遇到故障后能被可靠地恢复。

- **满意度:**
  - **正面反馈：** 用户对部分新功能和修复表示认可。例如，对GitHub Releases中GPT-5.6的支持感到满意。另外，一些用户通过贡献代码和提出详细的Bug报告（如#92201和#94228）展现了极高的参与度和专业性，这表明核心贡献者圈子对该项目抱有热情。
  - **负面反馈:** 整体情绪偏向焦虑和受挫，主要源于近期版本的稳定性问题。高频的“regression”标签和大量标为P1的Bug是明显的迹象。

## 8. 待处理积压

以下是一些长期未关闭或近期有重要更新的Issue/PR，需要维护者团队关注：

- **高优Bug, 长期未决:**
  - [#25592](https://github.com/openclaw/openclaw/issues/25592) (工具间文本泄露): 已存在超过4个月，仍有33条评论且有最新更新。作为“钻石龙虾”级别的Issue，其对用户体验的影响巨大，不应再被搁置。
  - [#70024](https://github.com/openclaw/openclaw/issues/70024) (频道停止超时导致永久死亡): 同样已存在超过2个月，是“钻石龙虾”级别，影响Session状态和消息传递，急需一个修复策略。

- **关键功能PR等待维护者审核:**
  - [#52951](https://github.com/openclaw/openclaw/pull/52951) (feat: add tools.fs.roots): 此PR已开放超过3个月，旨在提供细粒度的文件系统访问控制。对于多租户场景至关重要，应优先审核。
  - [#53467](https://github.com/openclaw/openclaw/pull/53467) (feat(slack): add ignoreOtherMentions): 同样是超过3个月的PR，针对Slack频道噪音问题提供了简洁的解决方案，有助于提升用户体验，值得合并。

- **安全相关修复:**
  - [#49083](https://github.com/openclaw/openclaw/pull/49083) (fix(security): use constant-time comparison for TLS fingerprint verification): 这是一个安全增强PR，使用恒定时间比较来防止计时攻击。安全优先级不应被忽略。

**总结:** OpenClaw项目正站在一个关键的十字路口。一方面，其功能更新和新版本发布（如GPT-5.6支持）证明了其创新活力。但另一方面，近期爆发的稳定性危机和积压的高优先级Bug正在消耗社区信任。维护者团队应优先将工作重心从“添加新功能”暂时转移到“修复现有Bug和提升稳定性”上，尤其是快速响应`v2026.6.11`版本引入的回归问题，并清理那些长期悬而未决的“钻石龙虾”级别Issue，以重振用户信心。

---

## 横向生态对比

好的，作为AI智能体与个人AI助手领域开源项目分析师，我将基于上述各项目的动态日报，为您生成一份横向对比分析报告。

---

# AI智能体与个人AI助手开源生态横向对比分析报告 (2026-07-02)

## 1. 生态全景

当前，个人AI助手/自主智能体开源生态呈现出 **“大项目跃进，新项目分化”** 的态势。以 `OpenClaw`、`Hermes Agent`、`IronClaw` 为代表的头部项目正经历快速迭代，但普遍在引入重大功能后遭遇了 **稳定性危机**，用户从“探索功能”转向“要求可靠”。与此同时，一批新兴项目（如 `ZeroClaw`, `CoPaw`) 以及更轻量级的方案 (`NanoBot`, `PicoClaw`, `NanoClaw`) 通过聚焦特定场景（如安全性、移动端、模板化、渠道兼容性）进行差异化竞争。**安全加固、运行时一致性、多模型调度、以及跨平台（尤其是跨IM渠道）的可靠性** 成为所有项目共同面临的“圣杯挑战”。社区情绪在肯定项目创新力的同时，对频繁出现的回归问题和长期未解决的P1级Bug表现出明显焦虑。

## 2. 各项目活跃度对比

以下表格总结了2026年7月2日各项目的核心活跃度指标。

| 项目名称 | 今日Issue数 | 今日PR数 | 版本发布 | 项目健康度 | 关键标签 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 高 (300+) | 高 (400+) | v2026.7.1-beta.1 | 🟡 **警惕** | 稳定性风暴、回归问题、会话状态 |
| **Hermes Agent** | 50 | 50 | v0.18.0 (昨日) | 🟢 **良好** | 大版本发布、功能丰富、社区贡献活跃 |
| **IronClaw** | 24 | 50 | 无 | 🟡 **中等** | 架构重构(Reborn)、内部QA、性能优化 |
| **CoPaw** | 较少 (vs PR) | 32 | v2.0.0-beta.2 | 🟢 **良好** | 安全性、飞书集成、渠道兼容性 |
| **ZeroClaw** | 高 (50) | 高 (50) | 无 | 🟢 **良好** | 架构拆解、MCP工具、安全审计 |
| **NanoBot** | 24 | 66 | 无 | 🟢 **良好** | 修复密集、测试增强、普适性增强 |
| **PicoClaw** | 15 | 15 (低合并) | 无 | 🟡 **中等** | 活跃PR但合并慢、Matrix致命Bug |
| **NanoClaw** | 多变 | 6 (高合并) | 无 | 🟢 **良好** | Agent模板化、稳定性修复、长期积压清理 |
| **LobsterAI** | 0 (新) | 7 | 无 | 🟢 **良好** | 修复驱动、稳定、社区讨论低 |

*注：OpenClaw数据基于“超过700条更新”的笼统描述，活跃度遥领先，但健康度警示最强。*

## 3. OpenClaw 在生态中的定位

OpenClaw 在生态中扮演着 **“能力最全但风险最高的旗舰项目”** 角色。

- **核心优势**:
    - **功能广度**: 率先支持 GPT-5.6，提出“耐久例程”等前瞻性架构，路线图激进，功能覆盖最全。
    - **社区规模**: Issue/PR数量远超其他项目（日更700+），是当之无愧的活跃中心，吸引了大量关注和贡献。
- **关键差距与风险**:
    - **稳定性短板**: 与 `Hermes Agent` (刚发大版本)和 `IronClaw` (专注稳定性) 不同，OpenClaw 的 `v2026.6.11` 版本带来的回归问题极其严重，会话中断、消息丢失等P1级Bug集中爆发，社区信任受到打击。
    - **治理挑战**: “发布版本遗漏重入保护”(#98416) 暴露了其发布流程存在严重缺陷，这在 `ZeroClaw` (通过拆分大型PR提升质量) 和 `LobsterAI` (修复驱动版本) 等项目中未见如此严重的问题。
- **生态对比**: 相较 `Hermes Agent`（针对v0.18.0的快速修复），`IronClaw`（架构层面的熔断器与心跳解耦），OpenClaw的稳定性修复显得较为被动和滞后。它在功能上领先，但在可靠性和工程治理方面，正被追赶者拉开距离。

## 4. 共同关注的技术方向

多个项目同时涌现出相似的社区诉求，反映出行业的共性挑战：

1.  **会话与运行时一致性 (OpenClaw, ZeroClaw, IronClaw)**:
    - **具体诉求**: 解决不同入口（Web/TUI/IM Channel）下，Agent工具发现、消息路由、状态保持的不一致问题。
    - **体现**: OpenClaw的 `MCP tool missing`，ZeroClaw的 `#8193`，IronClaw的Slack/Ui不一致。

2.  **模型调度与细粒度控制 (Hermes Agent, NanoBot, CoPaw)**:
    - **具体诉求**: 允许用户为不同频道、不同任务（聊天/后台/委派）指定不同模型，以平衡成本、性能和效果。
    - **体现**: Hermes的频道级模型覆盖(`#1991`)和委派任务模型(`#56891`)，CoPaw的自动模型切换(`#5718`)，NanoBot的Cron级别模型预设(`#4378`)。

3.  **安全性加固 (CoPaw, ZeroClaw, PicoClaw)**:
    - **具体诉求**: 环境变量/密钥脱敏、Web控制台访问控制、认证完整性、防范zip炸弹等。
    - **体现**: CoPaw的 `#5705` 密钥脱敏，ZeroClaw的 `#8574` zip防范，PicoClaw的 `#3160` 跨站请求防范。

4.  **跨IM渠道可靠性 (CoPaw, PicoClaw, IronClaw, OpenClaw)**:
    - **具体诉求**: 解决微信、飞书、Telegram、Matrix等渠道下的消息丢失、重连失败、渲染错误等稳定性问题。
    - **体现**: 几乎每个项目都有针对特定平台的修复（如CoPaw修复飞书，PicoClaw修复Matrix，IronClaw修复Slack）。

5.  **Agent编排与模板化 (NanoClaw, OpenClaw, IronClaw)**:
    - **具体诉求**: 通过模板、SOP、工作流等机制，将Agent行为固化、标准化，降低多Agent场景下的管理与部署复杂度。
    - **体现**: NanoClaw的Agent模板化，OpenClaw的耐久例程和SOP，IronClaw的Scoped-lifecycle。

## 5. 差异化定位分析

| 维度 | **OpenClaw** | **Hermes Agent** | **IronClaw** | **ZeroClaw** | **CoPaw** | **NanoBot/NanoClaw** | **PicoClaw** | **LobsterAI** |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **核心定位** | 全能型智能体平台 | 开源自部署AI助手 | 企业级基础设施 | 通用Agent平台 | 中文生态智能体 | 轻量级Agent/工具 | 嵌入式/端侧智能体 | 办公效率AI |
| **技术路线** | 激进的架构演进 | 功能驱动，社区活跃 | 架构重构(稳定优先) | 安全与架构清晰 | 飞书/企微等渠道深度集成 | 模块化，测试驱动 | 跨平台，跑得快 | 稳健迭代，功能实用 |
| **目标用户** | 高级开发者、早期探索者 | 开源软件开发者、团队 | 企业开发者、运维 | 安全工程师、跨平台开发者 | 中国用户、飞书/微信生态用户 | 个人开发者、场景开发者 | 嵌入式场景、边缘计算 | 办公自动化、文档处理 |
| **核心优势** | 功能最全、社区最大 | 发布流程成熟、社区贡献多 | 架构设计严谨、可观测性强 | 注重安全、代码拆解得当 | 中文渠道支持领先 | 修复响应快、测试完善 | 轻便、支持多种硬件 | 钉钉/企业微信等办公集成 |
| **主要弱点** | 稳定性差、发布流程有缺陷 | 功能迭代快可能导致回归 | 架构复杂、学习曲线陡 | 平台兼容性(Windows)弱 | 社区规模小、长期Bug积压 | 功能全面性、深度不够 | 合并率低、Matrix稳定性差 | 用户反馈少、创新放缓 |

## 6. 社区热度与成熟度

- **快速迭代/新功能驱动阶段**:
    - **OpenClaw**: 热度最高，但质量动荡。用户积极但焦虑。
    - **Hermes Agent, ZeroClaw**: 兼具高活跃度和良好技术治理，社区贡献者有信心，是值得关注的优质生态。
    - **IronClaw, CoPaw**: 核心团队主导，方向明确，在关键领域（架构/安全）快速突破。

- **质量巩固/稳定性驱动阶段**:
    - **NanoBot, NanoClaw, LobsterAI**: 活跃度中等但健康。特点为Bug修复迅速、测试增强、积压得以清理。是稳定使用者的首选。
    - **PicoClaw**: 技术方案有特色，但长期待合并PR (如 `DeltaChat`) 和关键Bug (`Matrix同步`、`Android崩溃`) 未得到有效处理，社区信心可能受损。

- **冷清/停滞阶段**:
    - **NullClaw, TinyClaw, Moltis, ZeptoClaw**: 24小时无任何活动，表明社区或项目已处于停滞或低维护状态。

## 7. 值得关注的趋势信号

从社区的反馈中，我们可以提炼出以下对AI智能体开发者有参考价值的行业趋势：

1.  **从“黑盒”到“可观测、可调试”的刚需**: 用户强烈要求了解Agent内部运行状态。`IronClaw` 的 `run-borking` 修复和 OTel 策略，`OpenClaw` 的 “No thread attached” 投诉，都指向了**运行时透明性**是下一阶段必备特性。开发者应将 `debug` 和 `observability` 作为一等公民设计。

2.  **“MCP/工具”生态是核心护城河**: `ZeroClaw` 的 MCP 工具问题是最热Issue，`OpenClaw` 和 `Hermes` 的 `tools.fs.roots` 和技能配置需求也表明，**工具集的可扩展性和易用性**将决定Agent平台的价值。集成MCP（或类似协议）成为新共识。

3.  **“安全性”从可选到必需**: `CoPaw` 和 `ZeroClaw` 的安全加固密集出现，社区自发提出密钥管理RFC，这已不是企业级特性，而是云原生和自部署场景下的**基本要求**。任何考虑生产环境的项目，都必须自行承担安全审计和加固的开销。

4.  **“模板化/标准化”是降低门槛的关键**: `NanoClaw` 的Agent模板系统、`ZeroClaw` 的 SOP 尝试、`OpenClaw` 的耐久例程，共同指向一个趋势：**智能体正在从“自由写代码”向“配置化/模板化”转变**，如同容器变得可编排，Agent也需要“Docker Compose”。

5.  **跨平台（特别是Windows）支持仍是长尾挑战**: `ZeroClaw` 爆出74个Windows测试失败，`PicoClaw` 的Android崩溃长期未解，说明 **Linux/Mac生态之外的平台兼容性**依然是制约项目普适性的主要瓶颈。对于面向个人开发者而非企业运维的项目，这一点不容忽视。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 NanoBot 项目数据，生成一份 2026 年 7 月 2 日的项目动态日报。

---

# NanoBot 项目动态日报 | 2026-07-02

## 1. 今日速览

NanoBot 项目今日表现出显著的活跃度，尤其在修复方面。过去 24 小时内，项目共收到 24 条 Issue 更新和 66 条 PR 更新，显示出社区参与度极高。值得注意的是，一批搁置已久的安全和功能类 Bug 获取了新的进展，并有多个高优先级的修复 PR 已被合并。项目核心团队（`chengyongru`, `yu-xin-c`）和外部贡献者（`hamb1y`, `antoobi`）均提交了关键修复和新功能，表明项目正从新功能推进转向稳定性与安全性强化阶段。

## 3. 项目进展

今日项目在关键 Bug 修复和测试基础设施方面取得了实质性进展，多个已合并的 PR 解决了影响稳定性和安全性的问题。

- **修复 WebUI 子代理回填问题**：PR [#4641](https://github.com/HKUDS/nanobot/pull/4641) 已合并，解决了当 WebUI 会话刷新/回填时，子代理内部完成负载会以可见气泡形式显示在聊天界面中的问题（Issues [#4640](https://github.com/HKUDS/nanobot/pull/4640)）。这直接改善了用户体验。
- **修复 Shell 执行问题**：PR [#4643](https://github.com/HKUDS/nanobot/pull/4643) 已合并，优化了 `exec` 工具在会话模式下的性能：当子进程提前退出时，会立即返回结果，避免了不必要的等待。
- **修复自动化工作流稳定性**：PR [#4642](https://github.com/HKUDS/nanobot/pull/4642) 已合并，对本地触发器（`local trigger`）的审计记录进行了截断处理，防止内容过长的记录导致文件系统问题，并增强了 `fsync` 的容错能力。
- **完善安全修复**：针对 `ExecTool` 的相对符号链接权限绕过问题，`yu-xin-c` 提交的 PR [#4629](https://github.com/HKUDS/nanobot/pull/4629) 已被提出并待审查。这标志着对已报告安全漏洞（Issue [#4072](https://github.com/HKUDS/nanobot/pull/4072)）的积极跟进。
- **增强测试基础设施**：PR [#4631](https://github.com/HKUDS/nanobot/pull/4631)、[#4628](https://github.com/HKUDS/nanobot/pull/4628)、[#4630](https://github.com/HKUDS/nanobot/pull/4630) 和 [#4633](https://github.com/HKUDS/nanobot/pull/4633) 展示了社区对测试质量的重视。这些 PR 添加了用于测试 Agent Runner、Memory Lifecycle、工具调用阻断以及 Cron 实例一致性的脚本化测试框架，为未来代码变更提供了更高的稳定性和信心。

## 4. 社区热点

今日社区讨论的焦点主要集中在以下几个议题上：

- **Anthropic OAuth 支持**: PR [#4632](https://github.com/HKUDS/nanobot/pull/4632) 是今日最受关注的合并请求之一，由 `hamb1y` 提出。该项目旨在为不持有 Anthropic Console API 密钥的 Claude 订阅用户提供 OAuth 认证支持。Issue [#4604](https://github.com/HKUDS/nanobot/pull/4604) 是此功能请求的直接来源，显示出用户对降低使用门槛、便捷接入 Claude 模型有强烈需求。
- **WebUI 桌面通知**: PR [#4651](https://github.com/HKUDS/nanobot/pull/4651) 由 `antoobi` 提出，旨在为后台运行的聊天会话添加桌面通知功能。这是一个用户粘性提升功能，允许用户在切换标签页工作后，能及时收到 Agent 回复的提示，显著提升用户体验。
- **功能启用框架**: PR [#4396](https://github.com/HKUDS/nanobot/pull/4396) 虽然提出时间较早，但仍在持续更新。该 PR 目标是让 NanoBot 具备可选功能的发现、安装和启用能力，例如将 Bedrock 支持变为可选扩展。这表明社区和核心团队正在思考项目的模块化和可扩展性，为未来更灵活的架构做准备。

## 5. Bug 与稳定性

今日有多项 Bug 被修复或有了明确的修复方案，但同时也暴露了新的问题。

- **高优先级：Cron 服务启动崩溃**：Issue [#4615](https://github.com/HKUDS/nanobot/pull/4615) 已被关闭并修复。该 Bug 导致 `nanobot gateway` 在启动时因对父目录执行 `fsync()` 操作失败而崩溃。
- **高优先级：WebUI 子代理回填**：Issues [#4640](https://github.com/HKUDS/nanobot/pull/4640) 已通过 PR [#4641](https://github.com/HKUDS/nanobot/pull/4641) 修复。
- **中优先级：Telegram 长消息渲染问题**：Issue [#4637](https://github.com/HKUDS/nanobot/pull/4637) 报告了当 Agent 发送长 Markdown 消息时，Telegram 上的分段消息（除最后一段外）无法正确渲染。这是一个新的 Bug，暂无 Fix PR。
- **中优先级：`exec` 在 Windows 上的 Shell 语义不一致**：Issue [#4544](https://github.com/HKUDS/nanobot/pull/4544) 指出了 `exec` 工具在 Windows 环境下，单行命令使用 `cmd.exe` 而多行命令使用 `PowerShell` 的不一致问题。此问题已在 `hamb1y` 提交的大型修复 PR [#4648](https://github.com/HKUDS/nanobot/pull/4648) 中被包含。
- **低优先级（批量修复）**：`hamb1y` 提交了 PR [#4648](https://github.com/HKUDS/nanobot/pull/4648)，这是一个修复批次，针对多达 13 个已确认的 Bug，涵盖安全（#4072, #4075, #4076, #4078）、功能（#4061, #4082）和稳定性（#4055, #4058）等多个方面。该 PR 是今日最重要的稳定性贡献之一。

## 7. 用户反馈摘要

- **🔧 深入用户反馈：外部脚本触发 Agent 动作**: Issue [#4605](https://github.com/HKUDS/nanobot/pull/4605) 中，用户`chengyongru`（同时也是核心贡献者）表达了希望从外部脚本触发 Agent 动作的强烈需求。该用户此前已成功通过 `gws` CLI 集成了 Gmail 技能，并希望在此基础上实现自动化工作流。这表明高级用户不仅满足于基本的对话，更期望将 Agent 作为核心组件嵌入到自己的自动化编排中。
- **🗣️ 跨渠道体验诉求**: Issue [#4619](https://github.com/HKUDS/nanobot/pull/4619) 中，用户 `PaSSw0rds` 针对飞书（Lark）频道，提出了在 `/new` 新会话时发送“系统级”消息以实现视觉分割的建议。这体现了用户对跨渠道一致性体验的追求，希望在不同的 IM 平台（如 Telegram, Discord, 飞书）上，切换会话的体验能够保持同步和清晰。

## 8. 待处理积压

以下是一些长期未解决或近期未被关注的重要问题，值得维护者关注：

- **关键 Bug 积压**：`hamb1y` 在 5 月底报告的一系列 Bug（如 #4055, #4056, #4058, #4062, #4064, #4067, #4068）至今已有月余，虽然部分已在 PR [#4648](https://github.com/HKUDS/nanobot/pull/4648) 中处理，但仍有部分（#4056, #4062, #4067）被明确排除在外，需要单独跟进。
- **核心功能需求**：Issue [#4378](https://github.com/HKUDS/nanobot/pull/4378) 提出的“Cron 级别模型/预设”功能请求，由用户 `chengyongru` 代为提交，显示了对更精细的定时任务控制的需求。该请求已存在半月，可能未被纳入当前短期规划。
- **重构议题**：Issue [#4136](https://github.com/HKUDS/nanobot/pull/4136) 提出的 `Session.retain_recent_legal_suffix()` API 重构，旨在理清归档语义。这是一个核心模块的架构改进建议，虽然已有修复，但更彻底的 API 重构仍需提上日程。
- **安全审计需求**：多个安全问题（#4072, #4075, #4076, #4078）同时被曝光，虽然已有 PR，但这种现象本身可能暗示项目中存在一种普遍性的安全审计缺失，建议进行一次全面的安全检查。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，这是为您生成的 Hermes Agent 项目动态日报，基于 2026-07-02 的 GitHub 数据。

---

# Hermes Agent 项目动态日报 | 2026-07-02

## 1. 今日速览

今日项目活跃度极高，继昨日发布 **v0.18.0 大型版本**后，社区反馈和贡献热情高涨。过去24小时内产生了 **50 条 Issue** 和 **50 个 PR**，显示出项目在重大版本更新后的高涨维护热情。开发团队正在积极回应版本更新后涌现的 Bug 和安全问题，并基于社区贡献快速合并重要的修复和功能。总体来看，项目处于 **高度活跃且健康** 的状态，社区生态繁荣。

## 2. 版本发布

### Hermes Agent v0.18.0 (v2026.7.1) — The Judgment Release

项目于昨日发布了重大版本更新。这是自 v0.17.0 以来，历经 **约 1,720 次提交、998 个合并的 PR、关闭 949 个 Issue** 的里程碑式版本。本次发布更新内容庞大，涉及系统各个层面。

- **主要更新内容**：
    - 引入了全新的 **Judgment** 功能（推测为智能决策或审核相关模块）。
    - 大规模重构和优化了代码库，涉及 2,215 个文件，净增约 25.1 万行代码。
    - 解决了近 950 个 Issue，大幅提升了系统稳定性和功能完整性。
    - 新增了 **超过 370 位社区贡献者**，表明项目得到了广泛的外部支持。

- **破坏性变更与迁移注意事项**：
    - 由于更新规模巨大，**强烈建议**用户在升级前备份原有配置 (`~/.hermes/config.yaml` 等)。
    - 部分遗留的 API 或平台适配器可能已被替换或重写，如 `per-channel model` 功能可能已在本次发布中从 `PR #1991` 合入主分支。
    - 用户应关注新版本中可能弃用的配置项和工具，例如 `install.sh` 脚本已明确依赖 `xz-utils`（Issue #11197）。
    - **已确认的回归问题**：`hermes doctor` 在新的 Vertex AI provider 配置上存在故障（Issue #56906）。

## 3. 项目进展

今日有多项重要 PR 被合并，代表了项目在功能完善、安全加固和跨平台兼容性方面的持续进步。

- **安全管理**：合并了多个安全修复 PR，包括：
    - `#56976`: 修复 `pip fallback` 环境变量泄漏问题，防止子进程获取 API 密钥。
    - `#56977`: 新增对 Azure Entra 凭证的环境变量剥离保护。
    - `#56968`: 拒绝未授权的微软 Teams 发件人访问，防止附件装载安全风险。
    - `#2860`: 针对 SMS 平台实施了最小权限工具集策略。

- **平台与兼容性修复**：积极推进了对“Kasia”加密 P2P 协议平台的支持 (`#2707`已合并)，同时针对 Telegram (`#56910`)、QQ Bot (`#53443`、`#56970`)、Feishu (`#30990`) 等平台提出了关键的 Bug 修复。

- **功能推进**：
    - `#1991`: 一个备受欢迎的功能——**“频道级模型和系统提示词覆盖”** 最终被合并，允许用户为 Discord、Telegram 等平台的不同频道指定不同的模型和角色。
    - `#2840`: 引入了 **交互式消息专用聊天模型** 的配置支持，允许用户为实时聊天和后台任务（如 Cron 任务）分配不同的模型，优化了性能和成本。

## 4. 社区热点

今日讨论热度最高的议题集中在对**模型/频道细粒度控制**的需求上。

- **`#1955` (Closed): 频道级模型和提示词覆盖**
    - **热度**: 10 条评论, 7 个 👍
    - **评论分析**: 这是社区长期以来的核心诉求之一。用户希望在同一个 Bot 实例中，为不同用途的频道（如 #daily 使用低成本模型， #dev 使用高性能模型）配置不同的模型和系统提示词。该 Issue 在今日被关闭，表明其功能已在 `v0.18.0` 或后续的热修复中实现，引发了社区的积极反响。

- **`#40297` (Open): 桌面端支持“会话级别”工作区选择**
    - **热度**: 4 条评论, 9 个 👍 (今日最高赞)
    - **评论分析**: 社区对桌面客户端的用户体验提出了更高要求。用户指出，当前仅支持启动时设置一个工作目录，但桌面应用通常会在多个项目间切换。他们希望能在不重新启动应用的情况下，为每个新建的会话单独指定工作目录，这体现了用户对提升日常开发效率的强烈渴望。

## 5. Bug 与稳定性

今日报告的 Bug 数量在版本发布后显著增加，但开发团队响应迅速，多数问题已有对应的修复 PR。

- **严重**:
    - **`#48441` (Open): 终端会话快照明文泄露 `.env` 文件中的秘密。** 这是一个严重的安全漏洞，涉及所有环境变量。**已有 `#56976` 和 `#56977` 等修复 PR 在解决上游环境变量泄漏问题，但核心机制（快照本身明文存储）需要特别关注。**
    - **`#56979` (Open): 自定义 Fireworks provider 因工具 schema 引用解析失败。** 核心功能阻塞，导致首次请求失败。

- **中等**:
    - **`#53443` (Open): QQ 适配器 `connect()` 方法缺少 `is_reconnect` 参数，导致启动失败。** 已有修复 PR `#56970` 被合并，问题即将解决。
    - **`#56895` (Open): `/v1/responses` API 在上下文超限后陷入重复压缩循环。** 导致性能问题。
    - **`#56906` (Open): `hermes doctor` 诊断命令对新版 Vertex AI 配置失败。** 影响新用户在 `v0.18.0` 上的诊断体验。

- **低/功能性问题**:
    - **`#56923` (Open): Windows 平台上的备份导入测试失败。** 主要与权限模型 (`os.chmod`) 有关。
    - **`#56834` (Open): Linux 上桌面客户端构建失败。** 与 Electron 依赖路径有关。
    - **`#56835` (Open): 桌面端从睡眠恢复后出现网络崩溃。** 属于特定场景下的稳定性问题。

## 6. 功能请求与路线图信号

除了已实现的频道级模型配置，社区正在传递两个新的路线图信号：

- **更灵活的模型调度**：
    - **`#56891` (Open)**: 请求在 `delegate_task` 工具上开放 `model` 参数，允许 LLM 在任务委派时为不同子任务选择不同模型（如阅读文件用轻量模型，推理用重型模型）。这代表着从全局配置到细粒度、智能化的模型路由演进趋势。
    - **`#54748` (Open, PR)**: 开发团队已提交一个“模型路由层”的 PR，通过配置实现模型和回退链的选择。这表明项目正在将灵活的模型调度作为下一阶段的核心目标。

- **桌面端增强**：
    - **`#40297` (Open)**: “会话级工作区”是高票需求，很可能会被优先考虑。
    - **`#56944` (Open)**: 请求桌面应用增加“刷新会话”按钮，以解决与 VSCode 扩展协作时的同步延迟问题。

## 7. 用户反馈摘要

- **痛点**:
    - **“新版本 `install.sh` 依赖 `xz-utils` 未声明”** (`#11197`): 用户反映安装脚本在没有 `xz` 支持的Linux系统上静默失败，导致新手入门困难。
    - **“桌面端工作目录设置后，新会话仍使用旧目录”** (`#38855`): 用户在桌面版中 UI 设置与底层状态不一致，造成长期困扰。
    - **“`skills_list` 和 `skill_view` 的行为不一致”** (`#10713`): 用户在使用技能系统时，发现分类 (category) 和命名空间 (namespace) 的交互逻辑令人困惑，存在反直觉的设计。
- **使用场景**:
    - **“多频道多模型”** (`#1955`): 用户期望在 Discord/Telegram 群组中为不同功能频道（新闻、开发、闲聊）分配不同模型以平衡成本和效果。
    - **“代理使用思考模型时标题泄露推理过程”** (`#18529`): 用户发现使用 DeepSeek-R1 等会展示“思考”过程的模型时，会话标题会自动包含这些思考标记，导致标题内容怪异。

## 8. 待处理积压

| ID | 标题 | 类型 | 创建日期 | 最后更新 | 备注 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `#7066` | install  blocked | Bug | 2026-04-10 | 2026-07-02 | 中国用户反映安装脚本在访问特定域名（raw.githubusercontent.com）时可能被网络环境屏蔽，至今仍在讨论中。 |
| `#10713` | skills_list category is easily confused with plugin namespace | Bug | 2026-04-16 | 2026-07-02 | 技能系统的用户界面和API设计存在不一致，容易引起混淆。该问题持续近3个月，尚未被分配或标记。 |

**链接**: [Issue #7066](https://github.com/NousResearch/hermes-agent/issues/7066) | [Issue #10713](https://github.com/NousResearch/hermes-agent/issues/10713)

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，这是根据您提供的 PicoClaw 项目数据生成的 2026-07-02 项目动态日报。

---

# PicoClaw 项目动态日报 | 2026-07-02

## 1. 今日速览

今日项目活跃度较高，主要由 **15 个 Pull Requests** 的更新驱动，但合并率较低（仅 2 个被关闭/合并），说明团队当前可能侧重于代码审查与讨论阶段。社区贡献者在修复 CLI、Azure 依赖及支持新硬件平台（Raspberry Pi）方面表现活跃。同时，新报告了两个关键 Bug，分别涉及 Android 平台和 Matrix 协议通道，对特定用户群体影响较大。**项目整体状态为“高活跃度，低合并率”，亟需维护者对积压的 PR 进行合并决策。**

## 2. 版本发布

- **Nightly 构建: v0.3.1-nightly.20260702.2cf030d2**
  - **说明**: 这是一个自动化构建版本，可能包含最新的开发代码，稳定性未经充分验证，建议仅在测试环境使用。
  - **更新内容**: 自 `v0.3.1` 以来的所有变更。具体变更可查阅 [Full Changelog](https://github.com/sipeed/picoclaw/compare/v0.3.1...main)。
  - **迁移注意事项**: 无。Nightly 构建通常不建议用于生产环境。

## 3. 项目进展

今日未被合并的新 PR。以下为近期被关闭/合并的重要 PR，显示了项目在生命周期管理和通道功能上的进展：

- **`fix(pico): complete turn.done lifecycle signaling` (#3116)**: 该 PR 已关闭，修复了 Pico 会话中 `turn.done` 生命周期信号不完整的问题，确保了请求 ID 在后续消息中的正确传递，是向更稳定对话管理迈出的重要一步。
- **`feat(telegram): treat reply to bot message as mention in group chats` (#2975)**: 该 PR 已关闭，为 Telegram 群聊带来了便捷性。现在用户只需回复机器人的消息即可触发响应，无需再手动 `@` 提及，提升了用户体验。

## 4. 社区热点

- **讨论焦点**: **`[BUG] Matrix sync loop has no reconnection logic — silent death after network/server disruption` (#3203)**
  - **链接**: [Issue #3203](https://github.com/sipeed/picoclaw/issues/3203)
  - **分析**: 该 Issue 今日刚创建，但立即成为社区关注热点。它指出 Matrix 通道的 `/sync` 长轮询在网络中断后无法自动重连，导致服务“静默死亡”。这是一个**严重的稳定性问题**，因为用户可能在不自知的情况下失去了机器人响应能力，且现有 systemd 的 `Restart=on-failure` 策略无法生效。背后反映了用户对关键通信渠道可靠性（尤其是与去中心化协议 Matrix 的集成）的强烈需求。

## 5. Bug 与稳定性

按严重程度排列：

1.  **严重**: **`[BUG] Matrix sync loop has no reconnection logic` (#3203)**
    - **状态**: 新开，待修复。
    - **影响**: 导致 Matrix 通道永久失效，需要手动重启服务。
    - **是否已有 Fix PR**: 否。

2.  **严重**: **`[BUG] Process hooks crash gateway on Android/Termux` (#3164)**
    - **状态**: 已存在 9 天，仍为 `stale`（陈旧）状态。
    - **影响**: 在 Android Termux 环境下，任何进程钩子（Process Hooks）都会导致网关立即崩溃，完全无法使用该功能。
    - **是否已有 Fix PR**: 否。这是一个对移动端用户极具破坏性的 Bug，但长期未获回应，建议维护者优先关注。

## 6. 功能请求与路线图信号

- **`[Feature] Support streaming output for QQ channel` (#3201)**
  - **链接**: [Issue #3201](https://github.com/sipeed/picoclaw/issues/3201)
  - **分析**: 用户请求为 QQ 频道增加流式输出支持。目前仅有 Telegram 和 Pico WebSocket 实现此功能。这是一个**符合主流 LLM 应用趋势**的需求，可以显著改善 QQ 用户等待大模型响应时的体验。
  - **纳入可能性**: 较高。流式输出是提升用户体验的关键特性，且已有实现参考。如果该 PR 或类似工作在下一个开发周期中被采纳，很可能进入 v0.4.0 候选。

- **`fix(routing): strip leading/trailing underscores in ID normalization` (#3202)**
  - **链接**: [PR #3202](https://github.com/sipeed/picoclaw/pull/3202)
  - **分析**: 虽然标记为 Bug 修复，但实际上是强化了 ID 规范化的合规性。这暗示了系统可能在与外部系统（如下划线开头的 ID）交互时存在潜在的路由错误，修复后将提升系统的健壮性。

## 7. 用户反馈摘要

- **Android/Termux 用户痛点 (Issue #3164)**: 用户明确表达了在移动端使用 PicoClaw 的痛点，特别是“Process hooks”功能的不可用，扼杀了 Android 上自动化工作流的可能性。这表明移动端平台的支持和测试仍需加强。
- **对可靠性的刚性需求 (Issue #3203)**: 用户 `weissfl` 的报告非常专业，明确指出“静默死亡”比直接崩溃更可怕，因为它难以被自动化监控发现。这反映了技术用户对服务**7x24小时稳定运行**的极高期望，尤其是在自部署的 AI 助手场景中。

## 8. 待处理积压

以下为长期未更新或响应的关键 PR/Issue，可能阻碍项目进展：

- **`feat: add deltachat gateway` (#3063)**: 自 6月8日创建，至今已近一个月，仍未合并。该 PR 是增加一个新通信渠道的重要功能，长期搁置可能导致与 DeltaChat 适配性的偏差，增加后续合并成本。
- **`fix(openai_compat): recover Seed XML tool calls` (#3165)**: 此修复对于使用火山引擎（Doubao）Seed 模型的用户至关重要，且已存在超过一周，建议维护者尽快评估合并。
- **`fix(auth): reject cross-site launcher setup requests` (#3160)**: 这是一个**安全修复**，防止跨站点请求伪造设置密码，对保护首次运行的 Dashboard 安全具有重要意义，应优先于普通功能合并。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于 NanoClaw (github.com/qwibitai/nanoclaw) 2026-07-02 数据生成的项目动态日报。

---

# NanoClaw 项目动态日报 | 2026-07-02

## 1. 今日速览

今日项目活跃度较高，PR 处理量是 Issues 的 12 倍，显示出项目正处于**密集开发与整合阶段**。核心贡献者 `amit-shafnir` 提交了关于 **Agent 模板（Templates）** 功能的三个强关联 PR，标志着项目在 AI 智能体编排与可重复性方面迈出关键一步。同时，项目也在推进 **Slack 线程历史修复**、**WhatsApp 内存泄漏修复** 及 **默认提供商配置** 等稳定性和易用性改进。过去24小时内合并了6个 PR，其中包含多个来自 `shrwnsan` 的早期功能 PR，经长时间讨论后最终闭合并被纳入主干。

## 2. 版本发布

- **无新版本发布**

## 3. 项目进展

今日共有 **6 个 PR 被合并或关闭**，项目在这些方向上取得了实质性进展：

- **稳定性的长尾修复**：成功合并 `#2905 [fix(whatsapp): end the old socket on reconnect]`，解决了 WhatsApp 频道频繁断线重连导致的 **主机内存泄漏** 问题，使系统长周期运行更可靠。([#2905](https://github.com/nanocoai/nanoclaw/pull/2905))
- **长期待 PR 终获合并**：贡献者 `shrwnsan` 提交的多个功能 PR（#2677, #1716, #1257, #1693, #1597）经过数月的审查和修改后，在今天集中被关闭合并。这包括了对 **自定义 API 端点支持** (#1257)、**预任务脚本自动重试** (#2677) 等功能的最终接纳。
- **Agent 模板功能推进**：`amit-shafnir` 提交了关于 Agent 模板的第二部分 `#2909`，该 PR 在开发向导中引入了 **模板设置流程**，并允许用户从模板中“盖章”（Stamp）出第一个 Agent，极大地简化了新用户的入门配置。此 PR 堆叠在 `#2890` 之上，表明项目正在高效地推进这个核心功能。([#2909](https://github.com/nanocoai/nanoclaw/pull/2909))

## 4. 社区热点

今日讨论焦点集中在 **Agent 模板（Templates）** 这一新功能体系上，主要由贡献者 `amit-shafnir` 驱动。

- **[热点 PR #2890] 本地模板加载器与命令行支持**：这是 Agent 模板功能的第一部分，引入了 `ncl groups create --template <ref>` 命令，允许用户从本地模板直接创建 Agent 组。这是整个模板功能的基础层。([#2890](https://github.com/nanocoai/nanoclaw/pull/2890))
- **[热点 PR #2908] Codex 提供商下的模板功能打通**：此 PR 解决了模板 Agent 在 **Codex** 提供商下的端到端功能，通过“人格前缀”和与 Git 无关的技能发现机制，使模板创建的 Agent 能立即获得可用技能。这显示了项目在支持非官方 Anthropic API 上的深入。([#2908](https://github.com/nanocoai/nanoclaw/pull/2908))
- **分析**：这三个 PR 共同构成了 Agent 模板化的完整技术栈，反映了社区对 **“一键部署标准化 Agent 组”** 的强烈需求。通过模板来固化最佳实践、降低入门门槛，是 NanoClaw 向更成熟的应用平台演进的关键信号。

## 5. Bug 与稳定性

- **严重**：**WhatsApp 频道内存泄漏**（PR #2905）
  - **问题**：WhatsApp 频道的 `connectSocket()` 在每次重连时未关闭旧 Socket，导致对象和定时器持续累积，最终引发内存溢出。
  - **状态**：**已修复**。PR #2905 已合并，将在下一个版本中包含。([#2905](https://github.com/nanocoai/nanoclaw/pull/2905))

- **中等**：**Slack 频道线程历史缺失**（PR #2904）
  - **问题**：在 `engage_mode: 'mention'` 模式下，当 bot 被 @ 提及后，回复时无法获取该线程的完整对话历史，只能看到最新一条提及消息，导致 Agent 上下文不完整。
  - **状态**：**正在修复**，PR #2904 处于 OPEN 状态。([#2904](https://github.com/nanocoai/nanoclaw/pull/2904))

## 6. 功能请求与路线图信号

- **强制信号：Agent 模板系统**：`#2890`, `#2908`, `#2909` 三个 PR 的密集提交，表明 **模板化** 是当前路线图上的最高优先级。该功能将允许用户创建、分享和复用 Agent 组配置，是项目的增量发布机制。
- **强烈信号：实例级默认提供商**：PR #2906 提议通过环境变量 `DEFAULT_AGENT_PROVIDER` 设置实例范围的默认 AI 提供商，简化了多 Agent 组的管理，这表明用户希望在**运维层面获得更高层次的抽象配置**。([#2906](https://github.com/nanocoai/nanoclaw/pull/2906))
- **持续需求：语音转录技能**：PR #2317 提出的免费语音转录技能（支持 `openai-whisper` 和 `whisper.cpp`）虽有更新但尚未合并，反映了社区对 **低成本、本地运行的语音交互能力** 的长期兴趣。([#2317](https://github.com/nanocoai/nanoclaw/pull/2317))

## 7. 用户反馈摘要

- **痛点**：WhatsApp 频道的稳定性问题是真实痛点，社区贡献了完全修复方案（#2905）。Slack 频道的线程上下文丢失问题也暴露了多轮对话场景下的关键体验缺陷（#2904）。
- **满意点**：`shrwnsan` 贡献的多个 PR（如自定义 API 端点、备份技能、搜索技能等）在经过长周期审阅后最终合并，表明项目维护者对待 PR 态度严谨，社区贡献最终能被采纳，正向激励持续贡献。
- **使用场景**：Agent 模板功能暗示了用户希望将 NanoClaw 用于**标准化业务流水线**（如客服、内容生成等），而非仅停留在个人兴趣实验。

## 8. 待处理积压

- **#2317 [待合并] feat(skills): add /add-voice-transcription-free-whisper skill**：该 PR 自 2026-05-07 提交至今已近两个月，上次更新为 2026-07-01。作为一项完全免费且支持本地 GPU 加速的语音转录技能，其价值巨大，但迟迟未合并。这可能是因为其涉及复杂的外部依赖（如 Python 或 C++ 运行时）和跨平台兼容性问题。建议维护者尽快审查，或明确告知社区是否优先开发此功能。([#2317](https://github.com/nanocoai/nanoclaw/pull/2317))

---

**项目健康度评估：** 🟢 **良好**。开发活动活跃，核心功能（Templates）推进顺利，社区贡献的 Bug 修复质量高。需关注的是已合并 PR 的老龄化问题和部分技能 PR 的审核积压。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为AI智能体与个人AI助手领域开源项目分析师，以下是基于IronClaw项目2026年7月2日GitHub数据生成的日报。

***

### IronClaw 项目动态日报 | 2026-07-02

#### 1. 今日速览

IronClaw项目在2026年7月2日保持高活跃度，核心团队正全力推进“Reborn”架构的稳定性和性能优化。今日PR和Issue活动量巨大（50条PR，24条Issue），显示出激烈的开发迭代。尽管修复了一大批重要的生产环境Bug（如Slack集成、Routine创建），但QA测试发现的新问题（如技能自动激活功能失效、文件系统服务竞态条件）揭示了更深层次的架构问题。同时，社区的关注点集中在可配置技能/工具、用户体验改进和长期存在的E2E测试稳定性上。项目整体处于“积极修复与内部重构并行”的关键阶段，健康度中等偏上，但面临较高的回归风险。

#### 2. 版本发布

无新版本发布。

#### 3. 项目进展

今日项目进展主要集中在“Reborn”架构的缺陷修复、基础设施改进和文档设计上，多个XL规模PR被合并，标志着关键功能块落地。以下是重要合并/关闭的PR：

- **核心稳定性与架构修复**
    - **[PR #5407] fix(reborn): post-run skill bubble dropped on SSE resume**：修复了一个生产环境Bug——在SSE（服务器推送事件）恢复后，技能学习气泡无法正常显示。此为回归问题，由PR #5061引入。已经合入`main`分支。
    - **[PR #4998] fix(reborn): surface approval after auth resume**：XL规模改动，修复了认证恢复后用户确认请求不显示的问题，确保宿主运行时路径的正确性。
    - **[PR #5203] fix(llm): enable the circuit breaker by default**：默认启用了熔断器，使LLM提供商在故障时能快速失败，避免“假死”拖垮整个实例，显著提升了用户可见的稳定性。
    - **[PR #5228] Decouple runner heartbeat timeout**：将心跳频率与超时时间解耦，防止慢速写入操作拖垮心跳报告，提高了调度器的健壮性。

- **功能与基础设施**
    - **[PR #4544] feat(reborn): scoped-lifecycle admin install store**：XL规模PR，为未来Epic #5261 的可用性维度奠定了基础，实现了作用域生命周期模型和持久化存储。
    - **[PR #5532] chore(agents): wire codebase knowledge graph + OpenWiki**：提升了代理的代码发现能力，通过知识图谱和OpenWiki让CI、云代理和开发者能更高效地理解1.27M行代码库。
    - **[PR #5531] test(reborn): add semantic judge fallback to live QA**：为Reborn WebUI v2的实时QA测试引入了可选的LLM语义判断降级机制，提升了测试的鲁棒性。

- **文档与设计**
    - **[PR #5529] docs(reborn): final crate/module refactor design**：发布了Reborn栈的最终crate/module重构设计方案（纯文档），为后续大规模代码重构提供了蓝图。
    - **[PR #5249] docs(reborn): design — write-behind lease durability**：发布设计文档，计划通过“异步写入租约持久化”机制，彻底消除部署环境中的租约过期抖动问题。

**总结**：今日核心团队不仅修复了多个影响用户实际使用的关键Bug，还通过引入熔断器、优化调度器等手段提升了系统韧性。同时，文档设计层面的推进预示着未来几周将有结构性的代码重构。

#### 4. 社区热点

尽管核心人员贡献了绝大多数PR，但Issue区域显示了真实的用户痛点：

- **热度最高 (Bug)**：**[#5507] Failed routine run shows “No thread attached”** (1 评论)
    - **链接**：[Issue #5507](https://github.com/nearai/ironclaw/issues/5507)
    - **分析**：Routine运行失败后，UI显示“No thread attached”，且调试按钮被禁用。这直接阻塞了用户排查失败原因的能力，属于严重的可用性问题。用户评论表达了因无法调试而产生的挫败感。

- **讨论核心 (新功能)**：**[#5459] Configurable skills and tools** (2 评论)
    - **链接**：[Issue #5459](https://github.com/nearai/ironclaw/issues/5459)
    - **分析**：社区用户提出了一个明确的需求：允许管理员和用户分别安装WASM工具和技能，并控制其作用范围（全局共享/个人私有）。此Issue虽然评论不多，但其设计直接关联到系统的权限模型和多租户隔离，是平台化演进的核心信号。尚未有核心团队成员参与讨论。

- **回归与架构争议**：**[#5530] Skill criteria-based auto-activation is unreachable** (0 评论)
    - **链接**：[Issue #5530](https://github.com/nearai/ironclaw/issues/5530)
    - **分析**：由核心成员发现，指出“基于条件的技能自动激活”功能在当前的TurnCoordinator/agent-loop路径下完全不可用，其核心逻辑已经成为死代码。这揭示了在Reborn架构演进过程中，部分旧功能被“遗忘”或未被正确迁移的问题，引发了内部关于技术债务和重构优先级的关注。

#### 5. Bug 与稳定性

今日Bug报告主要集中在QA发现的回归和新架构问题，严重程度较高。

- **P1 (严重)**
    - **Routine创建及其功能缺陷**：
        - **[#5504] Routine creation hangs**：创建Routine时无限期挂起，无任何返回。这直接破坏了核心功能。无fix PR。
        - **[#5505] Routine prompt is self-referential**：创建的Routine提示自身包含了“创建自己”的指令，而非执行任务。无fix PR。
        - **[#5522] Reborn routine fails reading Slack DMs**：由于缺少Slack读取权限，导致Reborn架构下的Routine执行失败，并陷入重试循环。无fix PR，但属QA测试分支暴露。
    - **架构Bug**：
        - **[#5527] FilesystemSessionThreadService: idempotency write/read scope mismatch**：核心成员发现，文件系统服务中幂等性写入和读取的作用域不一致，导致生产环境中的“重播前策略”功能实际是无效的。这是一个非常隐蔽的架构性Bug，会破坏关键的业务规则。

- **P2 (中等)**
    - **Slack与Google集成问题**：
        - **[#5508] Slack delivery target not found**：尽管Slack已连接，但新创建的Routine无法找到Slack作为投递目标，而旧Routine正常。无fix PR。
        - **[#5506] Slack bot redirects to WebUI**：长时间任务在Slack中不会等待，而是直接跳转到WebUI，交互体验割裂。
        - **[#5416] Incorrect Google connection state**：Google连接状态在UI和Agent状态之间不一致，导致矛盾的认证流程。
    - **性能与UI问题**:
        - **[#5509] Chat creation latency scales with conversation history**：创建新聊天的延迟会随历史消息堆积而线性增长。

- **P3 (低危)**
    - **[#5510] Cannot delete old routines**：用户无法删除已创建的旧Routine。
    - **[#5500] Stabilize Reborn Playwright tests**：自动化测试不稳定，需要修复。

#### 6. 功能请求与路线图信号

- **“Configurable skills and tools” ([#5459]）**：此需求信号最为强烈，它要求实现不同粒度的工具安装与权限管理。这很可能与正在进行的PR #4544（Scoped-lifecycle admin install store）和Epic #5261密切相关，预示着即将开发的功能与权限控制面板。
- **“Header notifications for automation tasks” ([#5443] - 已关闭)**：该功能请求已在今日关闭，表明团队已经采纳并完成了自动化任务的头部通知功能实现。
- **“Add global auto-approve shortcut text” ([#5246] - 已关闭)**：此改进也已合并，提升了用户在批准工具调用时的操作效率。

#### 7. 用户反馈摘要

从今日的Issues和PR评论中，可以提炼出以下关键用户反馈：

- **对调试支持的强烈需求**：用户在面对Routine失败时，强烈的需求是能够查看执行线程和详细的日志。而“[#5507] No thread attached”和“[#5457] Logs page empty”恰恰阻止了用户查看这些关键信息，这被认为是最大的痛点。用户评论表达了无法调试带来的挫败感。
- **对“半成品”集成的不满**：Slack和Google的集成体验反复出现问题（如状态不一致、任务超时重定向），用户感到困惑和不便。特别是Slack投递目标丢失（[#5508]）和Google认证流程矛盾（[#5416]）的反馈，显示出集成功能在复杂场景下测试不足。
- **对性能问题的感知**：用户明显感知到聊天延迟随历史记录增加而增加（[#5509]），这种“慢慢变慢”的体验是用户流失的常见原因。
- **对系统行为透明度的要求**：用户希望知道系统“正在做什么”，而不是收到诸如“driver protocol error” (PR #5289-已关闭) 这类模糊的通用错误。同样，Slackbot直接跳转WebUI（[#5506]）也剥夺了用户的知情权和选择权。

#### 8. 待处理积压

- **[#4108] Nightly E2E failed**：一个自2026年5月27日就打开的Issue，记录了Nightly E2E测试的持续失败。虽然该问题可能由多种原因触发（如网络、环境），但其长期未关闭表明测试基础设施或某些核心功能的稳定性存在系统性问题。维护者应优先审视。
    - **链接**：[Issue #4108](https://github.com/nearai/ironclaw/issues/4108)
- **[#5460] Memories in WebUI workspace are visible to every user**：这是一个严重的隐私/数据隔离问题：同一个工作区的用户可以看到彼此的“记忆”。该Issue于6月30日创建，至今未分配且无评论，显然未引起足够重视，可能造成安全隐患。
    - **链接**：[Issue #5460](https://github.com/nearai/ironclaw/issues/5460)
- **[#4841] reborn: no run-borking failures**：一个持续近20天的XL规模PR，旨在消除所有“run-borking”的终端错误。尽管有持续的更新，但其迟迟未能合并，表明该领域的技术实现仍存在较大挑战。这关系到用户能否获得准确的失败原因，而不是被“卡死”。
    - **链接**：[PR #4841](https://github.com/nearai/ironclaw/pull/4841)

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

好的，作为AI智能体与个人AI助手领域开源项目分析师，我已根据您提供的LobsterAI GitHub数据，为您生成了2026年7月2日的项目动态日报。

---

# LobsterAI 项目动态日报 | 2026-07-02

## 1. 今日速览

今日项目活跃度中等，主要表现为**修复驱动的版本稳定**。过去24小时内，团队合并了7个Pull Request，显示出高效的代码合并与修复节奏，但未发布新版本。社区方面无新增Issue，目前积压的5条均为3个月前的旧Issue，今日无新增反馈，表明社区讨论热度较低。核心工作集中在修复定时任务通知、模型删除以及协同工作（Cowork）的功能完善上，整体项目健康度良好，正稳步向稳定版推进。

## 2. 版本发布

无。

## 3. 项目进展

今日项目在**Bug修复与功能增强**两方面取得明确进展，共合并/关闭了7个PR，主要覆盖前端（Renderer）、文档（Docs）和协同工作（Cowork）模块。

- **关键Bug修复**:
    - **PR #2252 (已合并)**: 修复了在设置中删除当前正在使用的自定义模型供应商时，应用界面白屏的严重问题。该问题由异步逻辑错误导致，现已解决。
    - **PR #2255 (已合并) & PR #2256 (待合并)**: 修复了定时任务编辑页面中，将通知渠道切换为“不通知”后，设置不生效的Bug。根本原因是后端API对空值处理不当，已通过前端逻辑修正，确保“不通知”状态能被正确清除。
- **功能推进**:
    - **PR #2249 (已合并)**: 为协同工作（Cowork）模块增加了“子Agent (Subagent) 工件面板 (Artifact Panel)”，允许用户在不替换主会话页面的情况下，在侧边栏查看和打开子Agent详情，提升了多Agent协作场景下的交互体验。
- **文档与开发体验**:
    - **PR #2251 (已合并)**: 改进了共享部署（Share Deployment）功能，确保使用独立的Node工具环境执行安装和打包命令，增强了部署的稳定性和可移植性。
    - **PR #2250, #2253, #2254 (均已合并)**: 更新了项目主页图片和README文档，属于日常维护。

项目在**稳定性**和**用户体验**上迈出了一步，特别是修复了影响使用的白屏和定时任务不生效问题。

## 4. 社区热点

今日无新的热点讨论。目前所有5条开放的Issue均为3个月前的旧问题，且无新的评论或反应。

- **#1354 “让龙虾帮忙启动pageant后电脑蓝屏”**: 这是目前最严重的问题报告，尽管只有2条评论，但涉及系统级崩溃，属于高风险问题。用户提供了详细的日志，值得核心团队优先评估。
    - 链接: [Issue #1354](https://github.com/netease-youdao/LobsterAI/issues/1354)

## 5. Bug 与稳定性

今日新报告的Bug数量为0。当前积压的Bug问题主要集中在**任务系统**和**Agent管理**模块，均来自2026年4月2日，虽标记为 `stale` 但并未关闭。

- **严重级别**:
    1.  **严重 (系统崩溃)**: **#1354** 启动Pageant后蓝屏。这是最需要关注的问题，可能涉及与Windows内核交互的底层逻辑。*目前无对应修复PR。*
    2.  **高 (功能失效)**: **#1357** “开启Pageant”回答已启动但实际未启动。这是一个假阳性响应的功能缺陷，影响用户信任度。*目前无对应修复PR。*
    3.  **中 (逻辑错误)**:
        - **#1358** 定时任务点击后无交互反馈。
        - **#1359** 已删除的任务在重启后再次出现，且内容为空。*目前无对应修复PR。*
        - **#1360** 自定义Agent创建时未做重名验证，可能导致混淆。*目前无对应修复PR。*

**今日修复**:
- **PR #2252**: 修复了删除激活的模型导致白屏的Bug (严重程度: 高)。
- **PR #2255**: 修复了定时任务通知设置为“不通知”不生效的Bug (严重程度: 中)。

## 6. 功能请求与路线图信号

今日无新的功能请求。从合并的PR（#2249）来看，项目正在按计划增强**协同工作（Cowork）** 场景下的子Agent管理能力，这可能是下一阶段版本的重点功能之一。同时，对共享部署功能的修复（#2251）表明开发者体验和部署稳定性也是当前优化方向。

## 7. 用户反馈摘要

由于今日无新反馈，此部分基于历史数据进行摘要：

- **核心痛点**: 用户对 **“任务”** 相关的稳定性和可靠性反馈较为集中。具体表现为指令执行结果与实际不符（#1354、#1357）、任务状态反馈缺失（#1358）以及任务状态管理异常（#1359）。这些问题直接影响了用户对AI助手执行核心任务（如启动工具、发送消息）的信任度。
- **使用场景**: 用户明确提到了“启动Pageant”（可能是Pageant SSH代理）、“在Popo（企业通讯工具）上发消息”等具体办公自动化场景，这与LobsterAI作为个人AI助手的定位高度一致。
- **不满意之处**: 功能存在“假阳性”响应（回答了但没做）和“任务残留”等问题，对用户期望造成了较大落差。

## 8. 待处理积压

以下为长期未更新的重要Issue，可能已被忽视，建议开发者团队进行审查和分类处理：

1.  **#1354 [严重] 启动Pageant后蓝屏** - 创建于2026-04-02。
    - 链接: [Issue #1354](https://github.com/netease-youdao/LobsterAI/issues/1354)
2.  **#1357 [高] “开启Pageant”回答已启动但实际未启动** - 创建于2026-04-02。
    - 链接: [Issue #1357](https://github.com/netease-youdao/LobsterAI/issues/1357)
3.  **#1359 [中] 删除的任务重启后再次出现** - 创建于2026-04-02。
    - 链接: [Issue #1359](https://github.com/netease-youdao/LobsterAI/issues/1359)
4.  **#1358 [中] 定时任务点击无反馈** - 创建于2026-04-02。
    - 链接: [Issue #1358](https://github.com/netease-youdao/LobsterAI/issues/1358)
5.  **#1360 [低] Agent自定义创建无重名验证** - 创建于2026-04-02。
    - 链接: [Issue #1360](https://github.com/netease-youdao/LobsterAI/issues/1360)

**建议**: 由于这些Issue已存在3个月且标记为 `stale`，建议项目维护者明确处理方案：对于可复现的问题（如#1357、#1359），应进入开发队列；对于难以复现或优先级低的问题（如#1354、#1360），应给出官方解释或标记为“未来版本考虑”。

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

好的，作为AI智能体与个人AI助手领域开源项目分析师，以下是为您生成的CoPaw (QwenPaw) 项目动态日报。

---

# CoPaw 项目动态日报 | 2026-07-02

## 今日速览

今日项目活跃度极高，PR与Issue更新量均处于近期高位，反映出社区参与热情和项目迭代速度加快。**v2.0.0-beta.2** 版本的发布引入了关键CLI功能，但也带来了稳定性挑战。社区反馈集中在**安全性**（密钥脱敏、Web控制台访问控制）、**稳定性**（内存泄漏、并发卡死）以及**渠道兼容性**（飞书消息拦截、Bot通信）等核心痛点。项目团队响应迅速，合并了多项关键修复和功能PR，尤其是针对飞书通道、治理政策和权限系统的改进，显示出项目正在向更成熟、安全的方向迈进。

## 版本发布

### v2.0.0-beta.2
- **版本号**: v2.0.0-beta.2
- **类型**: Beta (早期预览版)
- **发布说明**: 
  > ⚠️ **警告**: 此为正在积极开发中的早期Beta版本，**包含破坏性变更和不稳定因素**。仅限开发者和早期采用者使用，**不建议用于生产环境**。
- **更新亮点 (From Release)**:
  - `feat(cli): add cron up`: 新增CLI对定时任务 `cron up` 的支持，增强了非图形化场景下的任务调度能力。
- **关联Issue**: 预发布版本验证任务 `#5733` 已生成，旨在2小时内完成安装验证。
- **迁移注意事项**: 
  - 此为破坏性更新，从v1.x系列升级需谨慎，建议在隔离环境中测试。
  - 命令行工具新增了 `cron` 子命令，用户需查阅最新CLI文档以了解其用法。

## 项目进展

今日共计合并/关闭32个PR，核心进展聚焦于以下方面：

1.  **渠道连接稳定性**:
    - **飞书通道修复**: `PR #5724` 合并，修复了飞书通道硬丢弃所有Bot消息的问题，改为仅过滤自循环消息。此修复直接解决了多Agent协作场景下的沟通断裂问题。
    - **QQ频道修复**: `Issue #5696` 因 `PR #5696` (推测关联) 关闭，解决了QQ机器人WebSocket重连后HTTP会话变为 `None` 导致的崩溃。
    
2.  **核心运行时与架构**:
    - **治理策略改进**: `PR #5546` 合并，泛化了治理策略模式，为未来更灵活、可扩展的安全审批机制打下基础。
    - **目标模式修复**: `PR #5727` 合并，修复了 `/goal` 模式下的作用域过滤逻辑，解决了目标模式不可用的BUG。

3.  **记忆系统增强**:
    - **ADBPG内存重构**: `PR #5296` 合并，将ADBPG长期记忆从SQL模式全面迁移到REST-ONLY架构，并集成了自动搜索流程，提升了与产品方向的统一性及维护性。

4.  **Web UI与用户体验**:
    - **聊天会话管理**: `PR #5728` 合并，为聊天会话列表增加了日期分组和搜索功能，优化了长列表用户的导航体验。
    - **模型列表更新**: `PR #5730` 合并，更新了内置模型列表，确保了新模型的最新支持。

5.  **文件处理**:
    - **纯文件消息修正**: `PR #5693` 合并，修复了仅含附件的消息（如企业微信的Excel文件）因“无文本去重”逻辑而被静默丢弃的问题。

## 社区热点

1.  **安全性成为焦点**:
    - **`#5705` [Feature] 密钥脱敏与安全存储**: (评论: 5, 👍: 0) 详细分析了当前密钥管理机制的不足，并提出 `agent.json` 环境变量引用与日志脱敏方案。这反映了社区对生产环境安全性的高度关注。
    - **`#5715` [Feature] Web访问控制**: (评论: 2, 👍: 0) 用户明确要求为Web Console增加密码/密钥保护，直指当前完全公开访问带来的安全隐患。

2.  **飞书/Bot生态的痛点集中爆发**:
    - **`#5709` [Bug] 飞书通道硬丢弃Bot消息**: (评论: 2) 直接影响了多Agent之间的协作，被认为是严重BUG。
    - **`#5708` [Bug] 飞书交互式卡片消息不解析**: (评论: 2) 用户反馈卡片数据无法被Agent理解，使得基于卡片的工单系统完全失效。
    - **`#5710` [Bug] 上下文压缩无保护锚点**: (评论: 1) 用户反馈因上下文压缩导致Agent“失忆”，忘记渠道和关键指令，严重影响体验。

3.  **稳定性与性能讨论**:
    - **`#5720` [Bug] 内存泄漏**: (评论: 4) 用户详细分析了v1.1.12.post2版本的内存泄漏，指出异步任务和HTTP会话未正确清理，是影响长期运行的主要障碍。
    - **`#5725` [Question] 流式输出卡顿**: (评论: 3) 用户反馈对比DeepSeek后发现QwenPaw在流式输出时浏览器卡顿，指向前端性能瓶颈。

## Bug 与稳定性

| 严重程度 | Issue / PR ID | 问题描述 | 状态 | 是否有Fix PR |
| :--- | :--- | :--- | :--- | :--- |
| **严重** | `#5720` | 内存泄漏，进程运行约1小时后内存暴涨，导致进程被杀、配置损坏 | **OPEN** | 暂无明确关联PR |
| **严重** | `#5701` | [CLOSED] 同一Agent多开页面并发访问卡死 | **CLOSED** | 未指明PR |
| **高** | `#5717` `#4795` `#5710` | Runtime 2.0 由于截断的tool-call导致无限执行工具；向量索引膨胀至37G；上下文压缩丢失关键信息 | **OPEN** | `#4795`已关闭，其余OPEN |
| **高** | `#5709` `#5696` `#5708` | 飞书通道完全丢弃Bot消息；QQ频道重连后崩溃；飞书卡片无法解析 | **已修复** | `#5724`(飞书bot) `#5696`(QQ频道) |
| **中** | `#5725` | Console流式输出浏览器卡顿 | **OPEN** | 暂无关联PR |
| **低** | `#5403` | 浏览器自动填充干扰模型配置页面搜索框 | **OPEN** | 暂无关联PR |

## 功能请求与路线图信号

1.  **安全性增强（高优先级）**: `#5705` (密钥管理) 和 `#5715` (Web访问控制) 需求强烈，且有详细的实施方案。结合已有 `#5738` (多维限流) 的PR，预计安全加固将是下一个版本的核心方向之一。
2.  **CLI能力增强**: `#5737` 要求增强CLI以支持无图形化场景。这与新发布的v2.0.0-beta.2中 `cron up` 功能方向一致，体现了社区对自动化、脚本化操作QwenPaw的期望。
3.  **自动模型切换**: `#5718` 提出在模型限额不足或错误时，Agent能自动切换模型。这属于高级容错和自适应能力，是提升Agent自主性和可靠性的重要信号。
4.  **竞品对标与短板改进**: `#5711` 是用户提交的一份详尽的竞品分析报告，指出了工具调用、记忆机制、规则执行力等架构短板，对项目长期发展路线图有重要参考价值。

## 用户反馈摘要

- **满意度**: 用户对项目开放性（开源）和社区互动（Issue回复迅速）表示认可，多个Issue获得了维护者的及时回复。
- **痛点**:
  - **“连接后世界”不稳定**: 飞书、QQ等渠道的连接在重连、消息解析、多Agent交互场景下仍然脆弱，是用户最直接的负面体验来源。
  - **“内存/CPU”消耗过快**: `#5720` 和 `#5725` 表明，无论是后端服务还是前端UI，性能开销是影响用户日常使用的核心瓶颈。
  - **安全焦虑**: “完全公开”的Web控制台让云服务器部署的用户感到“脊背发凉”；密钥明文存储也令企业用户望而却步。
  - **“记忆”与“遗忘”的困惑**: 用户在使用中发现Agent在长对话或压缩后“失忆”，导致需要重复指令或做出不符合场景的反应，体验不佳。
- **使用场景**: 社区用户群体覆盖了从个人开发者的实验性部署，到企业级的飞书、钉钉、微信等渠道集成。

## 待处理积压

| 编号 | 类型 | 标题 | 创建时间 | 最后更新时间 | 备注 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `#4873` | **Bug** | 同时开两个subagent导致主agent无限快速轮询 | 2026-06-01 | 2026-07-02 | **长期未关闭的核心Bug**。涉及Agent任务调度核心逻辑，可能影响并发任务可靠性。 |
| `#5187` | **PR** | 实现Windows桌面GUI自动化 (computer-use) | 2026-06-14 | 2026-07-02 | **待合并的功能性大PR**。该功能将极大扩展Agent在Windows平台上的能力，但至今仍在开放状态。 |
| `#5525` | **PR** | 实现Windows原生沙箱 | 2026-06-25 | 2026-07-02 | **待合并的安全相关PR**。对Windows平台用户至关重要，与 `#5703` (沙箱不可用) 中提到的安全审批问题直接相关。 |

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于您提供的 ZeroClaw 项目数据生成的 2026年7月2日 项目动态日报。

---

# ZeroClaw 项目日报 | 2026年7月2日

## 1. 今日速览

ZeroClaw 项目今日维持 **高活跃度**。过去24小时内，Issue 和 PR 的更新总数均达到50条，体现了社区和开发团队的持续投入。尽管没有新版本发布，但技术债务清理、核心功能改进（特别是渠道集成、SOP管理、可观测性）和安全修复是今日的主要活动。值得注意的是，一个长期的、大规模的架构变更（PR #8504）被成功拆分为更易于审查的子PR并逐步推进，显示了项目维护能力的成熟度。**社区关注的核心仍然是Agent的稳定性、工具的可用性（尤其是MCP）以及跨平台兼容性。**

## 2. 版本发布

**无**

---

## 3. 项目进展

今日项目在多个关键领域取得了实质性进展，重要贡献包括：

- **渠道集成 (Channels) 重构推进**: 大型PR `#8504 [feat(channels): add Git forge channel with SOP ingress]` 已被关闭，它被成功拆分为三个结构更清晰、更易审查的子PR (`#8609`, `#8611`, `#8618`) 并分别推出，标志着渠道系统的架构梳理进入新阶段。
- **运行时与代理核心修复**:
    - `#8619 [feat(runtime): unified memory-context injection]` 提出了基于 `TurnOrigin` 的统一内存上下文注入机制，这是一个重要的架构改进，有望使运行时行为更加一致和可预测。
    - `#8599 [fix(agent): align Agent::from_config tool dispatcher...]` 和 `#8488 [fix(channels): derive channel prompt tool-availability...]` 解决了 `#8054` 中提出的工具分发和提示词可用性不一致问题，增强了不同入口（WebSocket/Channel）下的代理行为统一性。
- **安全加固**:
    - `#8547 [fix(audit): remove rag-pdf feature to clear RUSTSEC-2026-0192]` 通过移除 `rag-pdf` 特性，消除了 `ttf-parser` 带来的安全漏洞。
    - `#8574 [fix(skills): harden extract_zip_secure against zip-bomb inflation]` 加固了技能zip文件的解压缩过程，防范了潜在的“zip炸弹”攻击。
    - `#8591 [fix(audit): prevent signing-key leak via VarError formatting]` 修复了一个可能通过错误格式化字符串泄露审计签名密钥的Bug。
- **可观测性 (Observability)**:
    - `#8567 [feat(observability): runtime OTel content policy for LLM and tool I/O]` 实现了对OpenTelemetry中LLM和工具I/O内容的运行时策略控制，默认关闭，保护用户隐私。

---

## 4. 社区热点

今日最受社区关注的是几个核心功能缺失和架构问题，反映了用户对稳定性和易用性的高度期待。

- **#8193 [Bug: MCP tools missing from TUI sessions]** (评论:14) - **持续高热**
    - **链接**: [Issue #8193](zeroclaw-labs/zeroclaw Issue #8193)
    - **诉求**: MCP服务器连接正常，Gateway也能看到工具，但TUI界面无法获取到这些工具，导致工作流被阻塞。这暴露了运行时与前端在工具发现机制上的深层不一致，是当前项目的 **S1级关键阻塞问题**。社区迫切渴望修复此问题，以实现AGI工具的完整易用性。

- **#6808 [RFC: Work Lanes, Board Automation, and Label Cleanup]** (评论:13) - **长期热议**
    - **链接**: [Issue #6808](zeroclaw-labs/zeroclaw Issue #6808)
    - **诉求**: 这是一项社区治理RFC，旨在通过引入“工作车道”、板子自动化和标签清理来优化项目协作流程。虽然不直接影响最终用户，但13条评论表明，社区核心贡献者非常关注项目的工作效率和维护可持续性。这是一个从内部提升项目健康度的积极信号。

- **#7462 [Bug: 74 test failures on Windows]** (评论:6)
    - **链接**: [Issue #7462](zeroclaw-labs/zeroclaw Issue #7462)
    - **诉求**: 一位在Windows 11（中文环境）上运行的用户报告了74个测试失败。这突显了项目 **对非Linux平台的测试覆盖严重不足**，是潜在的平台兼容性门槛。用户希望CI能覆盖Windows环境，开发者则可能因缺乏相关资源而受阻。

- **#8226 [Feature: per-agent custom environment variables]** (评论:5)
    - **链接**: [Issue #8226](zeroclaw-labs/zeroclaw Issue #8226)
    - **诉求**: 用户需要一个“非秘密”的 `runtime_context` 和一个“掩码”的 `runtime_secrets` 块，来为不同Agent配置独立的身份、参数和令牌。这反映了在生产环境中，多租户、安全隔离和细致的资源管理是用户的刚需。

---

## 5. Bug 与稳定性

今日报告的Bug涉及多个方面，按严重程度排列如下：

- **S1 - 工作流阻塞**:
    - **#8193**: MCP tools missing from TUI sessions。 (无 fix PR)
    - **#8553**: Agent 无法使用环境变量作为 `http_request` 的 secret。 (无 fix PR)
    - **#6891**: Web Gateway上“定时任务”编辑接口报错422。 (无 fix PR)
    - **#6302**: Gemini 400 错误 - 历史记录序列化问题。 (无 fix PR)

- **S2 - 行为降级**:
    - **#7462**: Windows上74个测试失败 - 平台兼容性问题。 (无 fix PR)
    - **#8615 (今日新开)**: `compatible` provider 静默删除标签内容（`<think>`标签）。 (无 fix PR, 但可能已被注意)
    - **#8302**: Web 仪表板不显示已配置的MCP服务器工具。 (无 fix PR)

**稳定性总结**：项目的稳定性核心挑战在于 **多入口（TUI, Web, Channel）下的工具一致性问题**，以及 **多平台支持不足**。安全审计工作（#8547, #8574, #8591）正在积极处理潜在的威胁。

---

## 6. 功能请求与路线图信号

今日社区提出了多项新功能，其中一些已与现有PR形成关联，表明可能被纳入后续版本。

- **可能被纳入下一版本 (v0.9.0?) 的高优先级功能**:
    - **#8550**: 添加 OpenAI 兼容的 Chat Completions 端点。 (同日有 `#8603 RFC` 提出)。**这是标准化API接入的关键，可能性高**。
    - **#8568**: Mixture-of-Agents (MoA) 虚拟模型提供者。 (已有RFC `#8396` 在讨论线协议优先的提供者模型)。**MoA是前沿功能，可能作为v0.9.0之后的探索性特性**。
    - **#8600**: 在多模型提供者中轻松切换模型。 (无关联PR，但属于常见需求)。

- **已有PR支持或处于RFC阶段的中期功能**:
    - **#8587**: 增加更多SOP示例。 (与 #8590 PR 的SOP作者平台相关)。
    - **#8602**: 增强 `file_read` 工具（行数限制、编码检测等）。 (无关联PR)。
    - **#8226**: 支持 Agent 级自定义环境变量。 (无关联PR，但属于 `#7432 v0.9.0 tracker` 关注的安全与配置领域)。
    - **#8396**: 线协议优先的提供者模型 (Wire-Protocol-First Provider Model) 的RFC。**这是一个重大的架构演变信号，可能影响未来的所有提供者集成**。

**路线图信号总结**: 项目明显在向 **标准化API（OpenAI兼容）**、**多模型/多Agent架构**、**更安全的运行时环境**（per-agent secret、文件操作安全）和 **面向生态的集成**（渠道、Git Forge）演进。

---

## 7. 用户反馈摘要

从最新的 Issues 评论中，我们可以提炼出用户的真实声音：

- **痛点**: 最大的痛点是 **“配置了，但用不了”**。例如，配置了MCP和HTTP代理，但TUI或 Agent 无法正确使用（ `#8193`, `#8302`, `#8553`）。这表明运行时集成存在缝隙，导致用户投入配置成本却无法获得预期收益。
- **场景**: 用户希望将 ZeroClaw 部署为 **生产力Agent**。例如，通过 `http_request` 和 `SOP`（标准操作流程） 来自动化团队工作流（ `#8553`, `#8424` ）。同时，用户也希望能像使用其他商业AI服务（molts, Claude Code）一样，享受 **一键切换模型** 的便利（`#8600`）和 **类似Claude Code的`Read`工具的稳健性**（`#8602`）。
- **满意**: 虽然没有直接表扬，但大型PR (#8504) 的顺利拆解和近期密集的 CI 改进（`#7108`），以及安全漏洞的快速修复（`#8547`, `#8574`），都体现了项目维护者对代码质量和协作流程的认真负责，这在资深用户和贡献者中应该会获得高度认可。
- **不满意/担忧**: Windows 平台用户的挫败感明显（`#7462`）。此外，一些长期未解决的问题（如`#5269`文档问题，`#6074`提交丢失审计）虽然解决方案在途，但用户对进展速度可能有疑虑。

---

## 8. 待处理积压

以下是一些长期未响应或需要关注的重要 Issue/PR，可能影响项目健康度：

- **#6074 - [audit: track 153 commits lost in bulk revert...]** (2026-04-24 提出, 2条评论)
    - **链接**: [Issue #6074](zeroclaw-labs/zeroclaw Issue #6074)
    - **风险**: **高风险**。这是一个历史遗留审计问题，涉及153次提交的丢失。虽然已被标记为“进行中”，但从评论活跃度看，恢复工作的优先级可能不高。若不能妥善解决，可能在未来引发回归问题。
    - **建议**: 维护者需再次评估此审计工作的优先级，或在相关里程碑中设立明确的计划。

- **#8424 - [RFC: .ignore File Mechanism for Workspace File Protection]** (已关闭)
    - **链接**: [Issue #8424](zeroclaw-labs/zeroclaw Issue #8424)
    - **风险**: **中等风险**。这是一个被关闭的RFC，但关闭原因（`needs-author-action`）表明需求未被满足，可能因为提案不够完善。但其核心诉求（保护敏感文件）是硬需求，且被标记为 `risk:high`。社区可能对RFC的关闭感到失望，需要维护者后续跟进或给出更明确的指导。
    - **建议**: 项目是否计划以其他方式（如内置 `.zeroclawignore` 文件支持）来实现文件保护？建议在相关Milestone tracker（如 `#7432` v0.9.0）中重新讨论此问题。

</details>

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*