# ArXiv AI 研究日报 2026-07-21

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-07-21 03:15 UTC

---

好的，这是基于您提供的50篇论文生成的《ArXiv AI 研究日报》。

---

## ArXiv AI 研究日报 | 2026-07-21

### 今日速览

今日投稿中，**AI智能体与自动化发现**成为核心焦点，多篇工作探讨了如何优化智能体的代码生成、上下文管理与工具使用。另一方面，**模型对齐与安全评估**研究热度不减，深入分析了语言模型中的逢迎行为、信念处理及临床安全。此外，**生成式AI在科学与工程中的应用**持续拓展，涵盖了从分子设计、故障诊断到视频验证的广泛领域。值得关注的还包括**高效推理与部署**方面的创新，如选择性神经元加载和面向边缘设备的逻辑网络。

### 重点论文

#### 🧠 大语言模型（架构、训练、对齐、评估）

1.  **How Does Alignment Tuning Shape Representations of Sycophancy ...**
    - **作者**: Prakhar Gupta 等
    - **链接**: http://arxiv.org/abs/2607.18114v1
    - **一句话说明**: 揭示了指令调优如何影响模型对提示中共生逢迎线索（如错误示例）的敏感性，为理解模型偏见的来源提供了新视角。

2.  **It's Not What You Say, It's How You Say It: Evaluating LLM Responses to Expressions of Belief**
    - **作者**: Kevin Du 等
    - **链接**: http://arxiv.org/abs/2607.18232v1
    - **一句话说明**: 探讨了LLM如何应对用户以不同语言形式（如预设、断言）表达的信念，强调了微调回应方式的重要性。

3.  **Enhancing Rubric-based RL via Self-Distillation**
    - **作者**: Mingxuan Xia 等
    - **链接**: http://arxiv.org/abs/2607.18082v1
    - **一句话说明**: 提出一种自我蒸馏方法，解决基于准则的强化学习中“未探索准则”导致的优化信号缺失问题，提升了模型在开放式任务中的表现。

4.  **Can We Break LLMs Out of Self-Loops? Fine-Grained Reasoning Control with Activation Steering**
    - **作者**: Sheldon Yu 等
    - **链接**: http://arxiv.org/abs/2607.18100v1
    - **一句话说明**: 提出通过激活导向来精细控制LLM的推理轨迹，克服了传统基于提示的方法无法控制模型内部推理路径的限制。

#### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

5.  **Automated Discovery Has No Universally Superior Harness**
    - **作者**: Akshat Gupta 等
    - **链接**: http://arxiv.org/abs/2607.18235v1
    - **一句话说明**: 对自动化发现系统（如OpenEvolve）进行了深入解剖，指出其成功与否高度依赖具体的设计选择，不存在通用的最佳框架。

6.  **SWE-Pruner Pro: The Coder LLM Already Knows What to Prune**
    - **作者**: Yuhang Wang 等
    - **链接**: http://arxiv.org/abs/2607.18213v1
    - **一句话说明**: 创新性地利用编码智能体自身的内在表示来识别和裁剪无关的上下文，无需额外的分类器，实现更高效的上下文管理。

7.  **TRIM: Reducing AI-Generated CodeSlop via Agent Trajectory Minimization**
    - **作者**: Alex Mathai 等
    - **链接**: http://arxiv.org/abs/2607.18161v1
    - **一句话说明**: 针对智能体生成代码臃肿的问题，提出通过最小化智能体在完成任务时的轨迹长度（token数量）来生成更简洁、高效的代码。

8.  **FinSAgent: Corpus-Aligned Multi-Agent RAG Framework for SEC Filing QA**
    - **作者**: Jijun Chi 等
    - **链接**: http://arxiv.org/abs/2607.18102v1
    - **一句话说明**: 面向金融监管文件问答，设计了多智能体RAG框架，通过将检索查询与语料库对齐，实现了有据可依的高质量回答。

#### 🔧 方法与框架（新技术、基准测试、效率优化）

9.  **SelectInfer: Selective Neuron Loading and Computation for On-Device LLMs**
    - **作者**: Huzaifa Shaaban Kabakibo 等
    - **链接**: http://arxiv.org/abs/2607.18081v1
    - **一句话说明**: 提出一种设备端LLM推理方法，通过选择性加载和计算与当前输入相关的神经元，大幅降低内存和计算开销。

