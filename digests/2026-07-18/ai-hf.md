# Hugging Face 热门模型日报 2026-07-18

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-18 02:50 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的数据生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-18**

#### **今日速览**

本周 Hugging Face 生态呈现三大特征：**“极致量化”与“混合专家模型（MoE）”成为绝对主旋律**。以 `prism-ml` 的 1-bit/ternary Bonsai 系列和 `empero-ai` 的 Qwythos 系列为代表，社区对在消费级硬件上运行大模型的热情空前高涨。同时，**大型科技公司与开源社区竞相发布新一代MoE模型**，如智谱的 `GLM-5.2` 和腾讯的 `Hy3`，展现了在保持高性能的同时降低推理成本的技术趋势。此外，**多模态能力持续下放**，百度重磅开源的 `Unlimited-OCR` 与 Qwen 3.6 系列视觉模型表现抢眼，标志着通用OCR与视觉理解进入新阶段。

#### **热门模型**

##### 🧠 **语言模型（LLM、对话模型、指令微调）**

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | 作者: zai-org | 👍 4,073 | ⬇️ 534,698
  - 智谱开源的新一代MoE大模型，凭借强大的对话与推理能力成为本周点赞冠军，标志着国产大模型在开源社区的强劲势头。
- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | 作者: HauhauCS | 👍 2,829 | ⬇️ 2,295,313
  - 基于Qwen3.6的MoE架构的“无审查”社区微调版，因其宽松的使用限制和活跃的社区二次开发而广受欢迎。
- **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)** | 作者: prism-ml | 👍 681 | ⬇️ 200,774
  - 首个将“三进制量化”应用于27B模型的GGUF版本，在极低比特下保留了惊人的对话质量，是边缘部署的明星。
- **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)** | 作者: prism-ml | 👍 398 | ⬇️ 1,045,182
  - Bonsai-27B的极致1-bit量化版，下载量惊人，证明了社区对“让任何设备都能运行大模型”的渴望。
- **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)** | 作者: InternScience | 👍 573 | ⬇️ 34,066
  - 上海AI实验室推出的Agent专用MoE模型，优化了工具调用与函数交互能力，代表LLM从“聊天”向“行动”的转变。
