# Hugging Face 热门模型日报 2026-07-12

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-12 03:24 UTC

---

好的，作为AI模型生态分析师，这是为您整理的2026年7月12日《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-12**

#### **今日速览**

今日榜单呈现出几个明显趋势：首先，**Qwen 系列 (Qwen3.5/3.6) 生态影响力持续扩大**，大量微调、量化及模板修复模型占据多个席位，显示了社区对其的深度依赖。其次，**MoE (混合专家) 架构成为主流**，从百亿到千亿参数级别的模型普遍采用此架构，如GLM-5.2、InternScience/Agents-A1和NVIDIA的Nemotron系列。最后，**NVIDIA 模型表现抢眼**，其推出的视觉定位模型 `LocateAnything-3B` 获得极高关注，标志着其在多模态领域的强劲发力。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

-   **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** | 作者: tencent | 点赞: 699 | 下载: 8,210
    -   腾讯发布的新一代语言模型，基于HyV3架构，专注于文本生成。
-   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | 作者: zai-org | 点赞: 3,836 | 下载: 421,270
    -   GLM系列最新版本，采用MoE架构，在对话任务上表现突出，社区热度极高。
-   **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)** | 作者: InternScience | 点赞: 495 | 下载: 28,141
    -   基于Qwen3.5-MoE架构的智能体模型，专为Agent任务设计，反映了Agent应用的热潮。
