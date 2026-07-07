# AI 开源趋势日报 2026-07-07

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-07-07 03:51 UTC

---

好的，作为专注于 AI 开源生态的技术分析师，我为你呈上 2026-07-07 的《AI 开源趋势日报》。

---

### **AI 开源趋势日报 | 2026-07-07**

#### **1. 今日速览**

今日 AI 开源社区呈现出三大核心动向：第一，**“Agent Skills”生态爆发**，围绕 Claude Code、Codex、Gemini 等编程 Agent 的技能插件（Skills）项目出现井喷，成为今日增长最快的细分领域；第二，**本地化、隐私优先的 AI 工具备受青睐**，无论是会议助手还是个人知识管理，都强调离线运行和数据自主可控；第三，**“Prompt泄露”成为一个独特的公开数据集类别**，专门收集各大模型系统提示词的项目获得了极高的关注度，体现了社区对模型行为透明度的兴趣。

---

#### **2. 各维度热门项目**

##### 🔧 **AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）**

- **alibaba/zvec** ⭐13,586 (+382 today)
  [链接](https://github.com/alibaba/zvec)
  阿里开源的轻量级、高性能进程内向量数据库。相较于外部数据库服务，它提供了极致的低延迟，非常适合对延迟敏感的 AI 应用场景，如实时 RAG 和 Agent 内部记忆。

- **firecrawl/firecrawl** ⭐146,451 (+867 today)
  [链接](https://github.com/firecrawl/firecrawl)
  规模级网页搜索、抓取与交互 API。它为 AI Agent 提供了访问和理解互联网的“手和眼”，是构建 Agent 工作流的核心基础设施，社区热度持续高涨。

- **ogulcancelik/herdr** ⭐0 (+779 today)
  [链接](https://github.com/ogulcancelik/herdr)
  终端里的“Agent 多路复用器”。它解决了多 Agent 开发测试中的一个痛点：在同一终端会话中高效管理、切换和编排多个 Agent 的输入输出，提升开发效率。

- **steipete/CodexBar** ⭐0 (+598 today)
  [链接](https://github.com/steipete/CodexBar)
  一个 macOS 菜单栏工具，无需登录即可直观展示 OpenAI Codex 和 Claude Code 的使用量统计。对于重度依赖这些工具的开发者来说，是管理 API 成本和使用量的实用小工具。

##### 🤖 **AI 智能体/工作流（Agent 框架、自动化、多智能体）**

- **addyosmani/agent-skills** ⭐0 (+1112 today)
  [链接](https://github.com/addyosmani/agent-skills)
  为 AI 编码 Agent 提供生产级工程技能的 Skill 集合。这标志着 AI Agent 开发从“能跑”向“跑得稳、跑得好”进化，提供了经过验证的最佳实践和技能库。

- **alirezarezvani/claude-skills** ⭐0 (+610 today)
  [链接](https://github.com/alirezarezvani/claude-skills)
  一个庞大的 Agent Skills 合集，包含 330+ 技能，覆盖工程、营销、产品、合规、研究等多个领域。它是“Agent Skills”生态爆发的一个缩影，为 Claude Code 等 Agent 赋予了几乎任何领域的专业能力。

- **openai/codex-plugin-cc** ⭐0 (+906 today)
  [链接](https://github.com/openai/codex-plugin-cc)
  OpenAI 官方出品，让 Claude Code 可以调用 Codex 进行代码审查或任务委托。这是不同 AI 生态间协作的标志性项目，展示了 Agent 互操作性的未来方向。

- **mvanhorn/last30days-skill** ⭐0 (+458 today)
  [链接](https://github.com/mvanhorn/last30days-skill)
  一个 AI Agent Skill，能自动研究 Reddit、X、YouTube 等平台上的话题，并生成摘要。它展示了 Agent 如何自主完成复杂的跨平台信息收集与综合任务。

- **gastownhall/gastown** ⭐0 (+291 today)
  [链接](https://github.com/gastownhall/gastown)
  多 Agent 工作区管理器。专注于解决多个 Agent 协同工作时的协调与管理问题，是迈向复杂多 Agent 系统的基础设施尝试。

##### 📦 **AI 应用（具体应用产品、垂直场景解决方案）**

- **Zackriya-Solutions/meetily** ⭐0 (+2494 today)
  [链接](https://github.com/Zackriya-Solutions/meetily)
  今日最受欢迎的 AI 应用。一款隐私优先、完全本地运行的 AI 会议助手，支持 4 倍速实时转录、说话人识别和 Ollama 总结。它验证了用户对“无需云、真离线”AI 助手工具的强烈需求。

- **asgeirtj/system_prompts_leaks** ⭐0 (+1378 today)
  [链接](https://github.com/asgeirtj/system_prompts_leaks)
  一个系统提示词的公开数据库，收集了 Anthropic、OpenAI、Google 等公司的前沿模型 Prompt。它本身不直接运行代码，但作为数据集和研究材料，对 AI 安全、模型对齐以及社区了解大模型行为有很高的价值。

- **karakeep-app/karakeep** ⭐0 (+199 today)
  [链接](https://github.com/karakeep-app/karakeep)
  一个自托管的“收藏一切”应用（链接、笔记和图片），利用 AI 进行自动标签和全文搜索。是 Obsidian、Notion 等知识管理工具的 AI 增强替代品，强调数据自主权。

- **Leonxlnx/taste-skill** ⭐0 (+1458 today)
  [链接](https://github.com/Leonxlnx/taste-skill)
  一个为 AI 模型注入“品味”的 Skill，旨在减少 AI 生成内容的同质化。标志着开发者开始关注 AI 输出的质量和独特性，而非仅仅是准确率。

- **bradautomates/claude-video** ⭐0 (+427 today)
  [链接](https://github.com/bradautomates/claude-video)
  让 Claude 能够“看”视频。项目通过下载、提取帧、转录等步骤，将视频内容转化为 Claude 可以理解的形式，是 AI 多模态应用的一个轻量级实践。

##### 🧠 **大模型/训练（模型权重、训练框架、微调工具）**

- （Trending 榜单未收录相关项目，主题搜索中的项目多为老牌项目，新增热度一般，暂不在此处重复列出）

##### 🔍 **RAG/知识库（向量数据库、检索增强、知识管理）**

- **alibaba/zvec** ⭐13,586 (+382 today)
  [链接](https://github.com/alibaba/zvec) （提及两次）
  作为进程内向量数据库，它是构建轻量级、低延迟 RAG 应用的理想选择。

- **infiniflow/ragflow** ⭐84,448
  [链接](https://github.com/infiniflow/ragflow)
  RAG 领域的头部开源引擎，融合了 RAG 和 Agent 能力，为 LLM 提供强大的上下文层，社区成熟度和认可度极高。

- **Graphify-Labs/graphify** ⭐78,836
  [链接](https://github.com/Graphify-Labs/graphify)
  一个 AI 编程助手 Skill，能将代码、SQL、文档等任何文件夹转化为可查询的知识图谱。这是 RAG 的一个前沿方向——从简单向量检索升级为更复杂的图结构知识管理。

- **mem0ai/mem0** ⭐60,254
  [链接](https://github.com/mem0ai/mem0)
  AI Agent 的通用记忆层。解决了 Agent 在多轮对话或任务间缺乏长期记忆的痛点，是构建拥有“记忆能力”的 Agent 的核心组件。

---

#### **3. 趋势信号分析**

今日的 AI 开源热榜释放出几个强烈的信号：

1.  **“Agent Skills”生态进入爆发期**。以 `agent-skills`、`claude-skills` 和 `taste-skill` 为代表的项目，其核心思路是**将特定领域的知识、工作流和经验抽象为可复用的“技能模块”**，供给 AI 编程 Agent 调用。这标志着 AI 开发从“训练模型”转向“组合技能”，社区正在系统化地构建 Agent 的能力图谱。“工程 skills”（`agent-skills`）和“审美 skills”（`taste-skill`）的并行出现，说明社区正在追求 Agent 不仅“做到”，还要“做好”。

2.  **“本地 AI”的摩尔定律正被社区验证**。`meetily`（AI 会议助手）、`karakeep`（AI 知识管理）和 `zvec`（内存向量库）的发烫热度共同指向一个明确的用户需求：**不牺牲功能，但要牺牲云服务**。这些项目在本地实现了一度被认为必须依靠云端才能完成的实时转录、语义检索等功能，并强调 100% 私有化。这背后是本地模型（如 Ollama）性能的提升和硬件资源的丰富化，使得“离线 AI”成为普惠选项。

3.  **注意力经济转向“AI 透明度”**。`system_prompts_leaks` 的异军突起值得玩味。它本身并非技术工具，而是“信息矿藏”，但高达 1378 的今日新增星标，表明社区对模型背后的引导策略、安全限制和预置行为有极高的探索欲。这反映了在 AI 应用大规模落地后，开发者和研究者对模型“黑盒”内部逻辑的好奇与审视，可能催生下一波关于模型审计和 Prompt 工程安全的研究热潮。

---

#### **4. 社区关注热点**

- **⭐ `agent-skills` 和 `claude-skills` 合集**：如果你正在使用或开发 AI 编码 Agent，这个项目是必看之选。它包含了将 Agent 扩展到特定领域的最佳实践，是当前“Agent 技能”生态的集大成者。
- **⭐ `meetily`**：对于关注隐私和本地部署的团队或个人，这个项目是会议录播和总结工具的优质开源选择。它展示了 Rust + 本地 AI 模型能实现的强大实时能力。
- **⭐ `system_prompts_leaks`**：不是工具，而是知识库。如果你是 Prompt Engineer、AI 安全研究员或者单纯好奇各大模型背后的秘密，这个仓库是极具价值的参考，它能帮你了解竞品模型的策略。
- **⭐ `Graphify-labs/graphify`**：对于希望超越简单 RAG、构建更深层次知识联系的开发者，这个项目代表了下一代知识库的方向——将代码和文档变为可推理的知识图谱，而不仅仅是可搜索的向量。
- **⭐ `alibaba/zvec`**：如果你正在构建高频调用的 AI Agent 或实时 RAG 应用，zvec 提供了一种极致的低延迟向量检索方案。它的“进程内”特性是关键优势，非常值得一试。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*