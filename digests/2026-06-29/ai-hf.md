# Hugging Face 热门模型日报 2026-06-29

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-06-29 12:40 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供数据的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026年6月29日**

#### **1. 今日速览**

今日Hugging Face生态呈现出“三强争霸”与“新秀涌现”的态势。NVIDIA凭借 **GLM-5.2** 和 **Qwen-3.6** 系列的优化版（NVFP4）展示了其在模型部署领域的深厚功力，其中Qwen-3.6单模型下载量突破530万，社区热度极高。与此同时，以 **Qwen** 和 **DeepSeek** 为代表的国产模型家族依然势头强劲，其衍生版本（如Agent、Uncensored）大量涌现。值得注意的是，包括 **Krea 2**（图像生成）、**nvidia/LocateAnything**（视觉定位）在内的多模态与专用模型开始冲击榜单，反映出社区对实用性AI工具的需求正在上升。

#### **2. 热门模型分类**

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**
  - 作者: zai-org | 点赞: 2,882 | 下载: 133,350
  - 说明：本周点赞数最高的模型，基于GLM架构的MoE模型，在对话生成任务上表现出色，代表了国产大模型社区的活跃微调生态。
- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**
  - 作者: HauhauCS | 点赞: 2,322 | 下载: 3,089,944
  - 说明：周下载量超300万的“黑马”，基于Qwen 3.6的微调版本，以“无审查”和“激进”风格为标签，引发了社区对模型安全边界的广泛讨论。
- **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)**
  - 作者: deepseek-ai | 点赞: 201 | 下载: 5,460
  - 说明：DeepSeek V4系列的Pro版本，带有“DSpark”加速特性，代表了前沿推理模型的最新迭代。
- **[deepseek-ai/DeepSeek-V4-Flash-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-DSpark)**
  - 作者: deepseek-ai | 点赞: 87 | 下载: 2,239
  - 说明：与Pro版互补的Flash版本，注重推理速度和效率，共同完善DeepSeek V4生态。
