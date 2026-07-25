# Hugging Face 热门模型日报 2026-07-25

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-25 15:45 UTC

---

好的，作为AI模型生态分析师，以下是为您整理的2026年7月25日《Hugging Face 热门模型日报》。

---

### 📰 Hugging Face 热门模型日报 (2026-07-25)

#### 1. 今日速览

本周 Hugging Face 生态呈现出几个显著趋势：**小体积（<4B）与极端量化（1-bit/2-bit）模型**因显著降低部署成本而备受追捧；**Qwen3.6** 系列成为社区微调与量化的绝对“底模”之王，催生了海量的衍生模型；同时，**多模态（尤其是文本到图像、图像到文本）** 模型占据主流，从通用大模型到专用OCR、机器人控制均有突破。此外，百度的 `Unlimited-OCR` 以极高点赞数成为黑马，展示了特定场景任务的强大吸引力。

#### 2. 热门模型

##### 🧠 语言模型（LLM、对话模型、指令微调）

-   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** (zai-org, 点赞: 4,436, 下载: 707,029)
    -   本周点赞数最高的模型，采用 MoE-DSA 架构的 GLM 第五代模型，在对话和生成任务上表现出色。
-   **[poolside/Laguna-S-2.1](https://huggingface.co/poolside/Laguna-S-2.1)** (poolside, 点赞: 646, 下载: 45,260)
    -   poolside 发布的高性能文本生成模型，属于 `Laguna` 系列，拥有多个量化版本（GGUF, NVFP4）广泛传播。
-   **[upstage/Solar-Open2-250B](https://huggingface.co/upstage/Solar-Open2-250B)** (upstage, 点赞: 555, 下载: 2,784)
    -   Upstage 推出的 250B 参数级别大型语言模型，代表了当前开源大模型在规模与性能上的前沿探索。
-   **[Nanbeige/Nanbeige4.2-3B](https://huggingface.co/Nanbeige/Nanbeige4.2-3B)** (Nanbeige, 点赞: 388, 下载: 11,573)
    -   仅 3B 参数的小模型，凭借其优秀的性能和高效的推理能力在社区中获得了关注，适合资源受限场景。
-   **[fdtn-ai/antares-1b](https://huggingface.co/fdtn-ai/antares-1b)** (fdtn-ai, 点赞: 153, 下载: 5,661)
    -   1B 参数的安全领域专用大模型，基于 GraniteMoEHybrid 架构，针对安全性进行了专项优化。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

-   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** (baidu, 点赞: 3,065, 下载: 2,564,264)
    -   百度出品的全能 OCR 模型，支持图像到文本转换，凭借其强大的识别能力成为本周最热门的模型之一。
-   **[google/gemma-4-31B-it](https://huggingface.co/google/gemma-4-31B-it)** (google, 点赞: 3,367, 下载: 12,511,030)
    -   Google 的 Gemma 4 大语言模型，拥有高达 1250 万的下载量，展示了其作为基础模型的广泛影响力。
-   **[Qwen/Qwen3.6-35B-A3B](https://huggingface.co/Qwen/Qwen3.6-35B-A3B)** (Qwen, 点赞: 2,511, 下载: 6,413,105)
    -   Qwen 3.6 旗舰多模态模型，采用 MoE 架构，是当前社区大量衍生模型的“母版”，其视觉理解能力非常强劲。
-   **[thinkingmachines/Inkling](https://huggingface.co/thinkingmachines/Inkling)** (thinkingmachines, 点赞: 1,560, 下载: 31,575)
    -   thinkingmachines 开发的多模态对话模型，主打流畅的视觉与文本互动体验。
-   **[microsoft/Mage-Flow](https://huggingface.co/microsoft/Mage-Flow)** (microsoft, 点赞: 260, 下载: 1,156)
    -   微软推出的文本到图像生成模型，同时具备图像编辑能力，丰富了微软的图像生成生态。
-   **[nvidia/Cosmos3-Edge](https://huggingface.co/nvidia/Cosmos3-Edge)** (nvidia, 点赞: 114, 下载: 31,759)
    -   英伟达 Cosmos 系列的新成员，专注于边缘计算的视觉模型，展示了行业巨头对边缘 AI 的投入。
-   **[baseten/GLM-5.2-Vision-NVFP4](https://huggingface.co/baseten/GLM-5.2-Vision-NVFP4)** (baseten, 点赞: 96, 下载: 1,977)
    -   GLM-5.2 的视觉增强版本，并经过 NVFP4 量化，兼顾了多模态能力与推理效率。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

-   **[moonshotai/Kimi-K2.7-Code](https://huggingface.co/moonshotai/Kimi-K2.7-Code)** (moonshotai, 点赞: 1,271, 下载: 749,449)
    -   月之暗面推出的代码专用模型，基于 Kimi 系列，下载量巨大，表明其在代码生成领域有很强的需求。
-   **[openbmb/MiniCPM-RobotManip](https://huggingface.co/openbmb/MiniCPM-RobotManip)** (openbmb, 点赞: 174, 下载: 607)
    -   面壁智能 (OpenBMB) 发布的机器人操作 (Robot Manipulation) 专用视觉-语言-动作 (VLA) 模型，是机器人领域的突破性开源产品。
-   **[openbmb/MiniCPM-RobotTrack](https://huggingface.co/openbmb/MiniCPM-RobotTrack)** (openbmb, 点赞: 126, 下载: 379)
    -   面壁智能的另一款机器人模型，专注于目标跟踪，与 RobotManip 形成机器人套件。
-   **[Kwaipilot/KAT-Coder-V2.5-Dev](https://huggingface.co/Kwaipilot/KAT-Coder-V2.5-Dev)** (Kwaipilot, 点赞: 151, 下载: 841)
    -   基于 Qwen3.5 MoE 架构的代码生成模型，专注于提升编码能力。
-   **[ATH-MaaS/OvisOCR2](https://huggingface.co/ATH-MaaS/OvisOCR2)** (ATH-MaaS, 点赞: 283, 下载: 33,109)
    -   基于 Qwen3.5 的 OCR 专用模型，与百度的 Unlimited-OCR 并列，说明OCR需求正在爆发。
-   **[microsoft/Fara1.5-27B](https://huggingface.co/microsoft/Fara1.5-27B)** (microsoft, 点赞: 81, 下载: 1,039)
    -   微软推出的“Computer Use”模型，专为自动化计算机界面操作而设计，这是一个非常前沿的应用方向。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

-   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** (HauhauCS, 点赞: 3,084, 下载: 1,988,680)
    -   基于 Qwen3.6 的“激进”解禁版，去除了内容限制，深受特定社区欢迎，下载量极高。
-   **[DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF)** (DavidAU, 点赞: 519, 下载: 483,845)
    -   Qwen3.6 的另一个大型社区变异版本，同样主打“Uncensored”并进行了GGUF量化，体现了社区旺盛的改造热情。
-   **[prism-ml/Ternary-Bonsai-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-27B-gguf)** (prism-ml, 点赞: 1,020, 下载: 611,685)
    -   极致的 **2-bit** 量化模型，将 27B 模型压缩到极致，在下载和点赞上都取得了成功，证明了极端量化的市场价值。
-   **[prism-ml/Bonsai-27B-gguf](https://huggingface.co/prism-ml/Bonsai-27B-gguf)** (prism-ml, 点赞: 636, 下载: 2,114,963)
    -   另一款 **1-bit** 量化模型，下载量超过 210 万，说明“让大模型在消费级硬件上跑起来”是社区的核心诉求。
-   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** (empero-ai, 点赞: 2,459, 下载: 1,570,995)
    -   基于 Qwen3.5 的量化版本，在社区非常火爆，下载量超百万，凸显了推理优化的必要性。
-   **[bottlecapai/ThinkingCap-Qwen3.6-27B](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)** (bottlecapai, 点赞: 548, 下载: 27,064)
    -   基于 Qwen3.6 的微调模型，强调了“思考能力”的增强。
-   **[LuffyTheFox/Qwen3.6-35B-A3B-Uncensored-Genesis-Hermes-V5-GGUF](https://huggingface.co/LuffyTheFox/Qwen3.6-35B-A3B-Uncensored-Genesis-Hermes-V5-GGUF)** (LuffyTheFox, 点赞: 145, 下载: 60,643)
    -   另一个以 Qwen3.6 为基础的 Uncensored 微调版本，融合了 Hermes 风格，进一步体现了模型微调的“百家争鸣”。

#### 3. 生态信号

-   **Qwen 与 GLM 家族势头正旺**：Qwen3.6 系列无疑是本周的“地表最强底模”，其 MoE 架构和强大的多模态能力催生了大量社区微调版本。GLM-5.2 则凭借创新架构和高原生点赞数，成为另一个核心玩家。
-   **量化（GGUF）是刚需，极端量化成新热点**：几乎所有热门模型都会跟进 GGUF 格式。更值得注意的是，`prism-ml` 的 1-bit 和 2-bit 模型获得了惊人的下载量，这表明社区对于在普通个人电脑上运行大模型有着强烈的渴望，模型压缩技术正从实验走向主流。
-   **“Uncensored”模型生态蓬勃发展**：围绕 Qwen3.6 的“解禁版”形成了一个庞大且活跃的微调生态，成为社区文化和技术实践的一大特色。这反映了用户对模型自由度和特定内容生成的双重需求。
-   **机器人模型崭露头角**：`MiniCPM-RobotManip` 和 `MiniCPM-RobotTrack` 的上榜是一个重要信号，表明 AI 正从纯粹的数字世界向物理世界（机器人控制）加速渗透。

#### 4. 值得探索

1.  **`google/gemma-4-31B-it`**：作为 Google 的官方发布，其 1250 万的下载量背后是强大的性能和广泛的基础应用场景。研究其与社区热门 Qwen3.6 在架构和效果上的差异，极具价值。
2.  **`zai-org/GLM-5.2`**：本周点赞王。其 MoE-DSA 架构可能带来了不同于传统 MoE 的效率提升，值得深入探究其推理机制和性能表现。
3.  **`prism-ml/Bonsai-27B-gguf`** (1-bit): 作为极端量化的代表，探索 1-bit 模型的能力边界。它能否在保持一定智能水平的同时，实现“一台手机跑 27B 模型”的构想？这对边缘计算和隐私保护有深远意义。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*