# Hugging Face 热门模型日报 2026-07-15

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-15 02:48 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的2026-07-15数据生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-15**

#### **今日速览**

本周 Hugging Face 趋势榜呈现两大核心特征：**基础模型的军备竞赛**与**社区量化微调的全面爆发**。**Qwen 3.5/3.6** 系列及其衍生模型生态（如 Qwythos、ThinkingCap）占据绝对主导地位，覆盖文本生成、多模态和量化等多个细分领域。同时，**GLM 5.2** 与 **DeepSeek V4** 等国内大模型的新版本也展现出强劲的社区吸引力。值得注意的是，以 **GGUF** 和 **int4** 为代表的量化模型下载量巨大，表明本地化、高效推理已成为主流需求。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

-   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** — 作者: zai-org | 点赞: 3,949 | 下载: 489,611
    -   **一句话说明**：智谱AI最新旗舰对话模型，凭借强大的多轮对话能力和MoE架构，成为本周点赞数最高的模型。
-   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** — 作者: HauhauCS | 点赞: 2,735 | 下载: 2,443,871
    -   **一句话说明**：基于Qwen 3.6的“无审查”社区微调版，以激进风格和极高下载量引爆关注，反映了社区对去抑制化模型的需求。
-   **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** — 作者: tencent | 点赞: 782 | 下载: 10,406
    -   **一句话说明**：腾讯混元大模型的最新版本，是国产大模型在开源社区的重要参与者和竞争者。
-   **[nvidia/Nemotron-Labs-Audex-30B-A3B](https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B)** — 作者: nvidia | 点赞: 149 | 下载: 1,332
    -   **一句话说明**：英伟达发布的30B参数MoE模型，专注于实验室环境下的高效推理，展示了其在高性能计算领域的布局。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

-   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** — 作者: baidu | 点赞: 1,984 | 下载: 1,715,301
    -   **一句话说明**：百度推出的通用OCR模型，凭借极高的下载量和实用性，成为本周最受欢迎的多模态工具。
-   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** — 作者: empero-ai | 点赞: 2,160 | 下载: 2,006,265
    -   **一句话说明**：结合了Qwen 3.5与Claude风格调教的多模态模型，其量化版本下载量超200万，是“调教 + 量化”模式的典型成功案例。
-   **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)** — 作者: OpenMOSS-Team | 点赞: 190 | 下载: 65,109
    -   **一句话说明**：专注于语音转录与说话人日志化的开源模型，为语音场景提供了高效解决方案。
-   **[mgwr/M87](https://huggingface.co/mgwr/M87)** — 作者: mgwr | 点赞: 109 | 下载: 2,408
    -   **一句话说明**：基于Krea-2-Turbo的LoRA微调模型，用于特定风格图像生成，展示了社区对Stable Diffusion生态的延续和创新。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

-   **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)** — 作者: yuxinlu1 | 点赞: 1,189 | 下载: 468,629
    -   **一句话说明**：基于Gemma 4的Agentic编程模型，专为终端和代码生成任务优化，展现了Agent在专业领域的潜力。
-   **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)** — 作者: InternScience | 点赞: 539 | 下载: 30,539
    -   **一句话说明**：专注于Agent任务的多模态模型，结合了Qwen 3.5 MoE架构，是当前Agent应用的主流首选方案。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

-   **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** — 作者: froggeric | 点赞: 904 | 下载: 0
    -   **一句话说明**：虽无下载量，但凭借修复Qwen系列聊天模板问题的技术价值获得近千赞，凸显了社区对模型可用性的重视。
-   **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** — 作者: deepreinforce-ai | 点赞: 881 | 下载: 1,533,354
    -   **一句话说明**：一个35B参数的LLM，其GGUF量化版本下载量巨大，是大型模型在消费级硬件上部署的典型案例。
-   **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)** — 作者: unsloth | 点赞: 1,092 | 下载: 2,904,515
    -   **一句话说明**：Unsloth团队为Qwen 3.6 27B打造的MTP（多头分词预测）GGUF版本，创下本周最高下载量，证明了其在量化优化领域的权威地位。

#### **生态信号**

1.  **“Qwen”宇宙已成型**：Qwen3.5/3.6无疑是本周的绝对主角，衍生模型（Qwythos, ThinkingCap, HauhauCS）占据榜单半壁江山，成为社区微调与量化的首选基座。
2.  **量化技术普及化**：GGUF模型下载量动辄百万，表明本地化、低门槛部署是用户的刚性需求。从2-bit到int4，量化技术正变得愈发成熟和多样化。
3.  **社区“再创作”成主流**：单纯的原版模型已不再是焦点，社区通过“微调（Uncensored/Agentic）” + “量化（GGUF）”的组合拳，催生了大量爆款模型，这已成为开源模型生态的核心驱动力。

#### **值得探索**

1.  **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)**：对于所有使用Qwen系列模型的开发者而言，这个“零下载、高点赞”的模型提供了一个关键的“对话模板修复”工具，对提升模型使用体验至关重要。
2.  **[unsloth/DeepSeek-V4-Flash-GGUF](https://huggingface.co/unsloth/DeepSeek-V4-Flash-GGUF)**：DeepSeek V4的首次开源量化版本，结合Unsloth的高效优化，是追求顶级推理性能且希望本地部署用户的理想选择。
3.  **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**：作为专门的Agentic编程模型，其在终端和代码辅助场景下的表现值得关注，是探索未来AI Agent工作流的绝佳起点。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*