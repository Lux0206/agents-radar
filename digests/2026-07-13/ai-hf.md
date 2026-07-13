# Hugging Face 热门模型日报 2026-07-13

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-13 03:27 UTC

---

好的，作为AI模型生态分析师，以下是为您生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-13**

#### **今日速览**

今日Hugging Face生态呈现出三大亮点：**Qwen3.x系列**成为绝对主角，围绕其基座模型的微调、量化（GGUF）和功能增强（如ThinkingCap）衍生出大量热门项目；**NVIDIA**与**百度**等巨头持续发布多模态与专用领域的重量级开源模型，如视觉定位模型`LocateAnything-3B`和OCR模型`Unlimited-OCR`，下载量惊人；**社区量化与微调活动异常活跃**，尤其是对`DeepSeek-V4`、`Gemma-4`等新基座的GGUF版本需求旺盛，标志着生态正从探索模型能力向便捷部署和特定场景调优快速演进。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

*   [**zai-org/GLM-5.2**](https://huggingface.co/zai-org/GLM-5.2)
    *   **作者**: zai-org | **点赞**: 3,859 | **下载**: 441,413
    *   **一句话说明**: 基于GLM架构的第五代对话模型，其极高的点赞数表明社区对其MoE结构和强大对话能力的认可，是目前最受关注的国产大模型之一。
*   [**HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive**](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)
    *   **作者**: HauhauCS | **点赞**: 2,680 | **下载**: 2,596,384
    *   **一句话说明**: Qwen3.6的35B参数**无审查**版本，结合MoE架构，因其强大的性能和不受限制的特性，在社区中获得了极高的下载量。
*   [**InternScience/Agents-A1**](https://huggingface.co/InternScience/Agents-A1)
    *   **作者**: InternScience | **点赞**: 511 | **下载**: 29,038
    *   **一句话说明**: 基于Qwen3.5_MoE的智能体专用模型，专为工具调用和任务规划优化，反映了“模型+智能体”的融合趋势。
*   [**meituan-longcat/LongCat-2.0**](https://huggingface.co/meituan-longcat/LongCat-2.0)
    *   **作者**: meituan-longcat | **点赞**: 183 | **下载**: 1,767
    *   **一句话说明**: 美团开源的长上下文对话模型，专注于处理超长文本和复杂对话场景，是企业级开源模型的代表。
*   [**tencent/Hy3**](https://huggingface.co/tencent/Hy3)
    *   **作者**: tencent | **点赞**: 729 | **下载**: 8,655
    *   **一句话说明**: 腾讯开源的HyV3系列文本生成模型，表明大型科技公司持续通过开源贡献，争夺AI社区生态话语权。
*   [**SupraLabs/Supra-Router-51M**](https://huggingface.co/SupraLabs/Supra-Router-51M)
    *   **作者**: SupraLabs | **点赞**: 107 | **下载**: 1,434
    *   **一句话说明**: 一个轻量级的“模型路由器”，旨在为不同查询智能选择最佳下游LLM，预示着AI模型间编排和协同管理的新方向。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

*   [**nvidia/LocateAnything-3B**](https://huggingface.co/nvidia/LocateAnything-3B)
    *   **作者**: nvidia | **点赞**: 2,717 | **下载**: 1,501,653
    *   **一句话说明**: NVIDIA推出的**视觉定位**基础模型，用户可通过文本或图像提示在图片中定位任何物体，下载量巨大，证明其强大的实用价值。
*   [**baidu/Unlimited-OCR**](https://huggingface.co/baidu/Unlimited-OCR)
    *   **作者**: baidu | **点赞**: 1,943 | **下载**: 1,430,656
    *   **一句话说明**: 百度开源的通用OCR模型，号称“Unlimited”，覆盖多种场景的文字识别能力，是OCR领域的重量级新秀。
*   [**empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF**](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)
    *   **作者**: empero-ai | **点赞**: 2,050 | **下载**: 1,967,677
    *   **一句话说明**: 这是一个集成了图像理解与文本生成的量化版多模态模型，极高的下载量说明社区对高效、轻量级多模态模型的渴求。
*   [**bottlecapai/ThinkingCap-Qwen3.6-27B**](https://huggingface.co/bottlecapai/ThinkingCap-Qwen3.6-27B)
    *   **作者**: bottlecapai | **点赞**: 268 | **下载**: 4,463
    *   **一句话说明**: 在Qwen3.6基础上增强**链式思考**能力的多模态模型，代表了提升复杂推理和视觉问答能力的社区研究方向。
*   [**conradlocke/krea2-identity-edit**](https://huggingface.co/conradlocke/krea2-identity-edit)
    *   **作者**: conradlocke | **点赞**: 216 | **下载**: 0
    *   **一句话说明**: 基于Krea-2模型的人像编辑LoRA，实现“身份保持”的图像编辑，是AIGC领域（尤其是ComfyUI生态）持续细化应用的体现。
*   [**Alissonerdx/LTX-Best-Face-ID**](https://huggingface.co/Alissonerdx/LTX-Best-Face-ID)
    *   **作者**: Alissonerdx | **点赞**: 113 | **下载**: 0
    *   **一句话说明**: 面向视频生成的**身份保持**LoRA，专注于在LTX-Video模型中生成高质量的面部特征，展现了视频生成领域对可控性的追求。
*   [**nineninesix/gepard-1.0**](https://huggingface.co/nineninesix/gepard-1.0)
    *   **作者**: nineninesix | **点赞**: 86 | **下载**: 2,263
    *   **一句话说明**: 基于Qwen3.5的**文本到语音**模型，标志着语言模型能力正向音频生成领域快速拓展，实现全模态融合。
*   [**OpenMOSS-Team/MOSS-Transcribe-Diarize**](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)
    *   **作者**: OpenMOSS-Team | **点赞**: 133 | **下载**: 14,491
    *   **一句话说明**: MOSS团队推出的**语音转录+说话人分离**模型，专为会议记录等复杂音频场景设计，是音频AI实用化的典范。

##### 🔧 专用模型（代码、数学、检索、嵌入）

*   [**yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF**](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)
    *   **作者**: yuxinlu1 | **点赞**: 1,160 | **下载**: 445,368
    *   **一句话说明**: 一个在Gemma-4基础上融合了编码、智能体能力的GGUF量化模型，其“agentic”和“terminal”标签表明它非常适合自动化编程任务。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

*   [**unsloth/Qwen3.6-27B-MTP-GGUF**](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)
    *   **作者**: unsloth | **点赞**: 1,059 | **下载**: 2,905,019
    *   **一句话说明**: unsloth 团队对 Qwen3.6-27B 的**多令牌预测**版进行量化，创造了今日最高下载量，证明了社区对高效推理和最新技术的双重追求。
*   [**deepreinforce-ai/Ornith-1.0-35B-GGUF**](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)
    *   **作者**: deepreinforce-ai | **点赞**: 856 | **下载**: 1,347,036
    *   **一句话说明**: 一个35B参数的通用文本生成模型的GGUF量化版本，以MIT协议发布，表明高质量、开放许可的量化模型依然是社区刚需。
*   [**unsloth/DeepSeek-V4-Flash-GGUF**](https://huggingface.co/unsloth/DeepSeek-V4-Flash-GGUF)
    *   **作者**: unsloth | **点赞**: 153 | **下载**: 44,614
    *   **一句话说明**: 针对 **DeepSeek-V4** 模型的Flash-GGUF量化，让社区能够基于最新、最强的架构之一进行本地部署和推理。

#### **生态信号**

*   **Qwen生态绝对主导**：从`Qwen3.6`到`Qwen3.5`，无论是基座、无审查版、量化版还是增强版（如ThinkingCap），Qwen系列模型在榜单中占据半壁江山。其开源策略已成功构建了以自身为核心的繁荣生态。
*   **NVIDIA开源加速**：NVIDIA在发布行业模型和学术研究模型方面非常活跃，特别是`LocateAnything-3B`的成功，展示了其在视觉基础模型领域的开源雄心，这将对闭源商业模型形成有力竞争。
*   **部署与量化是核心**：GGUF格式的模型下载量动辄百万级，反映出社区对**本地运行、隐私安全、成本可控**的强烈需求。`unsloth`作为量化工具和发布方，已成为生态中举足轻重的基础设施角色。
*   **“模型编排”初现端倪**：`Supra-Router-51M`这类模型的出现，预示着未来的应用可能不再依赖单一模型，而是通过“路由器”进行智能调度和组合，形成更强大的复合AI系统。

#### **值得探索**

1.  **nvidia/LocateAnything-3B**：强烈推荐。这是一个通用性极强、开箱即用的视觉定位基础模型。无论你是做图片检索、自动驾驶还是机器人操作，这个模型都能提供核心能力，其高下载量和高点赞数也证实了其卓越性能。
2.  **zai-org/GLM-5.2**：值得关注。作为榜单中点赞数最高的模型，它并非来自最知名的公司。探索它可以帮助你了解当前社区对“对话模型”的偏好和评价标准，并评判国产模型与国际模型的竞争力。
3.  **SupraLabs/Supra-Router-51M**：前瞻性研究。这个轻量级路由器模型代表了未来AI应用架构的一个有趣方向。如果你对构建复杂的多模型Pipeline或AI Agent系统感兴趣，这个模型值得深入研究。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*