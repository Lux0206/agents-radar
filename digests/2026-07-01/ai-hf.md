# Hugging Face 热门模型日报 2026-07-01

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-01 11:42 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的数据生成的《Hugging Face 热门模型日报（2026-07-01）》。

---

### Hugging Face 热门模型日报 | 2026-07-01

#### 今日速览

本周 Hugging Face 生态呈现显著的分层化趋势。**GLM-5.2 系列**凭借其 MoE 架构和出色的对话能力，以绝对优势登顶社区热榜第一，成为社区焦点。与此同时，**Qwen 3.5/3.6 系列**的涌现势头强劲，催生了大量社区微调版本和量化模型，占据了榜单的“半壁江山”。值得关注的是，**DeepSeek-V4 系列**开始释放 Pro 和 Flash 版本，预示着新一轮超大规模模型竞赛的开启。此外，百度的 **Unlimited-OCR** 表现出强大的下载量，显示了垂直领域任务（OCR）的巨大刚需。

---

#### 热门模型

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**  
  **作者**: zai-org | **点赞**: 3,108 | **下载**: 159,967  
  **说明**: 本周最大热门。基于 MoE 架构的最新通用大模型，以其强大的对话和文本生成能力迅速获得了社区最高点赞，代表了国产开源模型的最新进展。

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M)**  
  **作者**: empero-ai | **点赞**: 603 | **下载**: 114,499  
  **说明**: 基于 Qwen 3.5 架构的指令微调模型，旨在复现神秘神话风格的对话体验，代表了社区对高质量、风格化对话模型的持续追求。

- **[deepreinforce-ai/Ornith-1.0-35B](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B)**  
  **作者**: deepreinforce-ai | **点赞**: 274 | **下载**: 135,452  
  **说明**: 35B 参数级别的 MoE 模型，隶属于 Ornith 系列。该系列同时提供了 **9B**、**35B** 和 **397B** 三个版本，覆盖了从消费级到企业级的部署需求。

- **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)**  
  **作者**: deepseek-ai | **点赞**: 264 | **下载**: 7,629  
  **说明**: DeepSeek-V4 系列的 Pro 版本，附带论文 `arxiv:2606.19348`。作为业界瞩目的超大模型，其发布标志着 DeepSeek 在第四代模型上的技术布局。

- **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LFM2.5-230M)**  
  **作者**: LiquidAI | **点赞**: 174 | **下载**: 21,935  
  **说明**: 小众但亮眼的小参数模型（230M），延续了 Liquid 在高效小模型上的探索，适合边缘计算场景。

- **[Chunjiang-Intelligence/DeepSeek-v4-Fable](https://huggingface.co/Chunjiang-Intelligence/DeepSeek-v4-Fable)**  
  **作者**: Chunjiang-Intelligence | **点赞**: 136 | **下载**: 1,766  
  **说明**: 基于 DeepSeek-v4 的社区微调版本，名称“Fable”暗示其专注于文学性或特定风格内容生成。

- **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)**  
  **作者**: InternScience | **点赞**: 111 | **下载**: 511  
  **说明**: 基于 Qwen 3.5 MoE 架构的 Agent 模型，专门为工具调用和自主任务执行而设计，反映了 Agent 模型持续成为研究热点。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**  
  **作者**: baidu | **点赞**: 1,534 | **下载**: 630,246  
  **说明**: 百度的通用 OCR 模型，将图像中的文字提取为文本。其极高的下载量（63万+）表明其在真实业务场景中具有极高的实用价值。

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**  
  **作者**: nvidia | **点赞**: 2,533 | **下载**: 896,058  
  **说明**: NVIDIA 推出的通用目标定位模型，可以仅通过自然语言指令在图像中定位任何物体。点赞数极高，且下载量接近90万，是本周最成功的多模态模型之一。

- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)**
  **作者**: krea | **点赞**: 431 | **下载**: 56,953  
  **说明**: 基于 Krea-2-Raw 模型的加速版本，专注于高效文生图。生图类模型进入榜单，表明图像生成的需求依然旺盛。

