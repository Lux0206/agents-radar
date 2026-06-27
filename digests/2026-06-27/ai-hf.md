# Hugging Face 热门模型日报 2026-06-27

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-06-27 08:27 UTC

---

好的，作为AI模型生态分析师，我为您呈现2026年6月27日的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-06-27**

#### **今日速览**

本周，Hugging Face 生态呈现出两大清晰趋势：**MoE（混合专家）架构的全面爆发**与 **GGUF 量化生态的持续繁荣**。智谱AI的 **GLM-5.2** 和 通义千问的 **Qwen3.6** 系列成为关注焦点，它们不仅原生权重受到热捧，围绕其开发的量化版、微调版和“无审查”版模型也大量涌现，形成了丰富的开发者生态。同时，**Gemma 4** 系列在代码和智能体任务上表现出色，其量化版和“去强化”版模型下载量巨大，显示出社区对实用性和可控性的强烈需求。NVIDIA 在语音识别和大模型推理优化（NVFP4）方面的贡献也值得关注。

#### **热门模型**

##### 🧠 **语言模型（LLM、对话模型、指令微调）**

*   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** - **zai-org** | 👍 2,624 | ⬇️ 83,589
    *   **一句话说明**：智谱AI推出的新一代MoE大模型，凭借优秀的对话能力在本周获得了社区最高关注。
*   **[WeiboAI/VibeThinker-3B](https://huggingface.co/WeiboAI/VibeThinker-3B)** - **WeiboAI** | 👍 735 | ⬇️ 54,638
    *   **一句话说明**：一款基于Qwen2的3B参数数学推理模型，因其在数学任务上的出色表现而成为小体量模型中的黑马。
*   **[nvidia/nemotron-3.5-asr-streaming-0.6b](https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b)** - **nvidia** | 👍 712 | ⬇️ 56,434
    *   **一句话说明**：NVIDIA发布的高效流式语音识别模型，为端侧和低延迟场景提供了高质量选择。
*   **[microsoft/FastContext-1.0-4B-SFT](https://huggingface.co/microsoft/FastContext-1.0-4B-SFT)** - **microsoft** | 👍 359 | ⬇️ 5,735
    *   **一句话说明**：微软推出的长上下文优化模型（基于Qwen3），旨在提升智能体在处理长文档时的高效检索能力。
*   **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LFM2.5-230M)** - **LiquidAI** | 👍 120 | ⬇️ 8,286
    *   **一句话说明**：Liquid AI发布的首批2.5代模型中的最小版本，是当前极小参数级别语言模型的性能标杆之一。

##### 🎨 **多模态与生成（图像、视频、音频、文本到X）**

*   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** - **baidu** | 👍 1,075 | ⬇️ 134,146
    *   **一句话说明**：百度的通用OCR模型，凭借强大的图文识别能力，成为本周下载量最高的模型之一，实用性极强。
*   **[MiniMaxAI/MiniMax-M3](https://huggingface.co/MiniMaxAI/MiniMax-M3)** - **MiniMaxAI** | 👍 1,248 | ⬇️ 169,951
    *   **一句话说明**：MiniMax的第三代多模态大模型，在图文理解与生成任务上展现强劲实力，备受社区期待。
*   **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** - **krea** | 👍 294 | ⬇️ 8,721
    *   **一句话说明**：Krea推出的第二代文生图模型的高速版本，继承了其“Raw”模型的特性，主打快速生成高质量图像。
*   **[datalab-to/lift](https://huggingface.co/datalab-to/lift)** - **datalab-to** | 👍 159 | ⬇️ 6,054
    *   **一句话说明**：基于Qwen3.5的多模态模型，专注于PDF文档与图表的深度理解与信息提取。

##### 🔧 **专用模型（代码、数学、医疗、嵌入）**

*   **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** - **nvidia** | 👍 2,391 | ⬇️ 494,756
    *   **一句话说明**：NVIDIA推出的3B参数视觉定位模型，能根据文本描述在图像中精确定位目标，在趋势榜上人气极高。
*   **[Chunjiang-Intelligence/DeepSeek-v4-Fable](https://huggingface.co/Chunjiang-Intelligence/DeepSeek-v4-Fable)** - **Chunjiang-Intelligence** | 👍 108 | ⬇️ 1,103
    *   **一句话说明**：DeepSeek v4的社区微调版本，专注于网络安全领域的应用，是专用垂直模型的代表。

##### 📦 **微调与量化（社区微调、GGUF、AWQ）**

*   **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** - **yuxinlu1** | 👍 2,410 | ⬇️ 516,333
    *   **一句话说明**：Gemma 4的社区微调代码版GGUF量化模型，下载量惊人，表明开发者对高质量、可本地运行的代码模型有巨大需求。
*   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** - **HauhauCS** | 👍 2,268 | ⬇️ **3,453,492**
    *   **一句话说明**：Qwen3.6 35B MoE模型的“无审查”版GGUF，本周下载量登顶，反映了社区对内容限制较少的模型的强烈偏好。
*   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** - **empero-ai** | 👍 620 | ⬇️ 486,810
    *   **一句话说明**：基于Qwen3.5的社区微调推理模型GGUF版，下载量巨大，与原始版（👍 458, ⬇️ 20k）对比可见量化模型的普及度。
*   **[unsloth/GLM-5.2-GGUF](https://huggingface.co/unsloth/GLM-5.2-GGUF)** - **unsloth** | 👍 419 | ⬇️ 107,553
    *   **一句话说明**：知名量化工具团队Unsloth为GLM-5.2提供的GGUF版本，方便了社区在本地部署该模型。

---

#### **生态信号**

*   **MoE 架构成为主流**：无论是智谱的 **GLM-5.2**、阿里的 **Qwen 3.x 系列**，还是其他模型，混合专家（MoE）架构已全面占据榜单核心位置。其“激活部分参数”的特性，在保持高性能的同时降低了推理成本，是社区追捧的关键。
*   **开源模型“一鱼多吃”生态成熟**：以 **Qwen3.6-35B-A3B** 为例，其原生模型、NVIDIA的FP4量化版、社区的无审查版、GGUF量化版、27B的变体等均在热榜。这显示围绕单一优秀基座模型的**微调、量化和适配生态**已经非常成熟，各玩家分工明确。
*   **超级量化时代来临**：GGUF模型在榜单中占据半壁江山，其下载量远超对应原生模型（如Qwythos-9B），说明**“下载即运行”**的一体化包是开发者进行本地部署和实验的首选。NVIDIA提出的 **NVFP4** 量化格式，也预示着超低精度量化正在从实验走向应用。
*   **“无审查”与“去强化”成社区热点**：来自`HauhauCS`和`huihui-ai`等作者的“Uncensored”和“Abliterated”模型热度极高，表明部分社区用户对主流模型的对齐（RLHF）策略并不满足，希望通过微调获得更“自由”的模型行为。

---

#### **值得探索**

1.  **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** - **最热门的社区实验品**。这个模型获得了本周最高的下载量，其对基座模型行为的大幅修改，成为了解当前社区对模型“自由度”诉求的最佳窗口。**（注意：使用此类模型需注意伦理与安全风险）**
2.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** - **视觉AI的下一个爆点**。3B参数的小模型就能实现精准的图像定位，这在机器人、自动驾驶、和图像编辑领域有巨大的应用潜力。它的高点赞数表明其能力获得了社区的广泛认可。
3.  **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** - **高效代码助手的最佳实践**。它证明了社区微调 + 量化可以产生极具竞争力的代码模型。对于希望在不依赖云服务的情况下拥有强大本地编程助手的开发者来说，这是最优选择。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*