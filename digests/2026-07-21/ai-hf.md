# Hugging Face 热门模型日报 2026-07-21

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-21 03:15 UTC

---

好的，作为AI模型生态分析师，这是为您生成的2026年7月21日《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-21**

#### **今日速览**

本周Hugging Face社区的核心主题是“极致效率”与“多模态融合”。以 `prism-ml` 为代表的团队成功将极低比特量化（1-bit、2-bit甚至三值化）的27B大模型推向主流，下载量惊人，标志着边缘端部署进入新阶段。同时，多模态模型全面爆发，以Google `Gemma-4`、`Qwen3.6` 和 `MiniCPM5` 系列为基础的各种变体（尤其是图像、视频理解与生成模型）占据了榜单多数席位。另外，以百度 `Unlimited-OCR` 为代表的专用模型和以 `MiniCPM-RobotManip` 为代表的机器人基础模型也表现出强劲势头，AI应用正从通用对话向垂直场景深度渗透。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)** | prism-ml | 点赞: 857 | 下载: 338,945
  - *一句话说明*：27B参数的三值化（Ternary，2-bit）模型，将推理效率和模型容量平衡推向新高度，下载量巨大。
- **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)** | prism-ml | 点赞: 543 | 下载: 1,262,894
  - *一句话说明*：Bonsai-27B的1-bit极致量化版本，以极低资源占用实现了惊人的下载量，是边缘设备运行的里程碑。
- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | zai-org | 点赞: 4,229 | 下载: 531,947
  - *一句话说明*：基于MoE架构的下一代GLM模型，以顶尖的点赞数证明了其在学术和通用对话领域的强劲实力。
- **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** | tencent | 点赞: 849 | 下载: 13,698
  - *一句话说明*：腾讯推出的新一代Hy（混元）系列语言模型，稳居主流大模型行列。
