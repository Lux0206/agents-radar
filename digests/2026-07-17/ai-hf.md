# Hugging Face 热门模型日报 2026-07-17

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-17 03:12 UTC

---

# Hugging Face 热门模型日报（2026-07-17）

## 今日速览

本周 Hugging Face 热度集中在**三进制/1-bit 量化技术**的爆发式增长，以 prism-ml 的 `Bonsai-27B` 系列为代表的极端量化模型下载量惊人，标志着边缘部署与消费级硬件推理进入新阶段。同时，**腾讯 Hy3**、**百度 Unlimited-OCR** 等大厂开源多模态模型保持强劲势头，**GLM-5.2** 凭借 MoE 架构与 DSA 优化成为周赞榜冠军。社区微调活动围绕 **Qwen3.6** 与 **MiniCPM5** 展开，多种 GGUF 与思考链变体涌现。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**  
  作者: zai-org | 👍 4,030 | ⬇ 513,061  
  基于 MoE 与 DSA 稀疏注意力技术的混合专家模型，在推理效率和质量间取得优异平衡，成为本周点赞数第一。

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**  
  作者: empero-ai | 👍 2,239 | ⬇ 2,042,670  
  Qwen3.5 精调变体的 GGUF 量化版，融合 Claude 风格思考链，下载量突破 200 万，社区口碑极佳。

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**  
  作者: HauhauCS | 👍 2,788 | ⬇ 2,328,315  
  Qwen3.6 的 MoE 版（35B 总参、3B 激活），取消内容审查限制并强化"进攻性"输出风格，下载量极高但争议性大。

- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)**  
  作者: deepreinforce-ai | 👍 902 | ⬇ 1,785,575  
  35B 参数级开源通用语言模型，GGUF 量化后适配 llama.cpp，兼顾性能与部署友好性。

- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**  
  作者: yuxinlu1 | 👍 1,208 | ⬇ 506,068  
  基于 Gemma 4 的 Agent 专用 GGUF 模型，面向终端与编码任务，结合复合思考链（Fable5）提升工具调用能力。