- **[Cactus-Compute/needle](https://huggingface.co/Cactus-Compute/needle)** | 作者: Cactus-Compute | 👍 257 | ⬇️ 874
  - 专为函数调用与工具使用设计的轻量级JAX模型，精准切入AI Agent开发者的核心需求。
- **[GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF](https://huggingface.co/GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking-GGUF)** | 作者: GnLOLot | 👍 273 | ⬇️ 154,762
  - 在1B小参数上通过蒸馏Claude Opus能力实现“思考”链的社区尝试，证明了小模型推理能力的潜力。
- **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** | 作者: tencent | 👍 820 | ⬇️ 12,719
  - 腾讯自研的Hunyuan系列第三代语言模型，在中文场景下展现出强大的基础能力，备受产业界关注。

##### 🎨 **多模态与生成（图像、视频、音频、文本到X）**

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | 作者: empero-ai | 👍 2,275 | ⬇️ 2,096,147
  - 融合了Qwen3.5视觉与Claude风格的强大多模态模型，其GGUF量化版下载量超200万，是当前最热的多模态推理选择。
- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | 作者: baidu | 👍 2,020 | ⬇️ 1,992,355
  - 百度重磅开源的通用OCR模型，号称“无限制”识别各类复杂场景文字，是本周最值得关注的垂直领域模型。
- **[thinkingmachines/Inkling](https://huggingface.co/thinkingmachines/Inkling)** | 作者: thinkingmachines | 👍 962 | ⬇️ 7,870
  - 一个全新的多模态原生模型，支持图像、文本、音频混合输入，代表多模态交互的未来形态。
- **[Wan-AI/Wan-Dancer-14B](https://huggingface.co/Wan-AI/Wan-Dancer-14B)** | 作者: Wan-AI | 👍 109 | ⬇️ 2,185
  - 图像生成视频（I2V）模型，专注于高动态舞蹈动作生成，为AI内容创作提供新工具。
- **[Alissonerdx/LTX-Best-Face-ID](https://huggingface.co/Alissonerdx/LTX-Best-Face-ID)** | 作者: Alissonerdx | 👍 178 | ⬇️ 0
  - 文本生成视频领域的身份保持LoRA，解决了视频生成中角色一致性的痛点。

##### 🔧 **专用模型（代码、数学、医疗、嵌入）**

- **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)** | 作者: OpenMOSS-Team | 👍 249 | ⬇️ 83,160
  - 复旦MOSS团队开发的音频转文字+说话人分离一体化模型，极大简化了会议纪要等场景的工作流程。
- **[ATH-MaaS/OvisOCR2](https://huggingface.co/ATH-MaaS/OvisOCR2)** | 作者: ATH-MaaS | 👍 153 | ⬇️ 10,795
  - 基于Qwen3.5的专用OCR模型，在学术文档、票据等场景下精度出色。

##### 📦 **微调与量化（社区微调、GGUF、AWQ）**

- **[empero-ai/Qwythos-9B-v2-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-v2-GGUF)** | 作者: empero-ai | 👍 162 | ⬇️ 98,370
  - Qwythos-9B的第二代量化版，持续优化了推理效率与生成质量。
- **[AngelSlim/Hy3-GGUF](https://huggingface.co/AngelSlim/Hy3-GGUF)** | 作者: AngelSlim | 👍 122 | ⬇️ 84,834
  - 腾讯Hy3模型的社区GGUF量化版，使这个大型模型能在更多设备上运行。
- **[prism-ml/Bonsai-27B-mlx-1bit](https://huggingface.co/prism-ml/Bonsai-27B-mlx-1bit)** | 作者: prism-ml | 👍 117 | ⬇️ 17,127
  - Bonsai-27B的Apple Silicon (MLX) 专属1-bit优化版，完美适配Mac用户。
- **[unsloth/Qwen3.6-27B-NVFP4](https://huggingface.co/unsloth/Qwen3.6-27B-NVFP4)** | 作者: unsloth | 👍 225 | ⬇️ 1,924,495
  - 著名微调工具Unsloth推出的4-bit浮点量化版，以极小的精度损失换取极高的推理速度，下载量巨大。
- **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** | 作者: froggeric | 👍 934 | ⬇️ 0
  - 修复了Qwen系列聊天模板Bug的“隐形”基础设施模型，虽无下载量，但高点赞数说明其解决了一个长期困扰开发者的痛点。
- **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)** | 作者: jlnsrk | 👍 127 | ⬇️ 3,447
  - 针对GLM-5.2的CPU友好型量化版本，采用Colibri技术实现高效的专家流式推理，拓展了大型MoE的部署场景。

#### **生态信号**

1.  **模型家族势头正旺**：**Qwen 3.6** 已成为社区微调和量化的“基础设施”模型，围绕其展开的衍生模型（如 `HauhauCS` 的无审查版、`unsloth` 的量化版）占据热度榜半壁江山。**GLM-5.2** 和 **Bonsai** 系列则分别代表了中国力量与极致量化两条主线。
2.  **开源vs闭源**：本周榜单完全是**开源模型的天下**。从大型厂商（腾讯、百度、智谱）到个人开发者（HauhauCS），开源生态展现出极强的活力。`empero-ai` 的Qwythos系列 (整合了闭源Claude的风格) 和 `GnLOLot` 的小模型蒸馏实验，标志着“开源模型 + 闭源风格/能力”的混合创新模式正在流行。
3.  **量化与微调活动**：**极低比特量化（1-bit, 2-bit, Ternary）** 成为本周最热门的技术主题，`prism-ml` 主导了这场革命。**GGUF** 格式依然是生态的绝对主流，但面向Mac用户的 **MLX** 格式（`prism-ml`, `froggeric`）和面向NVIDIA新硬件的 **NVFP4** （`unsloth`） 格式正快速崛起。微调活动则以 **“能力蒸馏”** （将大模型能力压缩至小模型）和 **“无审查化”** 为主要驱动力。

#### **值得探索**

1.  **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**：作为本周点赞最高的模型，其MoE架构设计、推理效率和在中文领域的表现，是所有关注大模型基础架构的研究者和企业必须研究的对象。
2.  **[Cactus-Compute/needle](https://huggingface.co/Cactus-Compute/needle)**：AI Agent是当前最热的应用方向，`needle` 模型专为此而生。探索其JAX实现、函数调用逻辑，对于开发高效、轻量的智能体应用极具价值。
3.  **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)**：该模型展示了如何在CPU上运行大型MoE模型。对于预算有限或需要服务器端大规模低功耗部署的场景，这项技术与“专家流式”推理方案值得深入研究，可能成为LLM普惠化的关键拼图。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*