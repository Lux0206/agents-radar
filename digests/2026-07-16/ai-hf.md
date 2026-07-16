# Hugging Face 热门模型日报 2026-07-16

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-16 02:55 UTC

---

好的，作为AI模型生态分析师，以下是根据您提供的2026-07-16数据生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-16**

#### **今日速览**

本周HuggingFace生态呈现三个显著特征：**MoE架构**模型持续霸榜，**Qwen 3.5/3.6**衍生模型生态空前繁荣，成为社区微调与量化的首选基座；**视觉与OCR**方向出现数款高下载量模型，表明多模态应用需求旺盛；同时，**极端量化（1-2bit）** 和**特定任务微调（如Agent、身份保持）** 成为社区活跃的创新方向，推动模型部署与个性化应用。

---

#### **热门模型**

##### 🧠 **语言模型（LLM、对话模型、指令微调）**

*   **zai-org/GLM-5.2** (🔥 本周点赞冠军)
    *   作者: zai-org | 点赞: 4,002 | 下载: 489,611
    *   说明: 智谱AI最新发布的MoE大模型，以强劲的性能和MoE架构的高效性受到广泛关注，是本周最具话题性的原生模型。
    *   链接: https://huggingface.co/zai-org/GLM-5.2

*   **HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive**
    *   作者: HauhauCS | 点赞: 2,761 | 下载: 2,443,871
    *   说明: 基于Qwen3.6的MoE模型的社区“无审查”版本，并辅以激进风格微调，体现了社区对个性化、可定制化模型的强烈需求，下载量极高。
    *   链接: https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive

*   **deepreinforce-ai/Ornith-1.0-35B-GGUF**
    *   作者: deepreinforce-ai | 点赞: 895 | 下载: 1,533,354
    *   说明: 一款35B参数级别的通用LLM的GGUF量化版本，凭借良好的性能与便捷的部署方式，在开源社区中迅速积累人气。
    *   链接: https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF

*   **tencent/Hy3**
    *   作者: tencent | 点赞: 801 | 下载: 10,406
    *   说明: 腾讯发布的新一代Hunyuan系列模型，作为官方原版权重，代表着大厂在开源领域的最新布局。
    *   链接: https://huggingface.co/tencent/Hy3

*   **InternScience/Agents-A1**
    *   作者: InternScience | 点赞: 556 | 下载: 30,539
    *   说明: 基于Qwen3.5 MoE架构的Agent专用模型，强调在工具调用和自主规划等Agent任务上的优化，代表了LLM向“行动力”发展的趋势。
    *   链接: https://huggingface.co/InternScience/Agents-A1

*   **nvidia/Nemotron-Labs-Audex-30B-A3B**
    *   作者: nvidia | 点赞: 156 | 下载: 1,332
    *   说明: 英伟达推出的30B-A3B MoE模型，专注于音频理解与处理任务，展示了巨头在特定模态与高效架构结合上的探索。
    *   链接: https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B

##### 🎨 **多模态与生成（图像、视频、音频、文本到X）**

*   **empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF**
    *   作者: empero-ai | 点赞: 2,218 | 下载: 2,006,265
    *   说明: 一款融合了多种数据集（包括Mythos）的视觉语言模型的GGUF量化版，下载量突破200万，是社区最热门的可部署多模态模型之一。
    *   链接: https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF

*   **baidu/Unlimited-OCR**
    *   作者: baidu | 点赞: 2,002 | 下载: 1,715,301
    *   说明: 百度发布的通用OCR模型，支持海量场景下的文字识别，下载量极高，反映出文档数字化和自动化处理领域的巨大需求。
    *   链接: https://huggingface.co/baidu/Unlimited-OCR

*   **unsloth/Qwen3.6-27B-NVFP4**
    *   作者: unsloth | 点赞: 208 | 下载: 1,599,150
    *   说明: 由知名微调工具Unsloth提供的Qwen3.6-27B的NVFP4量化版本，实现了性能与显存占用的最佳平衡，是视觉模型高效部署的典范。
    *   链接: https://huggingface.co/unsloth/Qwen3.6-27B-NVFP4

*   **OpenMOSS-Team/MOSS-Transcribe-Diarize**
    *   作者: OpenMOSS-Team | 点赞: 215 | 下载: 65,109
    *   说明: 专注于语音转写和说话人分离的音频模型，在会议记录、访谈分析等场景有广泛应用前景。
    *   链接: https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize

*   **robbyant/lingbot-world-v2-14b-causal-fast**
    *   作者: robbyant | 点赞: 100 | 下载: 0
    *   说明: 一个图像到视频的“世界模型”，旨在理解图像并生成符合物理规律的后续视频帧，代表了生成式AI向“世界模拟器”演进的方向。
    *   链接: https://huggingface.co/robbyant/lingbot-world-v2-14b-causal-fast

*   **Alissonerdx/LTX-Best-Face-ID**
    *   作者: Alissonerdx | 点赞: 154 | 下载: 0
    *   说明: 一个用于LTX视频模型的LoRA模块，专注于在视频生成中保持特定人脸的身份特征，是视频编辑和个性化内容生成的小而美工具。
    *   链接: https://huggingface.co/Alissonerdx/LTX-Best-Face-ID

