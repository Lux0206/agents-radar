# Hugging Face 热门模型日报 2026-07-03

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-03 10:16 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的2026年7月3日数据生成的《Hugging Face热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026年7月3日**

#### **今日速览**

本周 Hugging Face 生态显现出几个关键信号：**GLM-5.2** 系列凭借其 MoE 架构和 NVIDIA 的 NVFP4 量化版本，成为社区讨论度最高的模型家族之一。**多模态融合**趋势进一步深化，大量模型同时具备文本生成与图像理解能力（`image-text-to-text`）。**量化与微调**活动空前活跃，GGUF 格式模型占据榜单半壁江山，特别是针对 Qwen 和 Gemma 系列的高强度社区微调（如安全对齐“abliterated”版本和编码增强版）显示开发者正在深度定制基础模型。此外，NVIDIA 的 `LocateAnything-3B` 在视觉定位任务上异军突起，展示了大模型落地的专业化方向。

---

#### **热门模型分类整理**

##### 🧠 **语言模型（LLM、对话模型、指令微调）**

*   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** (zai-org | 👍 3,295 | ⬇️ 191k)
    *   **说明**：本周点赞冠军。智谱GLM系列的第五代大规模MoE模型，展示了国产开源模型的强大生态影响力。
*   **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)** (deepseek-ai | 👍 316 | ⬇️ 9k)
    *   **说明**：DeepSeek的第四代旗舰Pro版本，带DSpark加速技术，代表了前沿大模型的持续迭代。
*   **[deepreinforce-ai/Ornith-1.0-397B](https://huggingface.co/deepreinforce-ai/Ornith-1.0-397B)** (deepreinforce-ai | 👍 199 | ⬇️ 8k)
    *   **说明**：Ornith系列的超大规模版本（397B），基于Qwen 3.5 MoE，适合企业级高复杂度推理场景。
*   **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LFM2.5-230M)** (LiquidAI | 👍 194 | ⬇️ 30k)
    *   **说明**：小而美的代表。Liquid AI推出的230M参数小模型，适合边缘设备部署。

##### 🎨 **多模态与生成（图像、视频、文本到X）**

*   **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** (nvidia | 👍 2,583 | ⬇️ 1.1M)
    *   **说明**：NVIDIA出品的通用视觉定位模型，能够理解自然语言指令在图像中精准定位物体，下载量极高。
*   **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** (krea | 👍 468 | ⬇️ 84k)
    *   **说明**：Krea系列的第二代Turbo版文生图模型，主打快速生成与高清画质，是创意设计领域的热门工具。
*   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** (baidu | 👍 1,668 | ⬇️ 885k)
    *   **说明**：百度的无限类OCR模型，在图像到文本任务上表现卓越，社区评价极高的实用型模型。
*   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored...](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** (HauhauCS | 👍 2,410 | ⬇️ 3.0M)
    *   **说明**：本周下载量之王（超300万）。基于Qwen 3.6的无审查、激进风格微调版，满足特定用户对“去限制”和多模态能力的需求，争议与热度并存。

##### 🔧 **专用模型（代码、安全、表格、分类）**

*   **[yuxinlu1/gemma-4-12B-coder-fable5...](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** (yuxinlu1 | 👍 2,573 | ⬇️ 628k)
    *   **说明**：专为代码和推理优化的Gemma 4模型微调版，采用Fable5和Composer技术，在编程赛道表现抢眼。
*   **[BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6](https://huggingface.co/BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6)** (BugTraceAI | 👍 121 | ⬇️ 11k)
    *   **说明**：专注网络安全和漏洞分析的大模型，反映了AI在特定安全领域的深入应用。
*   **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)** (google | 👍 133 | ⬇️ 450)
    *   **说明**：Google发布的基础表格数据基础模型（TabFM），用于表格分类和回归任务，实现零样本预测。
*   **[nationaldesignstudio/rampart](https://huggingface.co/nationaldesignstudio/rampart)** (nationaldesignstudio | 👍 108 | ⬇️ 1.1k)
    *   **说明**：基于BERT的PII（个人身份信息）检测模型，适用于数据安全和隐私合规场景。

##### 📦 **微调与量化（社区微调、GGUF、AWQ）**

*   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** (empero-ai | 👍 1,305 | ⬇️ 1.4M)
    *   **说明**：基于Qwen 3.5的GGUF量化版，融合了Mythos数据集，下载量超百万，是本地部署和推理优化的首选。
*   **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)** (nvidia | 👍 210 | ⬇️ 190k)
    *   **说明**：NVIDIA专门为GLM-5.2推出的4位浮点量化版，专为自家GPU优化，性能与精度平衡极佳。
*   **[huihui-ai/Huihui-GLM-5.2-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-GLM-5.2-abliterated-GGUF)** (huihui-ai | 👍 139 | ⬇️ 3.7k)
    *   **说明**：针对GLM-5.2的“安全对齐消除”（abliterated）微调版，社区探索模型无审查能力的重要尝试。
*   **[Jackrong/Qwopus3.6-35B-A3B-Coder-MTP-GGUF](https://huggingface.co/Jackrong/Qwopus3.6-35B-A3B-Coder-MTP-GGUF)** (Jackrong | 👍 120 | ⬇️ 45k)
    *   **说明**：基于Qwen 3.6的编码专用版量化模型，体现了“量化+专业化”的社区微调趋势。

---

#### **生态信号**

1.  **模型家族势头分析**：**GLM-5.2** 和 **Qwen 3.x** 系列无疑是最强势的两大阵营。GLM凭借其原创MoE架构和NVIDIA等巨头的生态支持，迅速占领了主流认知。而Qwen系列则展现出极强的社区可塑性，围绕其诞生的微调、量化版本（如`Qwythos`, `Qwopus`）层出不穷，生态深度惊人。
2.  **开源权重 vs 闭源**：本周趋势榜上，**权重完全开放**的模型（如GLM-5.2, Qwen系列）占据了绝对主导地位。这表明社区创新高度依赖开放的权重，闭源模型的影响力在HF热度榜上受到挑战。
3.  **量化与微调活动**：**GGUF** 格式一统天下，几乎所有主流模型都有对应的GGUF版本，这标志着“人人都能本地跑大模型”的时代已经到来。同时，社区微调不再局限于“对话”，而是走向“深度定制”，出现了大量针对**代码（Coder）、安全（Security）、知识（Uncensored）** 的专业化微调版本，这表明大模型正在从通用工具演变为可被任意定制的能力基座。

---

#### **值得探索**

1.  **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)**：如果你拥有NVIDIA显卡，这是体验顶级MoE模型GLM-5.2潜力的最佳入口。它展示了硬软件协同优化的最高水平，值得所有对推理性能有极致要求的用户尝试。
2.  **[BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6](https://huggingface.co/BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6)**：这是大模型垂直化落地的绝佳案例。对于网络安全从业者或对AI攻防感兴趣的研究者，这个模型将是一个强大的辅助工具，代表了“AI+专业领域”的未来方向。
3.  **[HauhauCS/Qwen3.6-35B-A3B-Uncensored...](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**：虽然比较“另类”，但它的超高下载量值得关注。它代表了社区对模型控制权（去审查）的强烈需求。探索它可以让你理解在“安全对齐”之外，社区如何看待模型的自由度和潜在风险。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*