- **[moonshotai/Kimi-K2.7-Code](https://huggingface.co/moonshotai/Kimi-K2.7-Code)** | moonshotai | 点赞: 1,178 | 下载: 713,992
  - *一句话说明*：Kimi K2.7的代码专用压缩版，在保持强大编程能力的同时大幅减小体积，下载量极高。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[google/gemma-4-31B-it](https://huggingface.co/google/gemma-4-31B-it)** | google | 点赞: 3,298 | 下载: 11,987,240
  - *一句话说明*：Google最新发布的31B多模态指令模型，凭借原生多模态理解能力和顶级性能，成为本周下载量冠军。
- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | baidu | 点赞: 2,454 | 下载: 2,122,848
  - *一句话说明*：百度推出的无限制OCR模型，在文档理解和图像文字提取任务上表现惊艳，是下游应用的热门选择。
- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | empero-ai | 点赞: 2,371 | 下载: 2,117,323
  - *一句话说明*：基于Qwen3.5的9B多模态量化版，融合了Mythos数据集的推理能力，以高性价比吸引大量下载。
- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | HauhauCS | 点赞: 2,937 | 下载: 2,007,025
  - *一句话说明*：Qwen3.6的35B MoE视觉模型的“激进”无审查版，在特定社区中极受欢迎。
- **[Wan-AI/Wan-Dancer-14B](https://huggingface.co/Wan-AI/Wan-Dancer-14B)** | Wan-AI | 点赞: 145 | 下载: 2,408
  - *一句话说明*：Wan-AI推出的14B图像驱动视频生成模型，专注于舞蹈动作生成，在多模态生成领域独树一帜。
- **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)** | OpenMOSS-Team | 点赞: 293 | 下载: 87,533
  - *一句话说明*：MOSS团队的音频转文字+说话人识别一体化模型，为语音分析提供了强大工具。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[openbmb/MiniCPM-RobotManip](https://huggingface.co/openbmb/MiniCPM-RobotManip)** | openbmb | 点赞: 135 | 下载: 0
  - *一句话说明*：MiniCPM家族推出的机器人操作（VLA，视觉-语言-动作）模型，预示了端到端机器人基础模型的到来。
- **[nvidia/Nemotron-3-Embed-1B-BF16](https://huggingface.co/nvidia/Nemotron-3-Embed-1B-BF16)** | nvidia | 点赞: 87 | 下载: 61,708
  - *一句话说明*：NVIDIA推出的第三代1B嵌入模型，是构建高质量RAG系统的首选底座之一。
- **[Cactus-Compute/needle](https://huggingface.co/Cactus-Compute/needle)** | Cactus-Compute | 点赞: 292 | 下载: 950
  - *一句话说明*：基于JAX实现的函数调用/工具使用模型，为智能体开发提供了新的技术路线。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[prism-ml/Bonsai-27B-mlx-1bit](https://huggingface.co/prism-ml/Bonsai-27B-mlx-1bit)** | prism-ml | 点赞: 155 | 下载: 21,690
  - *一句话说明*：Bonsai-27B的1-bit MLX版，专为Apple Silicon优化，是Mac用户的福音。
- **[AngelSlim/Hy3-GGUF](https://huggingface.co/AngelSlim/Hy3-GGUF)** | AngelSlim | 点赞: 149 | 下载: 109,749
  - *一句话说明*：腾讯 Hy3 模型的社区GGUF量化版，降低了运行门槛，下载量迅速攀升。
- **[GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking](https://huggingface.co/GnLOLot/MiniCPM5-1B-Claude-Opus-Fable5-Thinking)** | GnLOLot | 点赞: 159 | 下载: 5,494
  - *一句话说明*：在MiniCPM5-1B上微调的思维链模型，证明了小参数模型也能具备强大推理能力。

#### **生态信号**

1.  **“三值化”与“1-bit”浪潮**：`prism-ml` 的Bonsai系列是本周最亮的技术信号。它不仅证明了超过200亿参数的模型可以压缩到1-bit甚至三值化，更通过`GGUF`和`MLX`双格式，实现了从NVIDIA到Apple全平台的普及。这意味着，个人电脑和手机运行顶级大模型的时代已经到来。

2.  **Qwen与MiniCPM家族生态繁荣**：基于阿里 `Qwen3.6` 和OpenBMB `MiniCPM5` 的社区微调与量化模型层出不穷（如 `Qwythos`、`HauhauCS`、`ThinkingCap`），形成强大的生态效应。开发者正围绕这些优质基座模型，疯狂产出角色扮演、无审查、专业推理等垂直变体，反映了社区对“可定制基座”的高度渴求。

3.  **开源权重持续引领，闭源模型加速分化**：Google `Gemma-4` 和 `Nvidia Nemotron` 等顶级实验室的开源权重模型在榜单上占据了绝对头部，其下载量远超社区微调模型，证明“高质量开源”仍是吸引流量的不二法门。而 `Kimi-K2.7-Code` 和 `GLM-5.2` 则代表了另一种趋势：通过发布压缩或特定领域的强模型来增强品牌影响力，形成了开源模型间的差异化竞争。

#### **值得探索**

1.  **`google/gemma-4-31B-it`**：本周最值得研究的模型。作为Google最新的多模态旗舰，它在自然图像理解、文档问答等任务上树立了新标杆。下载量破千万意味着它很可能是下一代应用的首选底座，值得深入研究其技术报告和推理模式。

2.  **`openbmb/MiniCPM-RobotManip`**：这个模型的下载量为0，并不意味着它不火，恰恰相反，它可能代表了AI的下一个前沿。作为机器人基础模型，它将视觉、语言和动作空间直接对齐。对于研究具身智能的团队来说，这是不可多得的开源基座。

3.  **`prism-ml/Bonsai-27B-gguf`**：如果你想在自己的设备上运行一个大模型，或者对低比特量化技术感兴趣，这个模型是绝佳的研究对象。它展示了“1-bit”模型在多大程度上能保持原始模型的能力，是理解模型压缩极限的样本。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*