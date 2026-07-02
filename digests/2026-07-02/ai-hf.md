# Hugging Face 热门模型日报 2026-07-02

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-02 10:20 UTC

---

好的，作为 AI 模型生态分析师，以下是基于你提供的数据生成的《Hugging Face 热门模型日报》。

---

### Hugging Face 热门模型日报 (2026-07-02)

#### 今日速览

本周 Hugging Face 生态呈现三大看点：**百度**的 `Unlimited-OCR` 凭借极高的下载量成为多模态领域的“爆款”，显示出工业级场景对通用 OCR 能力的迫切需求；**GLM-5.2** 家族生态爆发，社区涌现出大量由其衍生的量化 (`unsloth`)、破解版 (`abliterated`) 及 NVIDIA 优化版，证明了其极高的可玩性和部署潜力；**Agent 与工具调用**成为新共识，涌现出 `Qwen-AgentWorld` 和 `InternScience/Agents-A1` 等专为 Agent 设计的模型，标志着模型预训练方向正从“单纯对话”向“世界模型与行动”演进。

#### 热门模型分类

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** (zai-org, 3,202 👍, 176k ⬇️)  
  本周点赞数最高的模型，基于 MoE 架构的通用对话模型，凭借强大的性能和开放性成为社区焦点。
- **[deepreinforce-ai/Ornith-1.0-397B](https://huggingface.co/deepreinforce-ai/Ornith-1.0-397B)** (deepreinforce-ai, 192 👍, 7k ⬇️)  
  deepreinforce-ai 的旗舰级 MoE 大模型，主打视觉与文本的深度融合，代表了社区对大参数多模态模型的持续探索。
- **[meituan-longcat/LongCat-2.0](https://huggingface.co/meituan-longcat/LongCat-2.0)** (meituan-longcat, 152 👍, 0 ⬇️)  
  美团发布的评估结果仓库，尽管无权重，但其极高的关注度暗示了业内对长上下文模型评测标准的高度兴趣。
- **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LiquidAI/LFM2.5-230M)** (LiquidAI, 185 👍, 26k ⬇️)  
  Liquid AI 推出的超轻量级语言模型，证明了在极低参数量下也能保持竞争力的趋势，适用于边缘计算。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** (baidu, 1,615 👍, 758k ⬇️)  
  百度出品，通用无限制 OCR 模型，下载量接近百万，几乎成为文档数字化和自动化流程的标配工具。
- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** (krea, 446 👍, 69k ⬇️)  
  Krea 的第二代文生图模型的加速版，基于 Diffusers，在图像生成质量与推理速度之间取得了良好平衡。
- **[fal/LTX-2.3-3DREAL-LoRA](https://huggingface.co/fal/LTX-2.3-3DREAL-LoRA)** (fal, 138 👍, 0 ⬇️)  
  图像转视频领域的实用 LoRA，专注于生成高保真的 3D 风格视频，展示了社区在视频生成控制力上的微创新。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** (nvidia, 2,558 👍, 1M ⬇️)  
  英伟达的通用视觉定位模型，可以识别和定位图像中的任意物体，其下载量破百万，足见其在 AI 辅助设计、自动驾驶等领域的巨大需求。
- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** (yuxinlu1, 2,557 👍, 614k ⬇️)  
  Gemma-4 系列的代码专用模型，社区对其代码生成与推理能力进行了深度调优，是程序员自动化编码的热门选择。
- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** (HauhauCS, 2,388 👍, 3M ⬇️)  
  基于 Qwen 3.6 的非审查版本，下载量突破 300 万，反映了社区对允许自由探索和行为多样性的“解禁”模型有巨大需求。
- **[BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6](https://huggingface.co/BugTraceAI/BugTraceAI-CORE-Ultra-27B-Q6)** (BugTraceAI, 113 👍, 8k ⬇️)  
  专注于网络安全的渗透测试模型，代表了 AI 在专业安全领域的垂直应用正在崛起。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** (empero-ai, 1,193 👍, 1.2M ⬇️)  
  基于 Qwen 3.5 的创意叙事模型量化版，1 亿 token 的微调数据使其在创意写作领域表现惊艳，下载量极高。
- **[unsloth/GLM-5.2-GGUF](https://huggingface.co/unsloth/GLM-5.2-GGUF)** (unsloth, 491 👍, 239k ⬇️)  
  unsloth 出品的 GLM-5.2 量化版，其核心价值在于让巨大的 MoE 模型在消费级硬件上流畅运行，极大降低了使用门槛。
- **[nvidia/GLM-5.2-NVFP4](https://huggingface.co/nvidia/GLM-5.2-NVFP4)** (nvidia, 202 👍, 159k ⬇️)  
  英伟达官方使用其 `ModelOpt` 工具对 GLM-5.2 进行的 4-bit 浮点量化，代表了技术与硬件结合的最前沿优化方案。

#### 生态信号

1.  **MoE (混合专家) 架构统治地位确立**: 本周 Top 10 模型中有 5 个明确标注为 MoE 架构（`GLM-5.2`, `Ornith-1.0-35B`, `Qwen-AgentWorld`, `Qwen3.6`），这已成为行业共识，即以更低成本激活巨量参数。
2.  **“Agent 原生”模型兴起**: `Qwen-AgentWorld` 和 `Agents-A1` 的出现是一个强烈信号。模型开始专为工具调用、世界交互和行动链设计，预示着下一代模型的竞争焦点将从“谁更聪明”转向“谁更能执行任务”。
3.  **量化与微调生态空前繁荣**: 社区微调（如 `abliterated`、`Uncensored`）和量化（`GGUF`, `NVFP4`）活动异常活跃。几乎所有热门基础模型（GLM-5.2, Qwen3.6）都迅速被社区“二创”，这表明 AI 的“平民化”（人人可本地运行、自定义行为）已成为不可逆的趋势。

#### 值得探索

1.  **🤖 [nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**: 如果你从事任何需要计算机视觉或图像理解的工作，这个模型是目前最通用的一个“视觉瑞士军刀”，下载量已证明其价值。
2.  **🧠 [zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**: 如果你在寻找一个强大的基础模型进行二次开发或研究最新 MoE 技术，GLM-5.2 是本周的绝对核心，生态最为完善。
3.  **🛠️ [Qwen/Qwen-AgentWorld-35B-A3B](https://huggingface.co/Qwen/Qwen-AgentWorld-35B-A3B)**: 如果你想站在 AI 发展的下一个风口（Agent），这个模型代表了最前沿的探索方向，值得深入研究其在世界模型和工具调用上的能力。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*