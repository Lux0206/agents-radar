# Hugging Face 热门模型日报 2026-07-06

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-06 04:00 UTC

---

好的，这是为您准备的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-06**

#### **今日速览**

本周 Hugging Face 生态呈现三大特征：第一，**MoE（混合专家）架构**成为绝对的焦点，从 GLM-5.2 到 Qwen3.6 系列，几乎所有头部模型都采用了 MoE 结构，追求更高的参数效率。第二，**模型微调与量化活动极其活跃**，基于 Qwen3.5/3.6 和 Gemma-4 的社区版本（尤其是 GGUF 格式）占据了榜单半壁江山，显示出社区对“本地可运行的高性能模型”的强烈需求。第三，NVIDIA 和 DeepSeek 等巨头持续输出，前者以优化工具（NVFP4）和多模态定位模型抢占生态位，后者则推出了全新的 V4 架构，标志着推理模型的又一次迭代。

#### **热门模型**

**🧠 语言模型（LLM、对话模型、指令微调）**

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | 作者: zai-org | 👍 3,472 | ⬇️ 220,379
  - **说明**: 智谱最新一代 MoE 对话模型，以高点赞数和强大的对话能力成为本周榜单人气之王。

- **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)** | 作者: deepseek-ai | 👍 393 | ⬇️ 12,580
  - **说明**: DeepSeek V4 系列的专业版（Pro），主打高级推理与长上下文能力，代表新一代开源推理模型的最高水平之一。

- **[deepseek-ai/DeepSeek-V4-Flash-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-DSpark)** | 作者: deepseek-ai | 👍 163 | ⬇️ 48,696
  - **说明**: DeepSeek V4 的快速版（Flash），在保持强推理能力的同时优化了推理速度和成本。

- **[nvidia/Qwen3.6-27B-NVFP4](https://huggingface.co/nvidia/Qwen3.6-27B-NVFP4)** | 作者: nvidia | 👍 275 | ⬇️ 297,130
  - **说明**: NVIDIA 采用 Model Optimizer 量化工具优化后的 Qwen3.6 模型，使用 4 位浮点（NVFP4）格式，在性能和精度间取得平衡。

- **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)** | 作者: nvidia | 👍 240 | ⬇️ 280,087
  - **说明**: NVIDIA 对 GLM-5.2 的优化版本，同样是 NVFP4 量化，展示了 NVIDIA 在全栈优化上的布局。