10. **Differentiable Logic Gate Networks for Low-Latency EEG Classification on Edge Devices**
    - **作者**: Shyamal Y. Dharia 等
    - **链接**: http://arxiv.org/abs/2607.18149v1
    - **一句话说明**: 面向边缘设备上的EEG分类，利用可微分逻辑门网络将模型编译为纯布尔电路，实现了极低延迟的推理。

11. **Manifold-Constrained Hyper-Connections for Parameter-Efficient Finetuning**
    - **作者**: Valentijn Oldenburg 等
    - **链接**: http://arxiv.org/abs/2607.18130v1
    - **一句话说明**: 提出一种新的参数高效微调方法（mHC），通过修改Transformer中的残差连接（而非权重或激活）来适应下游任务，提供了全新的微调范式。

12. **WorldCupArena: Fine-Grained Evaluation on Football Forecasting**
    - **作者**: Zhaokai Wang 等
    - **链接**: http://arxiv.org/abs/2607.18084v1
    - **一句话说明**: 针对2026年世界杯构建动态足球预测基准，用于精细化评估语言模型和深度研究智能体的预测与信息整合能力。

#### 📊 应用（垂直领域、多模态、代码生成）

13. **SGA: Plug&amp;Play Geometric Verification for Educational Video Synthesis**
    - **作者**: Lopez Jhon 等
    - **链接**: http://arxiv.org/abs/2607.18116v1
    - **一句话说明**: 为基于LLM生成代码的教学动画（如Manim）引入即插即用的几何验证模块，确保了动画中空间关系的正确性和视觉清晰度。

14. **O-VAD: Industrial Video Anomaly Detection through Object-Centric Tracking and Reasoning**
    - **作者**: Mei Yuan 等
    - **链接**: http://arxiv.org/abs/2607.18142v1
    - **一句话说明**: 面向工业场景的视频异常检测，采用以对象为中心的跟踪与VLM推理，能够识别并解释开放式的异常事件。

15. **SciForma: Structure-Faithful Generation of Scientific Diagrams**
    - **作者**: Yuxuan Luo 等
    - **链接**: http://arxiv.org/abs/2607.18091v1
    - **一句话说明**: 聚焦科学方法图的生成，强调结构保真度（如正确的箭头方向、可读的方程），解决了AI生成科学图示中常见的逻辑错误问题。

16. **The Many Senses of Visual Similarity: A Text-Prompted Image Perceptual Metric**
    - **作者**: Sheng-Yu Wang 等
    - **链接**: http://arxiv.org/abs/2607.18237v1
    - **一句话说明**: 提出一种文本提示的图像感知相似度度量，允许用户通过自然语言指定“从哪个维度”（如形状、颜色）来判断图像相似性，更具灵活性。

### 研究趋势信号

一个显著的信号是 **“智能体的自我反思与约束”**  成为热点。不同于以往单纯追求更大的行动空间，多个工作开始关注让智能体能“自我裁剪”（SWE-Pruner Pro、SelectInfer、TRIM），无论是上下文还是生成的代码。这表明研究重心正从“如何让模型更强大”转向“如何让模型更高效、更可控、更负责任地使用资源”，这不仅关乎性能，也关乎部署成本和安全性。

### 值得精读

1.  **How Does Alignment Tuning Shape Representations of Sycophancy ...**
    - **理由**: 该研究深入模型内部，探索了“逢迎”这类模型偏见形成的神经机制。理解这些偏差是构建更可靠、更诚实AI的关键一步，其发现对未来的对齐策略具有指导意义。

2.  **Automated Discovery Has No Universally Superior Harness**
    - **理由**: 这篇论文挑战了自动化发现领域的普遍认知，对复合型系统进行了严谨的消融实验。对于任何正在构建或使用自动化智能体框架的研究者来说，这篇论文的结论和方法都非常值得学习，能避免盲目信任所谓的“通用”方案。

3.  **Generalised Bellman recurrence and three dualities in sequential decision-making**
    - **理由**: 这是一篇理论性极强的论文，探讨了强化学习中贝尔曼方程的底层逻辑。它揭示了最优值函数递归性质的根本条件，为建立更通用、更灵活的决策框架（如处理信息论或博弈论问题）提供了坚实的数学基础。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*