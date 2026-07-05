# Hugging Face 热门模型日报 2026-07-05

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-05 03:53 UTC

---

好的，这是为您生成的《Hugging Face 热门模型日报（2026-07-05）》。

---

## Hugging Face 热门模型日报（2026-07-05）

### 今日速览

本周 Hugging Face 生态呈现出鲜明的“巨头军备竞赛”与“社区微调狂欢”并存的格局。GLM-5.2、DeepSeek-V4 系列等中国模型家族的多个变体同时上榜，显示了强大的生态影响力。在社区侧，基于 Qwen3.5/3.6 和 Gemma-4 的量化版本（GGUF）和“无罪化”微调模型（Uncensored/Abliterated）霸占了下载和点赞榜的头部位置，本地部署和定向微调依然是社区最活跃的领域。此外，NVIDIA 和百度发布了多项视觉理解与 OCR 专用模型，多模态能力正快速向垂直场景渗透。

### 热门模型

#### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | zai-org | 👍 3,401 | 📥 208,920
    - 本周点赞冠军，智谱推出的新一代 MoE 大语言模型，是当前最受关注的国产开源旗舰模型。
- **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)** | deepseek-ai | 👍 371 | 📥 10,306
    - DeepSeek V4 系列的顶级版本，代表当前开源模型的最顶尖水平之一，伴随学术论文发布。
- **[deepreinforce-ai/Ornith-1.0-397B](https://huggingface.co/deepreinforce-ai/Ornith-1.0-397B)** | deepreinforce-ai | 👍 209 | 📥 33,268
    - 基于 Qwen3.5 MoE 架构的巨型模型（397B 参数），专为复杂推理任务设计，体现了“更大即更强”的路径。
- **[nvidia/Nemotron-Labs-TwoTower-30B-A3B-Base-BF16](https://huggingface.co/nvidia/Nemotron-Labs-TwoTower-30B-A3B-Base-BF16)** | nvidia | 👍 121 | 📥 10,479
    - NVIDIA 推出的“双塔”架构实验模型，兼顾活跃参数效率与性能，代表了一种模块化推理的新思路。
- **[Qwen/Qwen-AgentWorld-35B-A3B](https://huggingface.co/Qwen/Qwen-AgentWorld-35B-A3B)** | Qwen | 👍 534 | 📥 50,188
    - Qwen 官方推出的 Agent 强化版本，通过世界数据增训显著提升智能体任务表现。

#### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** | nvidia | 👍 2,606 | 📥 1,194,542
    - NVIDIA 发布的通用视觉定位模型，支持“指哪打哪”式的开放词汇目标检测，下载量与点赞量双高。
- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M)** | empero-ai | 👍 670 | 📥 135,665
    - 融合了 Qwen3.5 与 Claude 风格的高质量微调模型，6B 量级的多模态对话优选。
- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | baidu | 👍 1,715 | 📥 988,379
    - 百度推出的全能 OCR 模型，支持任意场景下的文字识别，下载量接近百万，商业级应用潜力巨大。
- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** | krea | 👍 497 | 📥 89,384
    - Krea 团队推出的新一代 Turbo 文生图模型，在生成速度与质量上取得平衡。
- **[fal/LTX-2.3-3DREAL-LoRA](https://huggingface.co/fal/LTX-2.3-3DREAL-LoRA)** | fal | 👍 157 | 📥 0
    - 基于 LTX-Video 模型的 LoRA，专为生成真实感 3D 视频优化，探索视频生成的新边界。

#### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** | yuxinlu1 | 👍 2,596 | 📥 641,260
    - 基于 Google Gemma-4 的代码专项微调 + 量化版，社区热度极高，是当前最强开源编码模型之一。
- **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)** | google | 👍 200 | 📥 1,177
    - Google 官方发布的表格数据基础模型，支持分类、回归与零样本能力，有望重塑表格数据处理方式。
- **[BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6](https://huggingface.co/BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6)** | BugTraceAI | 👍 132 | 📥 12,001
    - 专为网络安全与渗透测试设计的模型，代表了 AI 在垂直安全领域应用的落地。
- **[nationaldesignstudio/rampart](https://huggingface.co/nationaldesignstudio/rampart)** | nationaldesignstudio | 👍 123 | 📥 1,881
    - 基于 BERT 的轻量级 PII（个人身份信息）检测模型，已经转换为 ONNX 格式，适用于浏览器端推理。

#### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | HauhauCS | 👍 2,456 | 📥 2,993,053
    - 本周下载量之王！基于 Qwen3.6 的“超狂野”无罪化微调版，备受本地部署用户追捧。
- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | empero-ai | 👍 1,466 | 📥 1,464,047
    - 顶级社区模型的 GGUF 版，适合在 llama.cpp 本地运行，下载量巨大。
- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)** | yuxinlu1 | 👍 1,012 | 📥 342,752
    - 基于 Gemma-4 的通用智能体型微调模型 GGUF 版，适合在本地搭建 Agent 应用。
- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** | deepreinforce-ai | 👍 713 | 📥 359,659
    - Ornith 家族的量化版本，让消费级硬件运行 35B 级别模型成为可能。
- **[huihui-ai/Huihui-GLM-5.2-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-GLM-5.2-abliterated-GGUF)** | huihui-ai | 👍 162 | 📥 4,701
    - 对 GLM-5.2 进行“剔除对齐”并量化的社区版本，为偏好自由对话的用户提供选择。

### 生态信号

1.  **模型家族呈现寡头化**：本周前三热门家族分别为 **Qwen (3.5/3.6)**、**Gemma-4** 和 **GLM-5.2**。所有社区微调与量化活动几乎都围绕这三个基础架构展开，它们的权重管理和 API 生态已成为本地部署的事实标准。
2.  **开源权重模型持续碾压闭源**：榜单上前十名皆是开源权重模型（或基于其的量化版本），未见闭源 API 模型身影。这表明开源社区在生态活力、创新速度和用户口碑上已对闭源构成显著优势。
3.  **量化与“特殊化”微调是主旋律**：“GGUF”几乎成为热门模型的标配，“abliterated”（剔除限制）和“uncensored”（无审查）微调成为社区头部创作者吸引流量的核心玩法。这说明用户对模型的**自由度和控制权**需求极高。

### 值得探索

1.  **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**
    - **理由**：本周下载量断层第一。如果你需要一个几乎没有约束、性能强大的 MoE 模型用于本地实验或特定场景，这是最具代表性的社区作品，也是衡量社区“去对齐”水平的标杆。

2.  **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**
    - **理由**：Google 官方盖章的表格基础模型。对于数据科学和金融、医疗等结构化数据从业者，这可能是今年最重要的模型发布之一。其零样本能力和 PyTorch 实现使其极易集成到现有工作流中。

3.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**
    - **理由**：NVIDIA 的视觉定位模型，以 3B 参数实现了强大的开放词汇目标检测能力。它代表了视觉理解从“分类”到“定位”的范式升级，无论是做自动驾驶、机器人还是自动化应用，都值得深入研究。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*