- **[InternetScience/Agents-A1](https://huggingface.co/InternetScience/Agents-A1)**  
  作者: InternScience | 👍 568 | ⬇ 33,400  
  基于 Qwen3.5 MoE 的 Agent 模型，支持图像与文本混合输入，在代理自动化场景表现突出。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[thinkingmachines/Inkling](https://huggingface.co/thinkingmachines/Inkling)**  
  作者: thinkingmachines | 👍 822 | ⬇ 4  
  全新多模态对话模型（image-text-to-text），支持图文混合推理，标签显示为"inkling_mm_model"，代表多模态新架构探索。

- **[tencent/Hy3](https://huggingface.co/tencent/Hy3)**  
  作者: tencent | 👍 813 | ⬇ 11,849  
  腾讯开源的 Hunyuan 第三代文本生成模型，在长文本生成与结构化输出上有显著提升，生态合作潜力大。

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**  
  作者: baidu | 👍 2,011 | ⬇ 1,852,722  
  百度开源的无限制 OCR 模型，能够处理复杂场景文字识别，下载量破百万，企业级应用价值高。

- **[bottlecapai/ThinkingCap-Qwen3.6-27B](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)**  
  作者: bottlecapai | 👍 390 | ⬇ 8,238  
  结合 Qwen3.6 的多模态思考链模型，强推理与视觉理解双通道并行，适合需要"边看边想"的任务。

- **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)**  
  作者: OpenMOSS-Team | 👍 234 | ⬇ 75,105  
  音频-文本多模态模型，支持转写加说话人分离（Diarize），开源语音处理新标杆。

- **[Wan-AI/Wan-Dancer-14B](https://huggingface.co/Wan-AI/Wan-Dancer-14B)**  
  作者: Wan-AI | 👍 92 | ⬇ 1,884  
  图像到视频舞蹈生成模型（14B），基于 Diffusers，在动作连贯性与角色一致性上有突破。

### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[ATH-MaaS/OvisOCR2](https://huggingface.co/ATH-MaaS/OvisOCR2)**  
  作者: ATH-MaaS | 👍 137 | ⬇ 3,678  
  基于 Qwen3.5 的专用 OCR 模型，针对文档版面分析与文字抽取进行了专项优化。

- **[Cactus-Compute/needle](https://huggingface.co/Cactus-Compute/needle)**  
  作者: Cactus-Compute | 👍 249 | ⬇ 733  
  基于 JAX 的函数调用与工具使用模型，轻量级设计，强调可组合性与 Agent 工作流集成。

### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)**  
  作者: prism-ml | 👍 610 | ⬇ 74,007  
  首次将三进制量化（2-bit）应用于 27B 级模型，在极小显存占用下保持可用质量，技术突破性极高。

- **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)**  
  作者: prism-ml | 👍 343 | ⬇ 559,267  
  革命性的 1-bit（二元）量化 27B 模型，是当前最激进的压缩方案，专为极端资源受限场景设计。

- **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)**  
  作者: froggeric | 👍 925 | ⬇ 0  
  非权重型仓库，提供了经过修复的 Qwen 聊天模板（Jinja），解决了大量社区误用问题，0 度下载仍获 925 赞，需求巨大。

- **[unsloth/Qwen3.6-27B-NVFP4](https://huggingface.co/unsloth/Qwen3.6-27B-NVFP4)**  
  作者: unsloth | 👍 216 | ⬇ 1,712,974  
  Unsloth 推出的 NVFP4（NVIDIA 4-bit 浮点）量化版 Qwen3.6-27B，兼顾速度与精度，极受笔记本部署用户欢迎。

- **[GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF](https://huggingface.co/GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF)**  
  作者: GnLOLot | 👍 265 | ⬇ 121,296  
  极小模型（1B）通过渐进式思考链微调实现类 Claude 推理效果，验证了小参数量模型通过精细训练也能接近大模型水平。

- **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)**  
  作者: jlnsrk | 👍 121 | ⬇ 2,621  
  为 GLM-5.2 定制的 int4 量化版，采用 Colibri 专家流式技术，使 MoE 模型在 CPU 上也能高效推理。

## 生态信号

### 模型家族势头正旺
**Qwen 系列**依然是最活跃的微调基座，Qwen3.5/3.6 变体（Qwythos、ThinkingCap、Uncensored 版）占据榜单半壁江山。**GLM-5.2** 以 MoE+DSA 架构赢得大量关注，有望与 Qwen 形成双雄格局。

### 开源权重 vs 闭源趋势
本周榜单几乎被**纯开源权重**模型占领，仅有少量衍生版的“风格蒸馏”涉及闭源模型。大厂（腾讯、百度）开源力度不减，社区更倾向在开源基座上做极端量化或功能定制，而非追摩闭源接口。

### 量化与微调风向
**三进制/1-bit 量化**是本周最具创新性的信号，prism-ml 的 Bonsai 系列证明低于 2-bit 的极端量化在 27B 级模型上可行，可能重塑边缘 AI 推理。**GGUF 格式**的统治地位进一步巩固，NVFP4 等新量化格式开始争夺份额。**Chat 模板修复**（如 Qwen-Fixed-Chat-Templates）的流行说明社区对“开箱即用”体验的重视程度已达到新高度。

## 值得探索

- **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)** — 三进制量化的里程碑，验证了 2-bit 以下并非不可能，是研究极限压缩技术的绝佳起点。

- **[bottlecapai/ThinkingCap-Qwen3.6-27B](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)** — 多模态+思考链的融合创新，代表了下一代数理推理与视觉理解一体化模型的演进方向。

- **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** — 虽然不提供权重，但作为开源社区“基础设施”类贡献的典范，展示了非模型仓库同样能创造巨大价值。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*