*   **mgwr/M87**
    *   作者: mgwr | 点赞: 127 | 下载: 2,408
    *   说明: 基于Krea-2 Turbo基座的LoRA模型，用于特定风格的文本到图像生成，反映了社区对生成图像艺术风格与概念的持续探索。
    *   链接: https://huggingface.co/mgwr/M87

##### 🔧 **专用模型（代码、数学、医疗、嵌入、Agent）**

*   **yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF**
    *   作者: yuxinlu1 | 点赞: 1,198 | 下载: 468,629
    *   说明: 基于Gemma-4的Agent和代码专用模型GGUF版，结合了多个先进微调配方，是命令行和编程场景下的强力助手。
    *   链接: https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF

*   **Cactus-Compute/needle**
    *   作者: Cactus-Compute | 点赞: 236 | 下载: 571
    *   说明: 一个基于JAX的函数调用（Function-Calling）和工具使用（Tool-Use）模型，专注于提升LLM的“动手能力”，代表着AI Agent基础设施的进步。
    *   链接: https://huggingface.co/Cactus-Compute/needle

##### 📦 **微调与量化（社区微调、GGUF、AWQ）**

*   **GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF**
    *   作者: GnLOLot | 点赞: 250 | 下载: 89,892
    *   说明: 对小尺寸模型（1B）进行GGUF量化并融合了“思维链”微调（Thinking）的典型代表，展示了在资源受限设备上运行推理模型的可能性。
    *   链接: https://huggingface.co/GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF

*   **prism-ml/Ternary-Bonsai-27B-gguf**
    *   作者: prism-ml | 点赞: 477 | 下载: 23
    *   说明: 采用“三元量化”（Ternary，2-bit）技术的27B模型，代表了在模型极低比特量化这一前沿领域的社区探索，以极致的模型压缩为目标。
    *   链接: https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf

*   **prism-ml/Bonsai-27B-gguf**
    *   作者: prism-ml | 点赞: 271 | 下载: 513
    *   说明: 1-bit量化的27B模型，相比2-bit更进一步，挑战模型量化的极限，代表了社区对极致部署效率的不懈追求。
    *   链接: https://huggingface.co/prism-ml/Bonsai-27B-gguf

*   **jlnsrk/GLM-5.2-colibri-int4**
    *   作者: jlnsrk | 点赞: 112 | 下载: 2,188
    *   说明: 为GLM-5.2模型提供的int4 CPU量化版本，使得在无GPU环境下运行顶级MoE模型成为可能，扩大了模型的应用范围。
    *   链接: https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4

*   **froggeric/Qwen-Fixed-Chat-Templates**
    *   作者: froggeric | 点赞: 918 | 下载: 0
    *   说明: 一个专门修正Qwen系列模型对话模板的工具/模型，解决了用户在实际部署中遇到的模板兼容性问题，虽非模型本身，但反映了社区对标准化和易用性的重视。
    *   链接: https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates

---

#### **生态信号**

*   **Qwen生态系与MoE浪潮**：本周最明显的趋势是围绕**Qwen 3.5/3.6**和**MoE（混合专家）** 架构的火爆。大量高下载量模型（如Qwen3.6-35B-A3B、Agents-A1）均基于此。可以认为 **Qwen 已经成为社区最活跃的“模型建材”**，其MoE变体因其高效性（以小参数量激活达到大模型性能）备受青睐。
*   **从“能用”到“好用”的量化竞赛**：量化不再是简单的减少位数。从极端的 **1-bit、2-bit（三元量化）** 到针对特定硬件的**NVFP4、int4**，再到配合**专家流式（expert-streaming）** 的量化方案，社区正在为AI在边缘设备、CPU上的最终落地进行着激烈的技术探索。
*   **视觉与Agent的未来**：**OCR（Unlimited-OCR）** 和 **视频生成（lingbot-world）** 的流行标志着多模态应用正从理解走向生成和模拟。同时，**Agent（Agent-A1, needle）** 和 **代码专属模型**（gemma-4-...-agentic）的涌现，预示着LLM的核心定位正从“知识问答”转向“任务执行”。

---

#### **值得探索**

1.  **zai-org/GLM-5.2**：作为本周点赞最高的原生模型，它代表了国产大模型在MoE架构上的最新进展。研究其训练策略与架构细节，对于理解下一代高效LLM至关重要。 ([链接](https://huggingface.co/zai-org/GLM-5.2))
2.  **Cactus-Compute/needle**：该模型专注于函数调用和工具使用，是探索AI Agent基础设施的一个优秀样本。试用它可以让您直接感受到LLM从“只会说”到“能够做”的质变。([链接](https://huggingface.co/Cactus-Compute/needle))
3.  **prism-ml/Ternary-Bonsai-27B-gguf**：此模型是前沿量化技术的代表。对于关注模型压缩、边缘部署或对低资源推理有强烈需求的开发者来说，体验这个27B的2-bit模型，将是一次见证“小身材大能量”的绝佳机会。([链接](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf))

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*