- **[fal/LTX-2.3-3DREAL-LoRA](https://huggingface.co/fal/LTX-2.3-3DREAL-LoRA)**  
  **作者**: fal | **点赞**: 132 | **下载**: 0  
  **说明**: 用于 LTX-2.3 视频生成模型的 LoRA 模块，专注于生成逼真的3D风格视频。作为 LoRA 模型出现在榜单，展示了社区对视频生成模型的定制化需求。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)**  
  **作者**: yuxinlu1 | **点赞**: 2,542 | **下载**: 597,090  
  **说明**: 基于 Google Gemma 4 的代码专用模型，结合了 Fable 和 Composer 技术。是本周最受关注的代码模型，下载量接近60万，证明了代码模型的巨大市场。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**  
  **作者**: empero-ai | **点赞**: 1,103 | **下载**: 1,113,871  
  **说明**: Qwythos-9B 的 GGUF 量化版。下载量突破百万，是本周下载量最高的模型之一，生动展现了用户对本地运行对话模型的热情。

- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**  
  **作者**: yuxinlu1 | **点赞**: 902 | **下载**: 288,741  
  **说明**: 基于 Gemma 4 的 Agent 模型 GGUF 版本，结合了 Fable 和 Composer 技术。说明 Agent 模型量化版同样广受欢迎。

- **[unsloth/GLM-5.2-GGUF](https://huggingface.co/unsloth/GLM-5.2-GGUF)**  
  **作者**: unsloth | **点赞**: 487 | **下载**: 212,201  
  **说明**: 热门模型 GLM-5.2 的 GGUF 量化版，由知名量化团队 unsloth 提供。GLM-5.2 的流行直接带动了其量化版本的下载量。

- **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)**  
  **作者**: nvidia | **点赞**: 191 | **下载**: 136,933  
  **说明**: NVIDIA 使用其私有格式 NVFP4 对 GLM-5.2 进行量化的版本，展示了大型企业与社区在量化适配上的合作。

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**  
  **作者**: HauhauCS | **点赞**: 2,367 | **下载**: 3,055,962  
  **说明**: 基于 Qwen 3.6 架构的“去审查”版本，下载量突破300万。该模型的出现，体现了社区对模型内容控制与价值观对齐的持续博弈。

---

#### 生态信号

1.  **MoE 与套壳模型当道**：榜单中大量模型（GLM-5.2、Ornith、Qwen AgentWorld）采用 **MoE（混合专家）** 架构，这表明行业共识已转向更高效的稀疏激活模型。同时，**Qwen 和 DeepSeek** 成为了社区最受欢迎的“基座”模型，大量微调版本（如 Ornith、Qwythos）涌现，形成了繁荣的模型“套壳”生态。

2.  **量化需求持续爆发**：GGUF 格式的量化模型在下载量上表现惊人，远超原版模型（如 Qwythos-9B GGUF 版本和 Gemma-4-coder GGUF 版本）。这表明 **本地化、高效部署** 是当前最核心的用户需求，HuggingFace 已从“模型仓库”演变为“模型应用平台”。

3.  **合规与安全的博弈**：“Uncensored”（去审查）模型（如 `HauhauCS/Qwen3.6-35B-A3B-Uncensored...`）下载量极高，说明开源领域存在对“无约束”模型的不变需求。这警示整个生态需要在创新与安全责任之间找到更好的平衡点。

---

#### 值得探索

1.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**  
    **推荐理由**：点赞和下载量双双登顶，是NVIDIA在通用视觉理解领域的标杆之作。它打破了传统目标检测的类别限制，通过自然语言即可实现任意物体定位，对于机器人、自动化和图像理解研究极具价值。

2.  **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**  
    **推荐理由**：本周社区热度冠军。它背后是智谱AI对 MoE 架构的深度探索，其对话能力和通用表现值得深入研究。同时，关注其与 NVIDIA 等厂商的量化合作，这代表了未来大模型基础平台化的发展方向。

3.  **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**  
    **推荐理由**：下载量超过300万，虽然围绕其“Uncensored”特性争议巨大，但它深刻反映了当前模型对齐价值观的生成与用户真实需求的矛盾。研究这类模型有助于理解模型行为的边界，并对AI安全对齐政策产生重要影响。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*