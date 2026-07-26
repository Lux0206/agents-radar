# Hugging Face 热门模型日报 2026-07-26

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-26 03:25 UTC

---

好的，以下是 2026 年 7 月 26 日的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-26**

#### **今日速览**

本周 Hugging Face 平台主要由 **Qwen3.6 系列** 的社区微调与量化版支配，同时 **GLM-5.2** 凭借其 MoE 架构和顶尖点赞量成为最大亮点。**OCR 模型** 赛道竞争激烈，百度与 ATH-MaaS 均有重磅发布。值得注意的是，**“uncensored”** 主题的社区模型持续火热，而 **机器人操控模型**（如 MiniCPM-RobotManip）作为新兴类别开始崭露头角，标志着 AI 从数字世界向物理世界的渗透。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **zai-org/GLM-5.2**
   作者: zai-org | 点赞: 4,448 | 下载: 707,029
   [链接](https://huggingface.co/zai-org/GLM-5.2)
   **说明**: 本周绝对热门，基于 MoE 架构的通用对话模型，性能与效率平衡出色，吸引大量关注与使用。

- **Qwen/Qwen3.6-35B-A3B**
   作者: Qwen | 点赞: 2,516 | 下载: 6,413,105
   [链接](https://huggingface.co/Qwen/Qwen3.6-35B-A3B)
   **说明**: Qwen 官方推出的 MoE 视觉语言模型，总参 35B，激活仅 3B，极高效率与巨大下载量表明其作为社区微调基座的强大生态。

- **upstage/Solar-Open2-250B**
   作者: upstage | 点赞: 567 | 下载: 2,784
   [链接](https://huggingface.co/upstage/Solar-Open2-250B)
   **说明**: Upstage 开源的 250B 级大模型，是开源社区在超大参数规模竞争中的重要参与者和技术展示。

- **Nanbeige/Nanbeige4.2-3B**
   作者: Nanbeige | 点赞: 406 | 下载: 11,573
   [链接](https://huggingface.co/Nanbeige/Nanbeige4.2-3B)
   **说明**: 轻量级语言模型（3B），在边缘部署或特定任务场景下具有较高实用价值。

- **fdtn-ai/antares-1b**
   作者: fdtn-ai | 点赞: 166 | 下载: 5,661
   [链接](https://huggingface.co/fdtn-ai/antares-1b)
   **说明**: 专注于安全领域的 1B 模型，使用 GraniteMoEHybrid 架构，填补了特定垂直领域的小模型空白。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **baidu/Unlimited-OCR**
   作者: baidu | 点赞: 3,108 | 下载: 2,564,264
   [链接](https://huggingface.co/baidu/Unlimited-OCR)
   **说明**: 百度出品的高精度 OCR 模型，支持图像转文本任务，海量下载量体现了其在文档处理领域的广泛应用。

- **thinkingmachines/Inkling**
   作者: thinkingmachines | 点赞: 1,572 | 下载: 31,575
   [链接](https://huggingface.co/thinkingmachines/Inkling)
   **说明**: 一款新型多模态对话模型，标签包含 “conversational”，可能具备更自然的图文交互能力。

- **microsoft/Mage-Flow**
   作者: microsoft | 点赞: 277 | 下载: 1,156
   [链接](https://huggingface.co/microsoft/Mage-Flow)
   **说明**: 微软发布的图像生成与编辑模型，基于扩散框架，代表了其在视觉生成领域的最新探索。

- **ATH-MaaS/OvisOCR2**
   作者: ATH-MaaS | 点赞: 287 | 下载: 33,109
   [链接](https://huggingface.co/ATH-MaaS/OvisOCR2)
   **说明**: 基于 Qwen3.5 的第二代 OCR 视觉模型，与百度形成对标，显示 OCR 赛道竞争白热化。

- **moonshotai/Kimi-K2.7-Code**
   作者: moonshotai | 点赞: 1,277 | 下载: 749,449
   [链接](https://huggingface.co/moonshotai/Kimi-K2.7-Code)
   **说明**: Moonshot（月之暗面）推出的代码专用模型，基于 “压缩张量”（compressed-tensors）技术，可能是Kimi系列在代码领域的精调版本。

- **owensong/Inflect-Micro-v2**
   作者: owensong | 点赞: 88 | 下载: 47
   [链接](https://huggingface.co/owensong/Inflect-Micro-v2)
   **说明**: 轻量级语音合成模型，定位边缘AI和CPU推理，是本地化、离线TTS的实用选择。

- **nvidia/Cosmos3-Edge**
   作者: nvidia | 点赞: 121 | 下载: 31,759
   [链接](https://huggingface.co/nvidia/Cosmos3-Edge)
   **说明**: NVIDIA 的 Cosmos 系列边缘端模型，关注物理世界感知与生成，可能用于机器人或自动驾驶场景。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **Kwaipilot/KAT-Coder-V2.5-Dev**
   作者: Kwaipilot | 点赞: 168 | 下载: 841
   [链接](https://huggingface.co/Kwaipilot/KAT-Coder-V2.5-Dev)
   **说明**: 基于 Qwen3.5 MoE 架构的开发版代码模型，专注于代码生成和理解。

- **openbmb/MiniCPM-RobotManip**
   作者: openbmb | 点赞: 175 | 下载: 607
   [链接](https://huggingface.co/openbmb/MiniCPM-RobotManip)
   **说明**: OpenBMB 推出的 VLA（视觉-语言-动作）模型，用于机器人操控任务，代表AI向物理世界延展的重要方向。

- **openbmb/MiniCPM-RobotTrack**
   作者: openbmb | 点赞: 128 | 下载: 379
   [链接](https://huggingface.co/openbmb/MiniCPM-RobotTrack)
   **说明**: 机器人轨迹跟踪模型，与 RobotManip 呼应，展现了 MiniCPM 在机器人领域的系统性布局。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive**
   作者: HauhauCS | 点赞: 3,093 | 下载: 1,988,680
   [链接](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)
   **说明**: Qwen3.6 的知名 “uncensored” 社区微调版，下载量巨大，反映了社区对模型输出自由度的高度需求。

- **DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF**
   作者: DavidAU | 点赞: 548 | 下载: 483,845
   [链接](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF)
   **说明**: 另一款极受追捧的 Deep Fine-Tune + GGUF 格式 “uncensored” 模型，名称即体现了内容的猎奇与定制化取向。

- **prism-ml/Ternary-Bonsai-27B-gguf**
   作者: prism-ml | 点赞: 1,029 | 下载: 611,685
   [链接](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)
   **说明**: 采用 2-bit 三元量化的 27B 模型 GGUF 版，是极致量化压缩的代表，适合在资源受限设备上运行。

- **prism-ml/Bonsai-27B-gguf**
   作者: prism-ml | 点赞: 638 | 下载: 2,114,963
   [链接](https://huggingface.co/prism-ml/Bonsai-27B-gguf)
   **说明**: Bonsai 系列的 1-bit 极限量化版，下载量极高，显示了社区对在消费级硬件上运行大模型的强烈渴望。

- **empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF**
   作者: empero-ai | 点赞: 2,466 | 下载: 1,570,995
   [链接](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)
   **说明**: 基于 Qwen3.5 的 9B 模型 GGUF 版，以 “reasoning”（推理）为核心卖点，量化后仍保持强推理能力，实用性极强。

- **bottlecapai/ThinkingCap-Qwen3.6-27B**
   作者: bottlecapai | 点赞: 551 | 下载: 27,064
   [链接](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)
   **说明**: Qwen3.6 的 “思考帽” 微调版，强调模型在回答前进行深度思考，提升输出质量。

- **conradlocke/krea2-identity-edit**
   作者: conradlocke | 点赞: 539 | 下载: 0
   [链接](https://huggingface.co/conradlocke/krea2-identity-edit)
   **说明**: 针对 Krea-2 模型的 LoRA 微调，专注于身份保持的图像编辑，刚发布不久，点赞数据表明了市场对此功能的期待。

#### **生态信号**

**1. Qwen 生态的绝对统治力：** Qwen3.6 系列，特别是 **35B-A3B** 的 MoE 版本，已成为社区微调和量化的绝对主流基座。其高效率和优秀性能催生了大量 “uncensored” 变体和 GGUF 量化版，生态极其繁荣。

**2. “Uncensored” 与量化双轮驱动：** 社区活动高度集中在两个方向：一是追求输出自由的 **“uncensored”** 微调；二是追求在消费级硬件上部署的 **GGUF 量化**。这两类模型往往拥有最高的下载量和活跃的点赞数，是社区驱动的核心动力。

**3. 开源大模型进入多模态与专业性深水区：** 除了通用语言模型，本周 **OCR**（百度、ATH-MaaS）、**机器人**（OpenBMB）、**代码**（Moonshot）、**图像编辑**（Microsoft、LoRA）等专用模型频发，显示开源社区正从“能用”向“好用、专用”方向发展。微软和 NVIDIA 的加入也表明了大厂在开源生态中的角色日益重要。

#### **值得探索**

1.  **zai-org/GLM-5.2** ([链接](https://huggingface.co/zai-org/GLM-5.2))：作为本周点赞量冠军，代表当下 MoE 架构模型的最优水平之一，是研究高效大语言模型的首选。
2.  **openbmb/MiniCPM-RobotManip** ([链接](https://huggingface.co/openbmb/MiniCPM-RobotManip))：为数不多的开源机器人 VLA 模型，是关注具身智能和机器人领域的入门与实践极佳选择。
3.  **prism-ml/Ternary-Bonsai-27B-gguf** ([链接](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf))：探索模型压缩和量化极限的前沿代表，对于研究模型效率、边缘部署和极低比特量化的研究者具有很高的参考价值。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*