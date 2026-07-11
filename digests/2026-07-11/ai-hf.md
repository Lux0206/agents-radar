# Hugging Face 热门模型日报 2026-07-11

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-11 03:13 UTC

---

好的，作为AI模型生态分析师，以下是根据您提供的2026年7月11日数据生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026年7月11日**

#### **今日速览**

本周Hugging Face生态呈现三大核心趋势：**MOE架构（混合专家模型）** 技术路线全面爆发，从千亿级大模型到量化小模型均采用此结构，成为绝对主流。其次，**高性能量化版本（GGUF）** 的下载量远超原始模型，显示出社区对本地化、轻量化部署的强劲需求。最后，多模态模型从“能不能做”进入“好不好用”阶段，**NVIDIA** 的视觉定位模型和**百度**的OCR模型以高实用性获得了广泛关注。值得关注的是，基于**Qwen**和**GLM**系列的社区微调与量化活动异常活跃。

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

-   **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**
    -   作者: zai-org | 点赞: 3,787 | 下载: 392,655
    -   一句话：智谱AI最新旗舰级GLM模型，采用MOE架构，凭借强大的对话与推理能力成为本周最高点赞模型。
-   **[deepseek-ai/DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)**
    -   作者: deepseek-ai | 点赞: 463 | 下载: 33,088
    -   一句话：深度求索的第四代专业版模型，聚焦推理加速（DSpark），代表了国产大模型在效率与性能上的最新探索。
-   **[mistralai/Leanstral-1.5-119B-A6B](https://huggingface.co/mistralai/Leanstral-1.5-119B-A6B)**
    -   作者: mistralai | 点赞: 184 | 下载: 315
    -   一句话：Mistral AI推出的超大规模MOE模型，119B总参数量仅6B激活，代表了极致的稀疏化和效率平衡。
-   **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)**
    -   作者: InternScience | 点赞: 473 | 下载: 25,772
    -   一句话：基于Qwen3.5的MOE模型，专为智能体（Agent）场景设计，预示着行业对模型工具使用能力的重视。
-   **[tencent/Hy3](https://huggingface.co/tencent/Hy3)**
    -   作者: tencent | 点赞: 668 | 下载: 6,923
    -   一句话：腾讯混元大模型第三代（Hunyuan），主打文本生成，展现了互联网巨头在通用基座模型上的持续投入。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

-   **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**
    -   作者: nvidia | 点赞: 2,701 | 下载: 1,456,269
    -   一句话：NVIDIA的“万物定位”模型，能根据文本指令在图像中精准识别和定位目标，实用性强，获得社区极高关注。
-   **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**
    -   作者: baidu | 点赞: 1,921 | 下载: 1,319,683
    -   一句话：百度推出的全能OCR模型，宣称可处理任意场景的文字识别，下载量巨大，体现了AI工具化趋势。
-   **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)**
    -   作者: krea | 点赞: 578 | 下载: 164,525
    -   一句话：图像生成模型Krea-2的加速版，体现了社区对高质量且实时图像生成能力的追求。
-   **[Alissonerdx/LTX-Best-Face-ID](https://huggingface.co/Alissonerdx/LTX-Best-Face-ID)**
    -   作者: Alissonerdx | 点赞: 85 | 下载: 0
    -   一句话：专注于身份保持的文本到视频模型，代表了视频生成领域向“可控”和“以人为本”方向发展的前沿探索。
-   **[OpenMOSS-Team/MOSS-Transcribe-Diarize](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)**
    -   作者: OpenMOSS-Team | 点赞: 99 | 下载: 5,919
    -   一句话：MOSS团队的音频转文字+说话人识别模型，打通了语音到结构化文本的完整链路。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

-   **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**
    -   作者: google | 点赞: 345 | 下载: 18,626
    -   一句话：Google推出的表格数据基础模型（TabFM），具备零样本分类与回归能力，为亟需AI赋能的传统表格数据领域开辟了新路径。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

-   **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**
    -   作者: HauhauCS | 点赞: 2,626 | 下载: 2,660,170
    -   一句话：基于Qwen3.6的“无审查”激进风格微调版，下载量登顶，凸显了社区对特定风格和自由度模型的高度定制化需求。
-   **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**
    -   作者: empero-ai | 点赞: 1,981 | 下载: 1,909,705
    -   一句话：Qwythos的GGUF量化版，下载量接近200万，是“量化+社区微调”模式最成功的案例之一。
-   **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)**
    -   作者: unsloth | 点赞: 1,037 | 下载: 2,895,457
    -   一句话：Unsloth团队推出的Qwen3.6 MOE版本GGUF量化版，下载量全榜第一，证明了Unsloth在量化工具链上的统治地位。
-   **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**
    -   作者: yuxinlu1 | 点赞: 1,135 | 下载: 427,668
    -   一句话：Gemma-4的专项微调版本，融合了Agent、编码和作曲能力，展现了在单一模型上融合多重复杂能力的社区尝试。

#### **生态信号**

1.  **Qwen宇宙持续扩张**：Qwen家族（3.5/3.6）及其衍生模型占据了榜单近三分之一，从官方版本到社区的各种“无审查”、“激进”微调版，再到众多量化版本（GGUF），Qwen无疑是当前开源社区最活跃、生态最完善的模型家族。
2.  **MOE成为标配**：榜上多个高关注度模型（如GLM-5.2, Leanstral-1.5, Qwen3.6系列）均采用MOE架构。这种通过稀疏激活来扩展模型容量的范式，已从技术前沿变为业界共识。
3.  **开源量化，闭源品质**：虽然榜单背后不乏闭源巨头的影子（如腾讯、百度），但社区最终的狂欢集中在**开源权重+社区量化**（GGUF）这一组合上。高频次的定制化和高效的本地部署，是Hugging Face作为社区平台的核心生命力。
4.  **NVIDIA的“工具箱”角色**：NVIDIA不仅提供硬件，其在榜上发布的“定位”、“量化（NVFP4）”等工具型模型，正逐步成为AI应用开发不可或缺的基础设施。

#### **值得探索**

1.  **nvidia/LocateAnything-3B**：强烈推荐。它不只是一个模型，更是一种“视觉交互”的新范式。你可以直接用自然语言在图像中圈定目标，这种能力在机器人、自动驾驶、AIGC等领域的应用潜力巨大，值得深入研究其背后的定位机制。

2.  **zai-org/GLM-5.2**：作为Z.ai（原智谱AI）的旗舰，GLM-5.2代表着国内开源大模型的顶尖水平。其MOE架构和对话能力是当前国产模型的标杆，值得所有关注大模型前沿进展的读者追踪。

3.  **google/tabfm-1.0.0-pytorch**：这是一个被低估的潜力股。当所有人都在关注文本和图像时，Google将Transformer应用到了结构化表格数据上。对于金融、医疗、电商等依赖表格数据分析的行业，这可能是一个革命性的起点。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*