- **[nvidia/Nemotron-Labs-TwoTower-30B-A3B-Base-BF16](https://huggingface.co/nvidia/Nemotron-Labs-TwoTower-30B-A3B-Base-BF16)** | 作者: nvidia | 👍 123 | ⬇️ 10,696
  - **说明**: NVIDIA 的“双塔”架构实验模型，总参数量 30B，活跃参数仅 3B，是极极致 MoE 的探索。

- **[mistralai/Leanstral-1.5-119B-A6B](https://huggingface.co/mistralai/Leanstral-1.5-119B-A6B)** | 作者: mistralai | 👍 117 | ⬇️ 26
  - **说明**: Mistral 的超大规模 MoE 模型（119B 总参，6B 活跃），是 Leanstral 系列的最新迭代，虽刚发布下载量不高，但潜力巨大。

- **[BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6](https://huggingface.co/BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6)** | 作者: BugTraceAI | 👍 135 | ⬇️ 12,196
  - **说明**: 专为网络安全攻防场景设计的量化模型，体现了 LLM 在垂直安全领域的深入应用。

**🎨 多模态与生成（图像、视频、音频、文本到X）**

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** | 作者: nvidia | 👍 2,618 | ⬇️ 1,247,265
  - **说明**: NVIDIA 推出的 3B 参数视觉定位模型，能根据文本指令在图像中精确框选目标，兼具高下载与高点赞。

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | 作者: baidu | 👍 1,753 | ⬇️ 1,044,217
  - **说明**: 百度的通用 OCR 模型，支持不限场景的文字识别，实用性强，下载量破百万。

- **[internScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)** | 作者: InternScience | 👍 295 | ⬇️ 7,010
  - **说明**: 基于 Qwen3.5 MoE 的 Agent 模型，专注智能体任务规划与工具调用。

- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** | 作者: krea | 👍 515 | ⬇️ 99,049
  - **说明**: Krea 二代图像生成模型的加速版，在快速生成与画质之间取得良好平衡。

**🔧 专用模型（代码、数学、医疗、嵌入）**

- **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)** | 作者: google | 👍 227 | ⬇️ 2,670
  - **说明**: Google 发布的基础表格模型（TabFM），支持零样本分类与回归，是表格数据领域的重大进展。

- **[nationaldesignstudio/rampart](https://huggingface.co/nationaldesignstudio/rampart)** | 作者: nationaldesignstudio | 👍 129 | ⬇️ 2,783
  - **说明**: 基于 ONNX/BERT 的 PII（个人身份信息）检测模型，可部署在浏览器端，专注数据隐私保护。

**📦 微调与量化（社区微调、GGUF、AWQ）**

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | 作者: HauhauCS | 👍 2,493 | ⬇️ 3,018,257
  - **说明**: 社区对 Qwen3.6 的“去审查”激进微调版，GGUF 格式，以超高下载量成为本周社区量化之王。

- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** | 作者: yuxinlu1 | 👍 2,612 | ⬇️ 651,758
  - **说明**: 基于 Gemma-4-12B 的代码微调版，结合“fable”等技巧增强编程能力，GGUF 格式方便本地使用。

- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)** | 作者: yuxinlu1 | 👍 1,031 | ⬇️ 355,871
  - **说明**: 同一作者对 Gemma 模型的 Agent 能力增强版，进一步扩展了模型的自动化执行边界。

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | 作者: empero-ai | 👍 1,564 | ⬇️ 1,533,844
  - **说明**: 混合 Claude 风格的“神话”微调模型，GGUF 格式，兼具创意与推理，下载量极高。

- **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)** | 作者: unsloth | 👍 964 | ⬇️ 2,776,389
  - **说明**: Unsloth 团队对 Qwen3.6 的 GGUF 量化版，MTP 后缀代表支持多头注意力预测，是本地部署的绝佳选择。

- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** | 作者: deepreinforce-ai | 👍 734 | ⬇️ 394,164
  - **说明**: Ornith 1.0 系列的最大模型量化版，提供商用友好的 MIT 许可，适合企业环境。

- **[huihui-ai/Huihui-GLM-5.2-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-GLM-5.2-abliterated-GGUF)** | 作者: huihui-ai | 👍 169 | ⬇️ 5,609
  - **说明**: 对 GLM-5.2 进行“消融”（abliterated）去限制的社区微调版，GGUF 格式。

- **[Jackrong/Qwopus3.6-35B-A3B-Coder-MTP-GGUF](https://huggingface.co/Jackrong/Qwopus3.6-35B-A3B-Coder-MTP-GGUF)** | 作者: Jackrong | 👍 140 | ⬇️ 84,951
  - **说明**: 针对编程场景优化的 Qwen3.6 MoE 模型量化版，支持多模态输入。

#### **生态信号**

1.  **MoE 架构全面开花**：从 GLM、Qwen 到 DeepSeek、Mistral，几乎所有主流模型家族都在拥抱 MoE。这表明行业已共识：在有限算力下，通过稀疏激活（如总参 100B+，激活 10B）是提升性能的最优解。
2.  **社区驱动的“去审查”与“个性化”浪潮**：榜单上大量以“Uncensored”、“Abliterated”、“Aggressive”命名的模型表明，社区对模型安全边界的探索热情极高，这既是创新活力，也带来了新的安全治理挑战。
3.  **量化与部署是硬道理**：GGUF 模型下载量动辄数十万甚至百万，显示出开源模型的用户群体高度务实。用户不再仅仅关注模型分数，更关心“我的本地硬件能否跑起来”。NVIDIA 的 NVFP4 等工业级量化方案也在加入战局，推动量化从“社区手工”走向“厂商优化”。

#### **值得探索**

1.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**：强烈推荐。它代表了“VLM（视觉语言模型）+ 精细定位”的实用方向，3B 的轻量级设计使其易于集成到各类视觉应用中，下载量已说明其受欢迎程度。
2.  **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**：推荐数据科学家关注。Google 出品的表格基础模型，有望像 LLM 改造 NLP 一样改造传统的表格数据分析和机器学习，潜力巨大。
3.  **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)**：推荐本地玩家。Unsloth 的量化以不牺牲太多性能著称，结合 Qwen3.6 强大的基础能力，这是目前最值得在单卡上运行的通用大模型之一。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*