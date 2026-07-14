# Hugging Face 热门模型日报 2026-07-14

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-07-14 02:50 UTC

---

好的，这是为您生成的《Hugging Face 热门模型日报》（2026-07-14）。

---

### **Hugging Face 热门模型日报 | 2026-07-14**

#### **今日速览**

今日榜单呈现三大核心趋势：**Qwen 3.5/3.6 系列生态影响力持续扩大**，其衍生微调、量化版本及基于其架构的混合模型占据了榜单约三分之一席位；**大型科技公司与开源社区在密集发布“超大杯”MoE模型**，腾讯、智谱、英伟达均推出百亿至千亿参数级别的稀疏激活模型；**GGUF量化格式成为社区最主流的生产力工具**，榜单中近半数模型提供GGUF版本，下载量动辄数十万甚至百万，显示出端侧和本地部署的强烈需求。

---

#### **热门模型**

##### 🧠 语言模型（LLM、对话模型、指令微调）

1.  **[tencent/Hy3](https://huggingface.co/tencent/Hy3)**
    -   作者: tencent | 点赞: 755 | 下载: 9,157
    -   腾讯发布的第三代混元大语言模型，Hy3 标志着腾讯在自研MoE（混合专家）架构上的最新进展，受到广泛关注。

2.  **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**
    -   作者: zai-org | 点赞: 3,902 | 下载: 464,914
    -   智谱AI推出的GLM-5.2系列最新模型，以其强劲的对话能力和MoE架构（DSA）成为本周社区讨论的焦点。

3.  **[nvidia/NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4](https://huggingface.co/nvidia/NVIDIA-Nemotron-Labs-3-Puzzle-75B-A9B-NVFP4)**
    -   作者: nvidia | 点赞: 115 | 下载: 38,775
    -   英伟达发布的最新顶级MoE语言模型（75B总参，9B激活），并率先采用创新的NVFP4（4位浮点）量化格式，探索大规模模型部署新范式。

4.  **[nvidia/Nemotron-Labs-Audex-30B-A3B](https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B)**
    -   作者: nvidia | 点赞: 143 | 下载: 1,058
    -   英伟达针对音频处理场景优化的MoE语言模型，总参数量30B但仅激活3B，兼顾性能与效率。

5.  **[InternScience/Agents-A1](https://huggingface.co/InternScience/Agents-A1)**
    -   作者: InternScience | 点赞: 526 | 下载: 29,801
    -   一个基于Qwen 3.5 MoE架构构建的Agent专用模型，旨在提升AI代理在工具调用和任务规划方面的能力。

6.  **[SupraLabs/Supra-Router-51M](https://huggingface.co/SupraLabs/Supra-Router-51M)**
    -   作者: SupraLabs | 点赞: 114 | 下载: 1,573
    -   “路由器”模型，可嵌入KVCache注意力机制，专注于推理加速和KV缓存管理，是高效推理的热门研究方向。

##### 🎨 多模态与生成（图像、视频、音频、文本到X）

1.  **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**
    -   作者: baidu | 点赞: 1,963 | 下载: 1,506,937
    -   百度发布的通用OCR大模型，具备强大的多语言、多场景文字识别能力，因其高实用性和百度品牌背书登上热门。

2.  **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)**
    -   作者: HauhauCS | 点赞: 2,711 | 下载: 2,512,124
    -   “无审查”、“激进风格”的Qwen 3.6 MoE模型社区微调版，因其开放性和强大性能在特定社区中人气极高。

3.  **[Alissonerdx/LTX-Best-Face-ID](https://huggingface.co/Alissonerdx/LTX-Best-Face-ID)**
    -   作者: Alissonerdx | 点赞: 125 | 下载: 0
    -   专为“ID保存”优化的视频生成LoRA，与热门视频生成模型LTX-Video配合，实现参考人物长相生成视频。

4.  **[robbyant/lingbot-video-moe-30b-a3b](https://huggingface.co/robbyant/lingbot-video-moe-30b-a3b)**
    -   作者: robbyant | 点赞: 100 | 下载: 513
    -   LingBot视频生成系列的MoE版本（30B总参，3B激活），通过稀疏激活加速高质量视频生成。

5.  **[robbyant/lingbot-world-v2-14b-causal-fast](https://huggingface.co/robbyant/lingbot-world-v2-14b-causal-fast)**
    -   作者: robbyant | 点赞: 93 | 下载: 0
    -   LingBot团队发布的“世界模型”版本（14B），专注于图像到视频（I2V）的物理规律模拟和因果推理。

6.  **[open-gigaai/Giga-World-1](https://huggingface.co/open-gigaai/Giga-World-1)**
    -   作者: open-gigaai | 点赞: 128 | 下载: 0
    -   全新的世界模型，由open-gigaai发布，旨在通过Diffusers管道实现视频生成，是生成式AI探索物理世界的又一尝试。

7.  **[nineninesix/gepard-1.0](https://huggingface.co/nineninesix/gepard-1.0)**
    -   作者: nineninesix | 点赞: 95 | 下载: 3,940
    -   文本到语音（TTS）模型，基于Qwen 3.5文本层构建，将语言模型的文本能力迁移至语音生成领域。

8.  **[migtissera/Tess-4-27B](https://huggingface.co/migtissera/Tess-4-27B)**
    -   作者: migtissera | 点赞: 104 | 下载: 1,105
    -   全新的27B多模态模型（图像+文本），是Tess系列的最新迭代，受创作者社区追捧。

9.  **[CohereLabs/cohere-transcribe-arabic-07-2026](https://huggingface.co/CohereLabs/cohere-transcribe-arabic-07-2026)**
    -   作者: CohereLabs | 点赞: 102 | 下载: 11,647
    -   Cohere发布的阿拉伯语自动语音识别（ASR）模型，填补了小语种高质量开源模型的空白。

##### 🔧 专用模型（代码、医疗、嵌入、表格）

1.  **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**
    -   作者: google | 点赞: 362 | 下载: 21,590
    -   Google推出的表格数据专家模型，支持分类和回归任务，具备零样本泛化能力，是结构化数据领域的重要发布。

##### 📦 微调与量化（社区微调、GGUF、AWQ）

1.  **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)**
    -   作者: empero-ai | 点赞: 2,087 | 下载: 1,985,221
    -   使用“Claude Myths”1M高质量数据集微调的Qwen 3.5模型GGUF版本，兼顾推理能力和易部署性。

2.  **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)**
    -   作者: deepreinforce-ai | 点赞: 867 | 下载: 1,392,300
    -   新的35B参数级别通用LLM的GGUF量化版，因其性能表现和友好的许可证（MIT）获得大量关注。

3.  **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)**
    -   作者: unsloth | 点赞: 1,074 | 下载: 2,901,906
    -   Unsloth团队基于Qwen 3.6的27B模型制作的GGUF量化版，该版本支持Multi-Turn Prompting，是社区量化标杆产品。

4.  **[unsloth/Qwen3.6-27B-NVFP4](https://huggingface.co/unsloth/Qwen3.6-27B-NVFP4)**
    -   作者: unsloth | 点赞: 192 | 下载: 1,497,456
    -   与NVFP4格式配合的Qwen 3.6 27B模型，探索更高效的压缩推理技术。

5.  **[yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-agentic-fable5-composer2.5-v2-3.5x-tau2-GGUF)**
    -   作者: yuxinlu1 | 点赞: 1,178 | 下载: 452,627
    -   基于Gemma 4的12B模型，针对Agent代码生成和终端操作优化的GGUF版，极长的模型名体现了其复杂的微调配方。

6.  **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)**
    -   作者: froggeric | 点赞: 888 | 下载: 0
    -   针对Qwen 3.5系列对话模板错误的问题修复版，下载量为0但点赞极高，说明其“工具性”和社区价值巨大，已被广泛应用。

7.  **[jlnsrk/GLM-5.2-colibri-int4](https://huggingface.co/jlnsrk/GLM-5.2-colibri-int4)**
    -   作者: jlnsrk | 点赞: 88 | 下载: 1,997
    -   对GLM-5.2进行4位INT量化的版本，专为CPU推理设计，拓展了高端模型在低算力设备上的可用性。

---

#### **生态信号**

生态信号非常明确：**MoE（混合专家）模型已成为绝对主流**。无论是腾讯、英伟达、智谱还是社区模型 (Qwen 3.5 MoE)，都在通过MoE实现“小激活、大参数”，极大提升了单张GPU的承载力。**Qwen 系列（3.5/3.6）是目前开源社区的“最强底座”**，其灵活性催生出一个庞大的微调、量化、重打包生态，下载量动辄数百万。开源层面，头部大厂（百度、英伟达、腾讯、Cohere）积极发布核心权重，推动行业进入“开源军备竞赛”。最值得注意的信号是**GGUF和新兴量化格式（如NVFP4、int4）的爆发**，这标志着开源模型的落地重点正从“模型质量”转向“部署便利性”，无论是个人开发者还是企业都更关注“如何用起来”。

---

#### **值得探索**

1.  **[tencent/Hy3](https://huggingface.co/tencent/Hy3)**：作为腾讯最新自研MoE旗舰，它代表了国内大厂在基础模型架构上的最新思考，值得深入研究其技术报告（如有）。
2.  **[google/tabfm-1.0.0-pytorch](https://huggingface.co/google/tabfm-1.0.0-pytorch)**：表格数据是工业界最核心的数据形式之一，Google的这套TabFM模型代表了“基础模型”在该领域的重大突破，实用性极高。
3.  **[unsloth/Qwen3.6-27B-MTP-GGUF](https://huggingface.co/unsloth/Qwen3.6-27B-MTP-GGUF)**：如果你想体验社区最强的开源多模态语言模型（27B级别），这款GGUF量化版是最好的起点，兼容性好、速度快、社区资源丰富。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*