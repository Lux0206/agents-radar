# Hugging Face 热门模型日报 2026-07-24

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-24 03:14 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的2026年7月24日数据生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026年7月24日**

#### **今日速览**

- **多模态模型占据主导地位**：本周热门榜上，`image-text-to-text` 模型数量与纯文本模型持平，且包揽了榜单前三名中的两席，表明多模态能力已成为模型竞争的核心。
- **Qwen家族生态繁荣**：围绕Qwen3.5/3.6的社区微调和量化版模型（如`HauhauCS`、`LuffyTheFox`）数量激增，下载量巨大，显示了其作为基础模型的强大韧性和社区拥趸。
- **GLM-5.2 以黑马姿态登顶**：智谱AI的最新开源模型 `zai-org/GLM-5.2` 以超过4300的周点赞数力压Google、百度等巨头，成为本周最受关注的模型。
- **极低比特量化成为主流趋势**：以 `prism-ml` 为代表，1-bit和2-bit量化模型（如 `Bonsai-27B-gguf`）下载量突破百万，标志着在消费级硬件上运行大模型的极致优化成为现实。

---

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**  
  作者: zai-org | 点赞: 4,375 | 下载: 596,442  
   **说明**: 智谱AI的最新MoE架构开源模型，凭借强大的性能和有竞争力的开源协议，本周热度断层领先，成为社区新宠。

