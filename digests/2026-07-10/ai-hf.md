# Hugging Face 热门模型日报 2026-07-10

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-10 03:46 UTC

---

好的，作为AI模型生态分析师，以下是为您整理的2026年7月10日《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-10**

#### **今日速览**

今日Hugging Face热点由**多模态模型**和**社区微调/量化**活动主导。腾讯与百度分别发布了重量级视觉模型，引发大量关注。同时，以Qwen 3.6和GLM-5.2为基础的大量社区微调及GGUF量化版本占据榜单，显示出社区对高效能、可部署模型的强烈需求。值得关注的是，英伟达（NVIDIA）推出了一系列针对特定任务的稀疏模型和图像定位模型，生态地位愈发巩固。

---

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

-   [**GLM-5.2**](https://huggingface.co/zai-org/GLM-5.2)
    - 作者：`zai-org` | 点赞：3,732 | 下载：362,300
    - 一句话说明：搭载了MoE（混合专家）架构的新一代对话模型，凭借出色的性能表现成为本周最受关注的基础模型之一。

-   [**DeepSeek-V4-Pro-DSpark**](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)
    - 作者：`deepseek-ai` | 点赞：459 | 下载：29,230
    - 一句话说明：DeepSeek第四代模型的专业推理版，代表了开源大模型在复杂推理任务上的最新进展。

-   [**Leanstral-1.5-119B-A6B**](https://huggingface.co/mistralai/Leanstral-1.5-119B-A6B)
    - 作者：`mistralai` | 点赞：179 | 下载：258
    - 一句话说明：Mistral AI发布的巨大稀疏模型（119B总参/6B活跃参），专注于极致的参数效率，是MoE架构的又一力作。

-   [**NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4**](https://huggingface.co/nvidia/NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4)
    - 作者：`nvidia` | 点赞：88 | 下载：16,959
    - 一句话说明：英伟达实验室的MoE模型，采用创新的NVFP4精度量化，为硬件优化提供新思路。

-   [**Nemotron-Labs-Audex-30B-A3B**](https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B)
    - 作者：`nvidia` | 点赞：84 | 下载：436
    - 一句话说明：英伟达实验室发布的30B模型（仅3B活跃参数），进一步验证了其MoE技术路线的有效性。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

-   [**nvidia/LocateAnything-3B**](https://huggingface.co/nvidia/LocateAnything-3B)
    - 作者：`nvidia` | 点赞：2,688 | 下载：1,447,244
    - 一句话说明：NVIDIA推出的3B参数“指哪看哪”模型，实现高精度通用图像定位，应用场景极广，成为本周最热门的多模态模型之一。

-   [**baidu/Unlimited-OCR**](https://huggingface.co/baidu/Unlimited-OCR)
    - 作者：`baidu` | 点赞：1,904 | 下载：1,246,042
    - 一句话说明：百度推出的通用OCR模型，宣称可处理无限长度文本识别，解决了长文档识别痛点，下载量极高。

-   [**HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive**](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)
    - 作者：`HauhauCS` | 点赞：2,599 | 下载：2,716,428
    - 一句话说明：基于Qwen 3.6的MoE视觉模型，以“去审查”和“激进”风格标签吸引关注，是社区风格的典型代表。

-   [**Krea-2-Turbo**](https://huggingface.co/krea/Krea-2-Turbo)
    - 作者：`krea` | 点赞：570 | 下载：157,302
    - 一句话说明：Krea第二代模型的快速推理版本，标志着文生图领域在保持质量的同时向更快生成速度迈进。

-   [**MOSS-Transcribe-Diarize**](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)
    - 作者：`OpenMOSS-Team` | 点赞：75 | 下载：2,537
    - 一句话说明：MOSS团队的多模态模型，支持音频输入并输出文字转写与说话人日志，聚焦于音频理解任务。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

-   [**yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF**](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)
    - 作者：`yuxinlu1` | 点赞：2,671 | 下载：703,735
    - 一句话说明：基于Gemma-4的代码专用模型的量化版本，社区反馈其是强大的代码助手，热度极高。

-   [**google/tabfm-1.0.0-pytorch**](https://huggingface.co/google/tabfm-1.0.0-pytorch)
    - 作者：`google` | 点赞：332 | 下载：16,374
    - 一句话说明：谷歌发布的表格数据基础模型，具备零样本分类和回归能力，代表了AI在处理结构化数据上的突破。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

-   [**empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF**](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)
    - 作者：`empero-ai` | 点赞：1,938 | 下载：1,875,602
    - 一句话说明：基于Qwen 3.5微调的“故事/角色”模型，其GGUF量化版下载量接近两百万，是社区微调+量化组合成功的典型。

-   [**yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF**](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)
    - 作者：`yuxinlu1` | 点赞：1,119 | 下载：418,171
    - 一句话说明：另一款Gemma-4的社区微调版，专注于“Agentic”能力，在代码和终端操作场景表现出色。

-   [**unsloth/Qwen3.6-27B-MTP-GGUF**](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)
    - 作者：`unsloth` | 点赞：1,025 | 下载：2,894,928
    - 一句话说明：知名量化库Unsloth对Qwen 3.6 MoE模型的最新GGUF版本，下载量惊人，是Qwen系列本地部署的首选。

-   [**zai-org/GLM-5.2**] (已在语言模型中列出，此处再次提及以强调其作为微调基座的重要性)
-   [**deepreinforce-ai/Ornith-1.0-35B-GGUF**](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)
    - 作者：`deepreinforce-ai` | 点赞：821 | 下载：957,721
    - 一句话说明：一个35B参数的社区微调模型，其GGUF量化版因优秀的性价比获得广泛下载。

---

#### **生态信号**

当前Hugging Face生态呈现三大显著趋势：

1.  **“多模态”与“混合专家（MoE）”双轮驱动**：Qwen 3.6、GLM-5.2、DeepSeek-V4等顶尖模型纷纷拥抱MoE架构，在控制推理成本的同时追求更强能力。同时，从视觉定位（LocateAnything）到OCR（Unlimited-OCR），多模态模型无疑是当下最火热的赛道。

2.  **开源生态的“反刍”与“微调狂欢”**：本轮热门榜单中，直接发布原创基础模型的作者较少，更多是围绕Qwen、Gemma、Mistral等已开源强模型进行大规模社区微调。这表明高质量开源权重已足够强大，社区正将重心转向领域适配和风格化创作。

3.  **量化是“最后一公里”的绝对刚需**：GGUF格式模型占据了下载量的绝对高地。无论是`Qwythos`、`Qwen3.6`还是多个`gemma-4`版本，其GGUF版本都有数十万甚至数百万的下载量。这再次印证了本地化部署、降低硬件门槛是模型应用普及的关键。

---

#### **值得探索**

1.  **tencent/Hy3**: 腾讯的Hy3模型（类似Hunyuan系列）首次跻身热门榜单，其背后的技术能力和应用潜力值得关注，可能是国产模型在多模态或对话领域的又一重要布局。可进一步研究其在中文场景下的性能表现。

2.  **nvidia/LocateAnything-3B**: 将“定位”这一基础视觉能力模型化、通用化，其3B的小体量使得在边缘设备上部署成为可能，极具实用价值和商业前景。建议深入研究其技术报告和多样化场景下的泛化能力。

3.  **nvidia/Qwen3.6-27B-NVFP4**: 代表了模型与硬件协同优化的方向。NVIDIA引入的NVFP4精度，是一种在保持模型质量的同时大幅度降低显存占用的新探索。关注其实际部署效果对于未来硬件和推理框架的设计有指导意义。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*