- **[Chunjiang-Intelligence/DeepSeek-v4-Fable](https://huggingface.co/Chunjiang-Intelligence/DeepSeek-v4-Fable)**
  - 作者: Chunjiang-Intelligence | 点赞: 125 | 下载: 1,463
  - 说明：基于DeepSeek V4的社区微调版本，专注于网络安全领域，反映了大模型行业化定制的趋势。
- **[WeiboAI/VibeThinker-3B](https://huggingface.co/WeiboAI/VibeThinker-3B)**
  - 作者: WeiboAI | 点赞: 746 | 下载: 63,449
  - 说明：一个仅有3B参数的小模型，却在数学推理领域表现亮眼，证明了小模型在特定任务上的潜力。
- **[microsoft/FastContext-1.0-4B-SFT](https://huggingface.co/microsoft/FastContext-1.0-4B-SFT)**
  - 作者: microsoft | 点赞: 369 | 下载: 7,027
  - 说明：微软发布的长上下文模型（4B），针对长文本处理进行优化，代表了科技巨头在高效推理场景的布局。
- **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LiquidAI/LFM2.5-230M)**
  - 作者: LiquidAI | 点赞: 146 | 下载: 15,463
  - 说明：仅有230M参数的极轻量模型，探索在边缘设备上运行LLM的可能性。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**
  - 作者: baidu | 点赞: 1,316 | 下载: 362,945
  - 说明：百度出品的通用OCR模型，支持图片文字提取，因其强大的实用性和高完成度，成为本周最受欢迎的多模态模型。
- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)**
  - 作者: krea | 点赞: 378 | 下载: 38,454
  - 说明：强大的文生图模型Krea 2的Turbo加速版，快速生成高质量图像，展现了文生图赛道对速度的极致追求。
- **[krea/Krea-2-Raw](https://huggingface.co/krea/Krea-2-Raw)**
  - 作者: krea | 点赞: 239 | 下载: 27,464
  - 说明：Krea 2的基础版本，相比Turbo版更强调图像的原生质量与细节还原。
- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**
  - 作者: empero-ai | 点赞: 867 | 下载: 907,682
  - 说明：名为“Claude Mythos”的Qwythos-9B模型，具备图像理解能力，并提供了GGUF量化版，下载量极高。
- **[fal/LTX-2.3-3DREAL-LoRA](https://huggingface.co/fal/LTX-2.3-3DREAL-LoRA)**
  - 作者: fal | 点赞: 107 | 下载: 0
  - 说明：图生视频模型LTX-2.3的3D LoRA组件，专注于生成具有真实感的三维动态影像，代表了视频生成技术的垂直细分探索。
- **[nvidia/nemotron-3.5-asr-streaming-0.6b](https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b)**
  - 作者: nvidia | 点赞: 738 | 下载: 76,154
  - 说明：NVIDIA推出的流式语音识别模型（0.6B），支持实时语音转文字，对构建语音交互应用至关重要。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**
  - 作者: nvidia | 点赞: 2,454 | 下载: 728,320
  - 说明：本周表现极为亮眼的视觉定位模型，能根据指令精准定位图像中的任意物体，被评为“最有用的视觉工具之一”。
- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)**
  - 作者: yuxinlu1 | 点赞: 2,491 | 下载: 561,577
  - 说明：本周最热门的代码模型，基于Gemma 4微调，支持GGUF量化，专注于编程与推理任务，下载量巨大。
- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**
  - 作者: yuxinlu1 | 点赞: 824 | 下载: 241,409
  - 说明：Gemma 4的另一个微调版，专门针对“Agentic”和Terminal自动化场景设计，强调了AI Agent的自主操作能力。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)**
  - 作者: deepreinforce-ai | 点赞: 442 | 下载: 123,598
  - 说明：Ornith-1.0系列35B模型的GGUF版本，标志着社区对高性能中大型模型部署方案的需求旺盛。
- **[unsloth/GLM-5.2-GGUF](https://huggingface.co/unsloth/GLM-5.2-GGUF)**
  - 作者: unsloth | 点赞: 452 | 下载: 164,180
  - 说明：知名量化工具团队Unsloth出手，将热门的GLM-5.2模型转换为GGUF格式，极大降低其本地部署门槛。
- **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)**
  - 作者: nvidia | 点赞: 160 | 下载: 81,944
  - 说明：英伟达使用其NVFP4技术对GLM-5.2进行极致量化，展示了在保持性能的同时节省显存的能力。
- **[nvidia/Qwen3.6-35B-A3B-NVFP4](https://huggingface.co/nvidia/Qwen3.6-35B-A3B-NVFP4)**
  - 作者: nvidia | 点赞: 375 | 下载: 5,392,518
  - 说明：本周下载量最高的模型！NVidia优化的Qwen 3.6 MoE模型，凭借极致的推理效率和兼容性，成为本地部署的首选量化方案。
- **[unsloth/Qwen-AgentWorld-35B-A3B-GGUF](https://huggingface.co/unsloth/Qwen-AgentWorld-35B-A3B-GGUF)**
  - 作者: unsloth | 点赞: 98 | 下载: 116,693
  - 说明：Qwen AgentWorld模型的GGUF版本，结合了世界模型与Agent概念，是新兴方向上的量化尝试。

#### **3. 生态信号**

- **模型家族势头分析**：**Qwen 3.6** 家族和 **Gemma 4** 家族势头最旺，其社区微调版本（如Uncensored、Agentic、Coder）在榜单上占比极高，说明“强大基座 + 社区垂直优化”的模式已非常成熟。**DeepSeek V4** 和 **GLM-5.2** 也凭借其独特的MoE架构和高质量，成为微调的热门基座。
- **开源权重 vs 闭源趋势**：榜单上所有模型均为开源权重或优化版，未见闭源API模型上榜。这表明社区的主导力量依然在开源社区，特别是通过GGUF/NVFP4等量化技术，用户倾向于将强大的开源模型本地化。
- **值得关注的量化活动**：**GGUF** 与 **NVFP4** 是本周的绝对主流。Unsloth和NVIDIA分别是社区和官方量化技术的代表，前者降低了普通用户的使用门槛，后者则通过硬件优化提供了可能更优的性能。MoE模型的量化正在成为新热点。

#### **4. 值得探索**

1.  **🎯 [nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**: 如果您对“视觉理解”工作流感兴趣，这个模型不容错过。它比传统的目标检测更灵活，能以自然语言进行交互，潜力巨大。
2.  **🔬 [microsoft/FastContext-1.0-4B-SFT](https://huggingface.co/microsoft/FastContext-1.0-4B-SFT)**: 如果您在处理长文档或需要超长上下文的场景（如书籍理解、代码库分析），这款微软的模型值得深入研究。其在特定场景下的效率可能会令人惊喜。
3.  **⚡ [HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**: 尽管其“无审查”属性存在争议，但这恰恰代表了社区对创新边界和模型能力极限的探索。研究它的行为模式，对于理解“对齐”与“能力”的平衡非常有价值。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*