-   **[meituan-longcat/LongCat-2.0](https://huggingface.co/meituan-longcat/LongCat-2.0)** | 作者: meituan-longcat | 点赞: 177 | 下载: 1,572
    -   美团发布的长上下文对话模型，第二代版本，聚焦于处理长文本对话场景。
-   **[nvidia/Nemotron-Labs-Audex-30B-A3B](https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B)** | 作者: nvidia | 点赞: 122 | 下载: 743
    -   NVIDIA的30B参数MoE模型（激活3B），延续Nemotron系列高性能特性，面向实验室场景。
-   **[nvidia/NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4](https://huggingface.co/nvidia/NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4)** | 作者: nvidia | 点赞: 107 | 下载: 30,418
    -   75B参数的MoE模型（激活9B），采用创新的NVFP4量化格式，在推理效率上树立新标杆。
-   **[SupraLabs/Supra-Router-51M](https://huggingface.co/SupraLabs/Supra-Router-51M)** | 作者: SupraLabs | 点赞: 99 | 下载: 1,275
    -   一个极小的51M参数路由模型，用于在多个专家模型间进行任务分发，是MoE生态的重要组件。
-   **[mistralai/Leanstral-1.5-119B-A6B](https://huggingface.co/mistralai/Leanstral-1.5-119B-A6B)** | 作者: mistralai | 点赞: 189 | 下载: 350
    -   Mistral AI推出的119B参数MoE模型（激活6B），聚焦效率，是“小参数量，大能力”路线的代表。
-   **[openbmb/MiniCPM5-1B](https://huggingface.co/openbmb/MiniCPM5-1B)** | 作者: openbmb | 点赞: 911 | 下载: 366,106
    -   MiniCPM系列第五代，仅1B参数即展现出强大的文本生成能力，是端侧部署的潜力股。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

-   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | 作者: empero-ai | 点赞: 2,016 | 下载: 1,944,961
    -   基于Qwen3.5的9B多模态模型，经过社区风格微调并量化，支持图文理解，下载量巨大。
-   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | 作者: baidu | 点赞: 1,931 | 下载: 1,380,690
    -   百度推出的通用OCR模型，能力覆盖所有文字识别任务，功能强大且实用。
-   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | 作者: HauhauCS | 点赞: 2,653 | 下载: 2,641,936
    -   基于最新Qwen3.6的35B MoE模型，经过去审查（Uncensored）和激进风格微调，社区关注度极高。
-   **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** | 作者: nvidia | 点赞: 2,707 | 下载: 1,472,194
    -   NVIDIA推出的视觉定位模型，能够根据文本描述精确定位图像中的任何物体，技术领先。
-   **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** | 作者: krea | 点赞: 588 | 下载: 168,154
    -   Krea公司发布的文本到图像生成模型，作为Krea-2的加速版，更强调生成速度和性能。
-   **[CohereLabs/cohere-transcribe-arabic-07-2026](https://huggingface.co/CohereLabs/cohere-transcribe-arabic-07-2026)** | 作者: CohereLabs | 点赞: 90 | 下载: 7,687
    -   Cohere推出的阿拉伯语自动语音识别（ASR）模型，填补了特定语种的空白。
-   **[Alissonerdx/LTX-Best-Face-ID](https://huggingface.co/Alissonerdx/LTX-Best-Face-ID)** | 作者: Alissonerdx | 点赞: 101 | 下载: 0
    -   基于LTX视频模型的LoRA，专注于在生成视频时保持人物身份一致性。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

-   **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)** | 作者: google | 点赞: 349 | 下载: 20,110
    -   谷歌发布的表格数据基础模型，支持零样本分类和回归，为结构化数据分析提供强大工具。
-   **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)** | 作者: OpenMOSS-Team | 点赞: 110 | 下载: 12,817
    -   MOSS团队的音频转文字+说话人分离模型，专为复杂的多人会议场景设计。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

-   **[bottlecapai/ThinkingCap-Qwen3.6-27B](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)** | 作者: bottlecapai | 点赞: 236 | 下载: 4,128
    -   对Qwen3.6-27B进行推理增强微调（Thinking Cap）的模型，提升了模型在复杂推理任务上的表现。
-   **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** | 作者: froggeric | 点赞: 852 | 下载: 0
    -   专门修复Qwen系列模型聊天模板错误的库，解决了社区使用中的痛点，实用价值高。
-   **[unsloth/DeepSeek-V4-Flash-GGUF](https://huggingface.co/unsloth/DeepSeek-V4-Flash-GGUF)** | 作者: unsloth | 点赞: 142 | 下载: 38,922
    -   Unsloth团队推出的DeepSeek V4 Flash模型GGUF量化版，方便本地高效部署。
-   **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** | 作者: deepreinforce-ai | 点赞: 853 | 下载: 1,216,495
    -   名为Ornith的35B模型GGUF量化版，下载量破百万，社区应用广泛。
-   **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)** | 作者: yuxinlu1 | 点赞: 1,150 | 下载: 436,530
    -   在Gemma-4-12B基础上进行高度个性化和复合微调的版本，并量化为GGUF，面向Agent和代码场景。
-   **[GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF](https://huggingface.co/GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF)** | 作者: GnLOLot | 点赞: 192 | 下载: 29,887
    -   对MiniCPM5-1B进行思维链微调并量化的GGUF版本，将小模型的推理能力推向新高度。
-   **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)** | 作者: unsloth | 点赞: 1,049 | 下载: 2,904,169
    -   最新版Qwen3.6-27B的GGUF量化版，下载量近300万，是当前社区最主流的本地部署方案之一。

#### **生态信号**

1.  **Qwen 家族生态霸权**：以Qwen 3.5/3.6为核心的上百个衍生模型（微调、量化、LoRA）霸榜，表明一个成功的开源模型能催生庞大的社区生态，形成“平台级”影响。
2.  **MoE 成为标准配置**：从千亿参数的Nemotron到百亿参数的GLM-5.2，乃至1B级别的小模型，MoE架构因其极致的效率（小激活参数、大总参数）已从探索走向成熟，成为模型设计的主流范式。
3.  **量化社区空前活跃**：以Unsloth、empero-ai为代表的社区力量，通过GGUF量化极大降低了先进模型的使用门槛，推动“私有化部署”和“应用层创新”迅速普及。`unsloth/Qwen3.6-27B-MTP-GGUF`近300万的下载量是这一趋势最有力的证明。

#### **值得探索**

1.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**: 堪称“万物定位器”，它将视觉和语言的交叉理解提升到了新高度。无论是分析师在图像中寻找关键信息，还是开发者构建高级搜索应用，这个模型都极具实用和研究价值。
2.  **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)**: 如果你希望体验当前社区最先进的开源模型，这就是最好的入口之一。它代表了Qwen 3.6的强大能力与GGUF量化便捷性的完美结合，是驱动本地或边缘设备AI应用的基石。
3.  **[openbmb/MiniCPM5-1B](https://huggingface.co/openbmb/MiniCPM5-1B)**: 是“小模型大能力”路线的典范。对于研究如何在资源受限设备（如手机、PC）上运行高质量大模型的工程师和研究者来说，这个模型是必看的研究对象。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*