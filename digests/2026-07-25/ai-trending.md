# AI 开源趋势日报 2026-07-25

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-07-25 15:45 UTC

---

# AI 开源趋势日报（2026-07-25）

## 1. 今日速览

- **AI 代理技能体系爆发**：`mattpocock/skills`（+1743）、`ego-lite`（+986）、`obra/superpowers`（+600）等代理技能和专用基础设施项目今日登榜，显示开发者正从构建单个 agent 转向为 agent 打造可复用的技能库和运行环境。
- **上下文与记忆层持续升温**：`claude-mem`（88k+ stars）、`mem0`（61k+ stars）等持久上下文项目热度不减，跨会话记忆成为 agent 落地的核心基础设施。
- **垂直领域 AI 加速渗透**：金融领域的 `Kronos`（+319）、`Vibe-Trading`（27k+ stars）以及 AI 视频编辑器 `palmier-pro`（+731）表明 AI 正深入专业场景。
- **RAG 效率革命**：`LEANN`（97% 存储节省）、`turbovec`（量化向量索引）等代表 RAG 从“可用”向“高效”演进。
- **阿里开源代码审查工具**：`alibaba/open-code-review`（+439）将 LLM Agent 引入开发流程，企业级 AI 工程化实践受关注。

---

## 2. 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [vllm-project/vllm](https://github.com/vllm-project/vllm) | 87,138 | - | 高吞吐量 LLM 推理引擎，生产部署首选 |
| [ollama/ollama](https://github.com/ollama/ollama) | 176,848 | - | 一键本地运行多种大模型，使用门槛最低 |
| [andrewyng/aisuite](https://github.com/andrewyng/aisuite) | ? | +75 | 统一 API 访问多家 AI 服务，简化集成 |
| [turbovec](https://github.com/RyanCodrai/turbovec) | ? | +89 | 基于量化技术的向量索引，Rust 实现的 Python 绑定 |
| [Firecrawl](https://github.com/firecrawl/firecrawl) | 155,856 | - | 大规模网页搜索/抓取 API，专为 LLM 设计 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | 142,575 | - | 智能体工程标准框架，生态最丰富 |
| [run-llama/llama_index](https://github.com/run-llama/llama_index) | 51,085 | - | 文档代理与 OCR 平台，支持多种数据源 |

---

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | 220,313 | - | “与你共同成长的 agent”，自主进化能力 |
| [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 185,681 | - | 自主 AI 代理先驱，持续迭代中 |
| [browser-use](https://github.com/browser-use/browser-use) | 106,727 | - | 让 AI 代理操作网页，自动化在线任务 |
| [OpenHands](https://github.com/OpenHands/OpenHands) | 82,049 | - | AI 驱动软件开发，自动编码与调试 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 61,665 | - | 通用记忆层，为 AI 代理提供持久上下文 |
| [claude-mem](https://github.com/thedotmack/claude-mem) | 88,537 | - | 跨会话上下文捕获与注入，减少重复输入 |
| [ego-lite](https://github.com/citrolabs/ego-lite) | ? | +986 | **今日爆款** — 专为 AI 代理优化的浏览器，可共享登录状态 |
| [mattpocock/skills](https://github.com/mattpocock/skills) | ? | +1,743 | **今日爆款** — 工程师技能集，从 `.agents` 目录加载，定义 agent 技能新范式 |

---

### 📦 AI 应用（具体应用产品、垂直场景解决方案）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [Chat2DB](https://github.com/OtterMind/Chat2DB) | ? | +364 | AI 驱动的数据库客户端，支持 10+ 种数据库 |
| [palmier-pro](https://github.com/palmier-io/palmier-pro) | ? | +731 | macOS 原生 AI 视频编辑器，融合 AI 能力 |
| [MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 99,246 | - | 关键词生成高清短视频，AI 内容创作利器 |
| [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) | 86,236 | - | 100+ 语言 OCR 工具，桥梁连接图片与 LLM |
| [OpenBB](https://github.com/OpenBB-finance/OpenBB) | 70,998 | - | 开放数据平台，支持 AI 代理进行量化分析 |
| [Kronos](https://github.com/shiyu-coder/Kronos) | ? | +319 | 金融市场的基座模型，专注于金融语言理解 |
| [Vibe-Trading](https://github.com/HKUDS/Vibe-Trading) | 27,481 | - | 个人交易代理，基于 AI 的市场预测与执行 |

---

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [minimind](https://github.com/jingyaogong/minimind) | 53,838 | - | 2 小时从零训练 64M 参数 LLM，降低入门门槛 |
| [tiny-llm](https://github.com/skyzh/tiny-llm) | 4,407 | - | 系统工程师视角的 LLM 推理服务教程，构建 tiny vLLM |
| [opencompass](https://github.com/open-compass/opencompass) | 7,235 | - | LLM 评估平台，支持 100+ 数据集与主流模型 |
| [picollm](https://github.com/Picovoice/picollm) | 315 | - | 设备端 LLM 推理，X-Bit 量化，适合边缘部署 |

---

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [dify](https://github.com/langgenius/dify) | 150,213 | - | 构建代理工作流和 RAG 管道的协作平台 |
| [open-webui](https://github.com/open-webui/open-webui) | 146,694 | - | 用户友好 AI 界面，支持 Ollama 和多种模型 |
| [RAGflow](https://github.com/infiniflow/ragflow) | 85,975 | - | 领先开源 RAG 引擎，融合 Agent 能力 |
| [Graphify](https://github.com/Graphify-Labs/graphify) | 95,648 | - | 代码库转可查询知识图谱，支持多种 AI CLI |
| [LightRAG](https://github.com/HKUDS/LightRAG) | 38,116 | - | EMNLP 2025 论文实现，简单快速的 RAG |
| [anything-llm](https://github.com/Mintplex-Labs/anything-llm) | 63,829 | - | 本地优先的 agent 体验，私有化部署 |
| [LEANN](https://github.com/StarTrail-org/LEANN) | 12,728 | - | 97% 存储节省的 RAG 方案，MLSys 2026 论文 |

---

## 3. 趋势信号分析

**今日社区爆发性关注集中于三个方向：**

1️⃣ **AI 代理技能标准化与专用基础设施**  
`mattpocock/skills`（+1743）、`obra/superpowers`（+600）和 `ego-lite`（+986）三项目同时冲榜，标志着社区从“构建 agent”正式转向“为 agent 提供可复用的技能库和运行环境”。`skills` 定义了一套自 `.agents` 目录加载的技能协议，`ego-lite` 则解决 agent 登录态共享这一长期痛点。这预示着一个以“技能市场”和“agent 浏览器”为核心的新生态正在形成。

2️⃣ **RAG 效率革命**  
传统 RAG 面临存储和速度瓶颈，今日 `turbovec`（量化技术）和 `LEANN`（97% 存储节省）的登榜，表明开发者开始追求极致的资源利用。结合 `LightRAG` 获 EMNLP 2025 收录，RAG 正从“能跑”进入“高效跑”阶段，边缘设备和移动端场景尤其受益。

3️⃣ **金融与创意工具的 AI 深潜**  
`Kronos`（金融基座模型）、`Vibe-Trading`（交易代理）以及 `palmier-pro`（AI 视频编辑器）的活跃，显示 AI 在专业垂直领域的渗透加速。这与近期大模型在量化回测、视频生成领域的进展（如 Sora 引发的多模态热潮）紧密关联，开发者正积极将 LLM 能力封装为垂直产品。

---

## 4. 社区关注热点

- 🔥 **Agent 技能协议与运行时**：关注 `mattpocock/skills` 和 `obra/superpowers` 的设计模式，它们可能成为未来 agent 技能生态的标准基础。
- 🔥 **跨会话记忆管理**：`claude-mem`（88k+）和 `mem0`（61k+）说明持久上下文是 agent 可靠性的关键，值得深入研究内存压缩和检索机制。
- 🔥 **专属 AI 浏览器**：`ego-lite` 解决了 agent 登录认证和状态共享难题，类似基础设施有望催生新一代 agent 自动化工具。
- 🔥 **超高效 RAG**：`LEANN` 和 `turbovec` 展示了在资源受限环境下的 RAG 可能性，对移动端、IoT 场景有重要参考价值。
- 🔥 **企业级 AI 工程化**：`alibaba/open-code-review` 将 LLM Agent 整合到代码审查流水线，体现了大型企业在 AI 辅助开发上的务实落地路径，值得组织内部借鉴。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*