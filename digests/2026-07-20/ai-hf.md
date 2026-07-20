# Hugging Face 热门模型日报 2026-07-20

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-20 03:34 UTC

---

好的，作为AI模型生态分析师，以下是根据您提供的2026年7月20日Hugging Face热门模型数据生成的日报。

---

## 🤗 Hugging Face 热门模型日报 (2026-07-20)

### 📈 今日速览

本周Hugging Face生态呈现“多极化”爆发趋势。**百度**的`Unlimited-OCR`与**Google**的`Gemma-4-31B-it`凭借强大的基础能力，分别引领了工具型应用与通用多模态对话的下载与点赞热潮。与此同时，以**zai-org**的`GLM-5.2`和**empero-ai**的`Qwythos-9B`系列为代表的高效MoE架构与强化推理模型获得了极高关注。值得注意的是，以**prism-ml**为代表的极低比特（1-bit/2-bit）量化技术生态正在迅速成熟，并催生了诸如`Bonsai-27B`系列的大量衍生模型。此外，视频生成领域出现新星`Wan-Dancer-14B`，表明该赛道竞争仍在加剧。

### 🔥 热门模型分类解读

#### 🧠 语言模型（LLM、对话模型、指令微调）

*   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** ⭐4,172 | ⬇️536k
    *   作者: zai-org | 任务: text-generation
    *   **一句话说明**: 智谱AI推出的全新MoE架构大模型，凭借高效的DSA（动态稀疏注意力）和强大性能，成为本周讨论度最高的开源模型之一。
*   **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** ⭐836 | ⬇️13.7k
    *   作者: tencent | 任务: text-generation
    *   **一句话说明**: 腾讯混元系列最新版本，作为基础模型被广泛用于下游微调，是社区量化版本的重要源模型。
*   **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)** ⭐584 | ⬇️35.8k
    *   作者: InternScience | 任务: text-generation
    *   **一句话说明**: 基于Qwen3.5-MoE的智能体专用模型，针对工具调用和任务规划进行了优化，反映了“模型即智能体”的趋势。

#### 🎨 多模态与生成（图像、视频、音频、文本到X）

*   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** ⭐2,350 | ⬇️2.1M
    *   作者: empero-ai | 任务: image-text-to-text
    *   **一句话说明**: 融合了Qwen3.5与“Mythos”推理范式的视觉语言模型，GGUF量化版本爆火，下载量巨大，说明小尺寸强推理模型需求旺盛。
*   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** ⭐2,200 | ⬇️2.1M
    *   作者: baidu | 任务: image-text-to-text
    *   **一句话说明**: 百度开源的无限制OCR模型，在复杂场景下表现优异，成为该领域最具影响力的工具型模型。
*   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** ⭐2,903 | ⬇️2.1M
    *   作者: HauhauCS | 任务: image-text-to-text
    *   **一句话说明**: Qwen3.6的“去审查”社区微调版，激活参数仅3B的MoE架构与激进风格设定，在特定社区内极受欢迎。
*   **[google/gemma-4-31B-it](https://huggingface.co/google/gemma-4-31B-it)** ⭐3,276 | ⬇️12.3M
    *   作者: google | 任务: image-text-to-text
    *   **一句话说明**: Google最新的开源多模态模型，在多个基准上表现出色，其庞大的下载量彰显了其作为基础模型的地位。
*   **[Wan-AI/Wan-Dancer-14B](https://huggingface.co/Wan-AI/Wan-Dancer-14B)** ⭐129 | ⬇️2.4k
    *   作者: Wan-AI | 任务: image-to-video
    *   **一句话说明**: 新发布的图生视频模型，专注于“舞蹈”场景生成，表明视频生成正在向具体、高动态的垂直领域深化。
*   **[AngelSlim/Hy3-GGUF](https://huggingface.co/AngelSlim/Hy3-GGUF)** ⭐139 | ⬇️109.7k
    *   作者: AngelSlim | 任务: text-generation
    *   **一句话说明**: 腾讯Hy3模型的GGUF量化版本，让用户在消费级硬件上运行大模型成为可能，推动了边缘部署。
*   **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)** ⭐280 | ⬇️87.5k
    *   作者: OpenMOSS-Team | 任务: audio-text-to-text
    *   **一句话说明**: 专注于音频转录与说话人分离的模型，标志着MOSS生态向完整语音交互链演进。

#### 🔧 专用模型（代码、数学、医疗、嵌入）

*   **(本周热门榜中暂无突出专用的代码、数学、医疗模型)**

#### 📦 微调与量化（社区微调、GGUF、AWQ）

*   **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)** ⭐795 | ⬇️338.9k
    *   作者: prism-ml | 任务: text-generation
    *   **一句话说明**: 使用三值量化（Ternary）的27B模型GGUF版，以极低比特牺牲少量性能换取极高效率，是量化技术的里程碑。
*   **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)** ⭐503 | ⬇️1.2M
    *   作者: prism-ml | 任务: text-generation
    *   **一句话说明**: 采用1比特量化的27B模型GGUF版，下载量巨大，说明社区对“人人可运行大语言模型”的追求空前强烈。
*   **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** ⭐948 | ⬇️0
    *   作者: froggeric | 任务: N/A
    *   **一句话说明**: 修复Qwen系列聊天模板的实用工具型仓库，看似不起眼，却解决了开发者大规模部署的核心痛点。
*   **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)** ⭐142 | ⬇️4k
    *   作者: jlnsrk | 任务: N/A
    *   **一句话说明**: GLM-5.2的4比特CPU推理版本（Colibri），使MoE大模型在无GPU环境下也能流畅运行，拓展了使用场景。

### 🌿 生态信号分析

1.  **模型家族**：**Qwen (3.5/3.6)** 生态成为绝对主导，衍生出大量微调、量化、多模态变体。**MOSS**和**GLM**两大国产模型家族也势头强劲，形成了三足鼎立的态势。**Gemma-4**开始挑战传统格局。
2.  **开源 vs 闭源**：以`GLM-5.2`、`Gemma-4`、`Hy3`为代表的高性能开源权重模型不断涌现，其能力正在接近或部分超越闭源模型。开源社区强大的“二次开发”能力（微调、量化、修补）正在加速这一趋势。
3.  **量化与微调**：1-bit量化已成为现实，`Bonsai-27B`系列的火爆证明了其巨大的实用价值。微调活动极度活跃，主要集中在**去审查**、**角色扮演**（如`Krea`系列LoRA）和**增强推理能力**（如`Qwythos`）三个方面。GGUF格式是绝对主流，而MLX（Apple Silicon）生态也在迅速壮大。

### 💡 值得探索

1.  **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)** (1-bit): 强烈建议任何对本地部署大模型感兴趣的开发者尝试。这是目前最激进、也最成功的效率优化模型。在4-8GB内存的设备上体验27B模型的对话能力，将重新定义你对模型量化的认知。
2.  **[Wan-AI/Wan-Dancer-14B](https://huggingface.co/Wan-AI/Wan-Dancer-14B)** (Image-to-Video): 关注视频生成领域的朋友不应错过。在Sora热潮后，**Wan-Dancer**展示了如何通过垂直领域（舞蹈）的数据和优化，在可控性和质量上取得突破。它代表了“可控、专业、高质量”的下一代视频生成方向。
3.  **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)** (CPU推理): 对于缺乏GPU资源的开发者和研究人员，这个模型是福音。它证明了MoE模型通过“专家流式”（Expert-Streaming）技术，可以在CPU上实现可用的推理速度，为AI应用的广泛普惠提供了新路径。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*