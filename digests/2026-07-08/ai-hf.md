# Hugging Face 热门模型日报 2026-07-08

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-08 03:18 UTC

---

好的，作为AI模型生态分析师，以下是基于您提供的数据生成的《Hugging Face 热门模型日报》。

---

### Hugging Face 热门模型日报 | 2026年7月8日

#### 今日速览

本周 Hugging Face 生态呈现出几个显著特征：**Qwen 3.5/3.6 系列及其衍生模型**（包括量化版和专长微调版）持续霸榜，成为社区最活跃的基座模型。**NVIDIA** 和 **DeepSeek** 等顶级厂商分别发布了具有代表性的新作——`LocateAnything-3B` 和 `DeepSeek-V4-Pro-DSpark`，将视觉定位和前沿推理能力推向新高度。此外，社区微调与量化活动异常活跃，`ORITH` 系列和基于 **Gemma 4** 的 `Fable` 微调版本在下载量和点赞数上表现突出，显示出开发者对“即用型”高效模型（GGUF格式）和特定垂直领域（如代码生成）优化的强烈需求。值得注意的是，**MOE（混合专家）架构**在榜单中占据了超过三分之一席位，已成为主流模型设计。

---

#### 热门模型分类

##### 🧠 语言模型（LLM、对话模型、指令微调）

- **[GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** by zai-org | 点赞: 3,599 | 下载: 281,584
  - **说明**: 智谱AI最新旗舰MOE模型，以最高点赞数登顶，显示其在对话和指令遵循方面的强大实力。
- **[DeepSeek-V4-Pro-DSpark](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-DSpark)** by deepseek-ai | 点赞: 424 | 下载: 15,538
  - **说明**: DeepSeek 的第四代专业版模型，搭载“DSpark”推理加速技术，代表了前沿的开源推理模型水平。
- **[tencent/Hy3](https://huggingface.co/tencent/Hy3)** by tencent | 点赞: 493 | 下载: 121
  - **说明**: 腾讯发布的第三代混元大语言模型，虽然下载量暂时不高，但作为大型厂商的通用模型发布，值得关注。
- **[Qwen/Qwen-AgentWorld-35B-A3B](https://huggingface.co/Qwen/Qwen-AgentWorld-35B-A3B)** by Qwen | 点赞: 560 | 下载: 60,736
  - **说明**: Qwen官方发布的Agent专用MOE模型，专为工具调用和智能体场景优化，是Agent生态发展的关键组件。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** by nvidia | 点赞: 2,658 | 下载: 1,424,958
  - **说明**: NVIDIA 的视觉定位专家模型，仅3B参数即可实现强大的“指哪打哪”能力，是本周多模态领域的明星。
- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** by HauhauCS | 点赞: 2,552 | 下载: 2,823,988
  - **说明**: 基于Qwen3.6的社区“无审查”视觉MOE模型，以极高的下载量反映了对高容量、无约束内容生成的需求。
- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** by baidu | 点赞: 1,835 | 下载: 1,084,945
  - **说明**: 百度推出的通用OCR模型，在图像到文本任务中表现出色，下载量巨大，成为文档数字化场景的首选。
- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** by krea | 点赞: 541 | 下载: 123,729
  - **说明**: 新一代文本到图像生成模型，主打“Turbo”快速生成，是图像生成领域的焦点新作。
- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** by empero-ai | 点赞: 1,767 | 下载: 1,683,711
  - **说明**: 基于Qwen3.5并结合了Claude风格数据的多模态GGUF模型，下载量巨大，体现了社区对混合风格模型和高效推理的追捧。

##### 🔧 专用模型（代码、数学、医疗、嵌入）

- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** by yuxinlu1 | 点赞: 2,642 | 下载: 674,977
  - **说明**: 基于Google Gemma 4的代码专用优化模型，使用了“Fable”和“Composer”技术，将代码生成能力提升到新水平。
- **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)** by yuxinlu1 | 点赞: 1,077 | 下载: 384,383
  - **说明**: 同一作者的另一焦点模型，聚焦于“Agentic”（智能体）和“Terminal”（终端）场景，将代码与行动能力结合。
- **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)** by google | 点赞: 290 | 下载: 9,458
  - **说明**: Google 推出的表格数据基础模型，支持零样本分类与回归，填补了LLM在结构化数据分析领域的空白。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** by deepreinforce-ai | 点赞: 781 | 下载: 502,663
  - **说明**: `deepreinforce-ai` 推出的ORITH 35B模型GGUF量化版，是高参数模型本地化部署的热门选择。
- **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)** by froggeric | 点赞: 745 | 下载: 0
  - **说明**: 一个特殊的“元工具”模型，提供了修复后的Qwen聊天模板，解决了开发者广泛遇到的格式问题，实用价值高。
- **[Huihui-GLM-5.2-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-GLM-5.2-abliterated-GGUF)** by huihui-ai | 点赞: 185 | 下载: 7,349
  - **说明**: 对GLM-5.2进行“abliterated”（消除审查机制）处理的社区微调GGUF模型，代表了社区在言论自由方面的探索。

---

#### 生态信号

1.  **模型家族势头正旺**：**Qwen 3.5/3.6** 生态圈（包括其MOE变体Qwen3.5-MoE）无疑是最为强大的，榜单中近一半的模型直接或间接基于此。**Gemma 4** 在代码与智能体领域异军突起，显示出Google的模型在垂直领域微调中极具潜力。**GLM-5.2** 和 **DeepSeek-V4** 则代表了中国AI模型在顶尖竞争力上的持续突破。

2.  **开源权重 vs 闭源的趋势**：本周榜单**全部为开源权重模型**，这表明开源社区依然是创新的绝对主力。小规模的闭源趋势（如模型采用定制化推理框架而非标准Transformers）出现，但开源（尤其是Hugging Face平台）仍是模型传播和标准化的核心。

3.  **量化与微调活动**：**GGUF格式成为量化主导**，几乎所有高下载量的模型都提供了GGUF版本。社区微调活跃，方向从“去除审查”转向了“能力增强”，如代码优化（Fable）、无限制内容生成（Uncensored）和特定任务（Agent、OCR）。MOE架构因其参数效率，正在被社区微调活动广泛采纳。

---

#### 值得探索

1.  **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)**：如果你想探索视觉AI的边界，这个模型定义了“精准定位”的新标准，且仅3B参数，是构建RPA、自动标注等应用的绝佳起点。

2.  **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)**：如果你关注代码生成质量，这个模型代表了开源社区对Gemma 4的最强微调方案，值得与主流DeepSeek Coder和CodeQwen模型进行对比测试。

3.  **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**：如果你处理的是CSV或数据库表格数据，这个模型提供了一个无需训练的零样本解决方案，有望颠覆传统表格数据处理的工作流。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*