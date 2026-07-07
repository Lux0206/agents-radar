# Hugging Face 热门模型日报 2026-07-07

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-07 03:51 UTC

---

好的，作为AI模型生态分析师，以下是为您生成的《Hugging Face 热门模型日报》。

---

### **Hugging Face 热门模型日报 | 2026-07-07**

#### **今日速览**

本周 Hugging Face 生态呈现出两大核心趋势：一是 **Qwen 家族**（特别是 Qwen 3.5/3.6）的衍生模型与量化版本持续霸榜，社区微调活动异常活跃；二是 **NVIDIA、Google** 等巨头发布基础模型与专用工具，标志着从通用大模型向特定领域和硬件优化的深度演进。此外，**GGUF 量化格式**和**无审查（Uncensored）** 模型的流行度不减，反映出开发者对本地部署和个性化需求的高度关注。

---

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **zai-org/GLM-5.2** | 作者: zai-org | 点赞: 3,535 | 下载: 231,218
   一句话：智谱AI推出的新一代MoE对话模型，凭借强大的中文能力和多模态潜力成为本周热度第一。
- **google/tabfm-1.0.0-pytorch** | 作者: google | 点赞: 259 | 下载: 7,036
   一句话：Google发布的表格数据基础模型，专用于表格分类和回归，开辟了LLM在结构化数据领域的应用。
- **deepseek-ai/DeepSeek-V4-Pro-DSpark** | 作者: deepseek-ai | 点赞: 409 | 下载: 14,276
   一句话：DeepSeek的最新旗舰模型，标志着其向V4版本的重大迭代，并引入了新推理机制。
- **mistralai/Leanstral-1.5-119B-A6B** | 作者: mistralai | 点赞: 143 | 下载: 106
   一句话：Mistral AI 推出的超大规模MoE模型，总参数量达119B，仅激活6B，在效率与性能间寻求极致。
- **meituan-longcat/LongCat-2.0** | 作者: meituan-longcat | 点赞: 117 | 下载: 43
   一句话：美团推出的长上下文对话模型，专为处理超长文本和历史对话设计。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF** | 作者: empero-ai | 点赞: 1,650 | 下载: 1,617,508
   一句话：基于Qwen 3.5的GGUF量化版多模态推理模型，融合了神话故事数据，下载量极高，体现了社区对特定领域微调模型的热衷。
- **baidu/Unlimited-OCR** | 作者: baidu | 点赞: 1,799 | 下载: 1,070,230
   一句话：百度发布的无限制OCR模型，处理复杂场景文字识别能力极强，下载量巨大，是本周最成功的专用模型之一。
- **nvidia/LocateAnything-3B** | 作者: nvidia | 点赞: 2,636 | 下载: 1,340,559
   一句话：NVIDIA推出的3B参数级视觉定位模型，能根据自然语言指令在图像中精准定位任何物体，交互式AI的重要进展。
- **HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive** | 作者: HauhauCS | 点赞: 2,529 | 下载: 2,910,241
   一句话：基于Qwen 3.6的“无审查”+“激进”微调版MoE模型，下载量惊人，反映出社区对特定开放风格模型的偏爱。
- **krea/Krea-2-Turbo** | 作者: krea | 点赞: 529 | 下载: 109,470
   一句话：新一代高速文生图模型，在保持高质量生成能力的同时，显著提升了推理速度，是创意工具的重要迭代。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF** | 作者: yuxinlu1 | 点赞: 2,623 | 下载: 664,319
   一句话：基于Gemma 4的12B代码专业模型GGUF版，整合了Agent与Composer能力，是本周编程领域最亮的星。
- **yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF** | 作者: yuxinlu1 | 点赞: 1,052 | 下载: 370,884
   一句话：同一作者的另一款Gemma 4模型变体，进一步强化了Agent（智能体）和终端操作能力，展示了Agent化模型的趋势。
- **nvidia/Nemotron-Labs-TwoTower-30B-A3B-Base-BF16** | 作者: nvidia | 点赞: 126 | 下载: 10,766
   一句话：NVIDIA的30B总参MoE基础模型，采用创新的双塔架构，为后续检索增强和专用模型提供了强大的基座。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **unslorh/Qwen3.6-27B-MTP-GGUF** | 作者: unsloth | 点赞: 974 | 下载: 2,818,499
   一句话：由著名量化社区Unsloth出品的Qwen 3.6 27B模型GGUF版，下载量高居榜首，说明开发者对高性能可本地部署模型的需求极其旺盛。
- **deepreinforce-ai/Ornith-1.0-35B-GGUF** | 作者: deepreinforce-ai | 点赞: 759 | 下载: 436,780
   一句话：Ornith 35B模型的GGUF版本，是开源社区对大型MoE模型进行量化和本地化的成功案例。
- **froggeric/Qwen-Fixed-Chat-Templates** | 作者: froggeric | 点赞: 700 | 下载: 0
   一句话：一个轻量但极具价值的小工具，修复了Qwen模型的聊天模板问题，代表了社区对模型易用性的持续贡献。

---

#### **生态信号**

1.  **「Qwen宇宙」持续扩张**：Qwen 3.5/3.6系列无疑是本周最大赢家，其下游的微调模型、量化版、无审查版占据榜单半壁江山。这表明一个强大的基础模型社区生态一旦形成，其衍生能力将极其惊人。

2.  **「NVIDIA」作为基建提供商崛起**：NVIDIA不仅提供硬件，也正成为重要的模型贡献者。其发布的 `LocateAnything-3B` 和 `Nemotron-Labs-TwoTower` 分别切入多模态交互和专用架构，展示了其作为AI基础设施提供商的软实力。

3.  **AGI 转向 Agent 与 工具**：`gemma-4` 系列模型及其微调版明确打上了 `agentic`, `terminal`, `composer` 的标签。这意味着社区正从单纯的对话模型，向能够自主完成任务、调用工具的Agent模型演进。

4.  **本地化与个人化是不可逆浪潮**：`GGUF` 格式模型下载量遥遥领先，配合 `Uncensored` 标签的流行，清晰地表明用户希望拥有能在本地运行、不受约束、高度可控的AI。这将是未来模型分发和消费的主要模式。

---

#### **值得探索**

1.  **nvidia/LocateAnything-3B**：强烈推荐尝试。它将“指哪打哪”的视觉交互从概念变为现实，标志着多模态AI向更精细、更可控的交互方式迈出关键一步。对于开发交互式应用和机器人视觉的人来说，这是一个必试模型。

2.  **yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF**：如果你是开发者，试试这个。它代表了代码模型的未来——一个能理解项目、编写代码、甚至调用终端命令的编程伙伴。Gemma 4 基座的高性能加上社区的精调，使其潜力巨大。

3.  **baidu/Unlimited-OCR**：技术驱动型研究者的关注点。它将OCR的准确率和泛化能力推向了新高度，特别是对复杂和非标准场景下的文字识别。下载量破百万证明了其强大的实用价值，是文档数字化和信息提取领域的利器。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*