- **[upstage/Solar-Open2-250B](https://huggingface.co/upstage/Solar-Open2-250B)**  
  作者: upstage | 点赞: 467 | 下载: 362  
   **说明**: Upstage推出的250B参数级超大开源模型，定位高性能对话和生成，代表了开源模型在规模上的又一次突破。

- **[Nanbeige/Nanbeige4.2-3B](https://huggingface.co/Nanbeige/Nanbeige4.2-3B)**  
  作者: Nanbeige | 点赞: 326 | 下载: 4,532  
   **说明**: 3B参数的小型高效LLM，专注于在低资源场景下提供流畅的文本生成能力，适合边缘部署。

- **[poolside/Laguna-S-2.1](https://huggingface.co/poolside/Laguna-S-2.1)**  
  作者: poolside | 点赞: 519 | 下载: 13,285  
   **说明**: poolside公司专为软件工程优化的代码生成模型，本周正式发布，标志着垂直领域模型的重要性日益凸显。

- **[Motif-Technologies/Motif-3-Beta](https://huggingface.co/Motif-Technologies/Motif-3-Beta)**  
  作者: Motif-Technologies | 点赞: 174 | 下载: 1,856  
   **说明**: Motif推出的第三代文本生成模型Beta版，专注于特征提取和对话，是新兴力量的代表。

- **[fdtn-ai/antares-1b](https://huggingface.co/fdtn-ai/antares-1b)**  
  作者: fdtn-ai | 点赞: 121 | 下载: 2,747  
   **说明**: 专注于安全领域的1B参数小型LLM，反映了AI安全与可信赖正成为模型设计的重要维度。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[google/gemma-4-31B-it](https://huggingface.co/google/gemma-4-31B-it)**  
  作者: google | 点赞: 3,347 | 下载: 12,666,488  
   **说明**: Google Gemma 4系列的旗舰聊天模型，拥有惊人的下载量，证明其作为强大全能多模态模型的市场领先地位。

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**  
  作者: HauhauCS | 点赞: 3,036 | 下载: 2,027,080  
   **说明**: 基于Qwen3.6的35B-MoE（激活3B）去审查版，社区对其"激进"风格和高效推理的追捧使其下载量极高。

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**  
  作者: baidu | 点赞: 2,900 | 下载: 2,414,259  
   **说明**: 百度推出的通用OCR多模态模型，在文字识别任务上表现出色，满足了海量的文档处理需求。

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**  
  作者: empero-ai | 点赞: 2,440 | 下载: 2,126,755  
   **说明**: 基于Qwen3.5的推理强化模型，结合了Claude风格的微调与GGUF量化，是社区高质量微调模型的典范。

- **[Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice)**  
  作者: Qwen | 点赞: 1,800 | 下载: 2,497,020  
   **说明**: 阿里Qwen团队的开源TTS模型，支持定制音色和12Hz高频音频生成，推动了语音合成技术的开源民主化。

- **[microsoft/Mage-Flow](https://huggingface.co/microsoft/Mage-Flow)**  
  作者: microsoft | 点赞: 189 | 下载: 411  
   **说明**: 微软推出的文本到图像生成模型，强调图像编辑和生成流程的流畅性，代表了传统的文本到图像领域仍在持续演进。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[moonshotai/Kimi-K2.7-Code](https://huggingface.co/moonshotai/Kimi-K2.7-Code)**  
  作者: moonshotai | 点赞: 1,249 | 下载: 766,522  
   **说明**: 月之暗面为代码任务优化的专用模型，使用了压缩的张量技术，在编码效率和性能间取得了平衡。

- **[nvidia/nemotron-3.5-asr-streaming-0.6b](https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b)**  
  作者: nvidia | 点赞: 926 | 下载: 750,118  
   **说明**: NVIDIA推出的流式语音识别小模型，专为实时音频转写场景设计，体现了音频+文本任务的细分。

- **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)**  
  作者: OpenMOSS-Team | 点赞: 320 | 下载: 111,598  
   **说明**: MOSS团队开发的音频转写+说话人分离模型，将音频理解能力复合化，从“听”到“知道谁在说”。

- **[openbmb/MiniCPM-RobotManip](https://huggingface.co/openbmb/MiniCPM-RobotManip)**  
  作者: openbmb | 点赞: 165 | 下载: 408  
   **说明**: MiniCPM系列的机器人操作模型（VLA），将语言-视觉-动作能力结合，是AI走入物理世界的重要一步。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[thinkingmachines/Inkling](https://huggingface.co/thinkingmachines/Inkling)**  
  作者: thinkingmachines | 点赞: 1,509 | 下载: 24,669  
   **说明**: 一款社区微调的图像到文本对话模型，拥有极高的点赞-下载比，表明其微调质量受到高度认可。

- **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)**  
  作者: prism-ml | 点赞: 620 | 下载: 1,910,116  
   **说明**: 1-bit量化的27B模型，下载量近200万，是极低比特量化技术实用性的最佳证明，让大模型在普通电脑上运行成为可能。

- **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)**  
  作者: prism-ml | 点赞: 986 | 下载: 576,083  
   **说明**: prism-ml推出的“三进制”2-bit量化版本的Bonsai-27B，在模型大小和质量之间提供了新的平衡点。

- **[DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF)**  
  作者: DavidAU | 点赞: 407 | 下载: 334,847  
   **说明**: 典型的社区狂热微调产物，融合了“去审查”、“NEOMAX”等多重标签，体现了社区对模型个性化和极致的追求。

- **[bottlecapai/ThinkingCap-Qwen3.6-27B](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)**  
  作者: bottlecapai | 点赞: 529 | 下载: 25,231  
   **说明**: 对Qwen3.6-27B的思维链能力增强微调，旨在提升模型推理精度，代表了社区微调的重要方向。

---

#### **生态信号**

- **模型家族竞赛：GLM vs. Qwen vs. Gemma**: 本周表现最强劲的三个模型家族分别是智谱的`GLM-5.2`（创新高）、阿里的`Qwen3.6`（生态最繁荣）和谷歌的`Gemma-4`（市场接受度最高）。这三大阵营的开源策略差异，正在深刻塑造2026年下半年的AI格局。
- **开源权重模型持续领先**：榜单前10名全部为开源权重模型。`GLM-5.2`和`Gemma-4`的火爆表明，社区对开放、可研究、可定制的模型有强烈偏好，闭源API模型在这一领域的热度正被快速追赶。
- **“量化即正义”**：GGUF格式在榜上占比极高，且出现了大量的1-bit、2-bit乃至“三进制”量化尝试。**“Bonsai”** 系列的成功证明，通过极致的量化在消费级硬件上运行高性能模型，已成为与增大模型参数并行的另一条主流技术路线。

---

#### **值得探索**

1. **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**: 本周绝对王者。无论是从学术研究角度探索其MoE-DSA架构，还是从工程应用角度评估其作为通用基座模型的潜力，都是本月不可错过的模型。
2. **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)**: 如果您想在本地GPU上运行一个接近70B级别的模型，但显存有限，这个2-bit模型是理论上的最佳实践。它代表了模型压缩领域的前沿探索，值得所有关注端侧部署的开发者深入研究。
3. **[openbmb/MiniCPM-RobotManip](https://huggingface.co/openbmb/MiniCPM-RobotManip)**: 这不仅是模型，更是通往具身智能的钥匙。如果您关注AI与物理世界的交互，这个将视觉、语言和机器人动作指令融合的VLA模型，是最新的开源样本。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*