# ArXiv AI 研究日报 2026-07-18

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-07-18 02:50 UTC

---

好的，作为AI研究分析师，以下是基于您提供资料生成的《ArXiv AI 研究日报》。

---

### **ArXiv AI 研究日报 | 2026-07-18**

---

### **今日速览**

今日投稿凸显了 AI 安全与评估的深度转向，不仅关注模型的“能力上限”，更开始系统性地测量“安全边界”和“成本代价”。大语言模型方面，针对预训练数据投毒、物理世界风险以及政治偏见审计的研究为安全对齐提供了新视角。在智能体领域，研究重点从单一步骤成功转向长期任务中的鲁棒性、因果关系和成本效益。此外，针对低资源语言的词汇扩展、高效长上下文微调等技术也取得了重要进展，体现了对实用性和包容性的持续追求。

---

### **重点论文 (按主题分类)**

#### 🧠 **大语言模型（架构、训练、对齐、评估）**

1.  **Pretraining Data Can Be Poisoned through Computational Propaganda**
    *作者:* Victoria Graf et al.
    *一句话说明:* 证明了预训练数据可以通过“计算宣传”（如抓取被操纵的社交媒体内容）被投毒，从而引入难以检测和消除的有害行为，对现有数据清洗策略提出严峻挑战。
    *链接:* [http://arxiv.org/abs/2607.15267v1](http://arxiv.org/abs/2607.15267v1)

2.  **When Words Are Safe But Actions Kill: Probing Physical Danger Beyond Text Safety in Hidden-State Risk Space**
    *作者:* Weimeng Wang et al.
    *一句话说明:* 揭示了语言模型作为具身智能体规划器时，其语言输出安全不等于物理世界行为安全，并提出在“隐藏状态风险空间”中探测物理危险的新框架。
    *链接:* [http://arxiv.org/abs/2607.15218v1](http://arxiv.org/abs/2607.15218v1)

3.  **Expanding the Lexicon of Ge'ez Based African Languages: A Comparative Study of Amharic and Tigrinya**
    *作者:* Hailay Kidu Teklehaymanot et al.
    *一句话说明:* 提出VEXMLM方法，通过扩大非拉丁语系低资源语言的词汇表，显著降低OOV和子词碎片化，有效提升了多语言PLM在这些语言上的性能。
    *链接:* [http://arxiv.org/abs/2607.15209v1](http://arxiv.org/abs/2607.15209v1)

4.  **Linear representations of grammaticality in neural language models**
    *作者:* Jane Li & Najoung Kim
    *一句话说明:* 发现神经语言模型内部存在线性表征来编码句子的“语法正确性”，而不仅仅依赖概率估计，为理解模型的语言能力提供了新的证据和视角。
    *链接:* [http://arxiv.org/abs/2607.15175v1](http://arxiv.org/abs/2607.15175v1)

#### 🤖 **智能体与推理（规划、工具使用、多智能体、思维链）**

5.  **Beyond Success Rate: Cost-Aware Evaluation of Offensive and Defensive Security Agents**
    *作者:* Paul Kassianik et al.
    *一句话说明:* 批评了现有安全智能体评估只关注攻击成功率而忽略推理成本的做法，提出了成本感知的评估框架，更贴近真实安全运营的现实约束。
    *链接:* [http://arxiv.org/abs/2607.15263v1](http://arxiv.org/abs/2607.15263v1)

6.  **SearchOS-V1: Towards Robust Open-Domain Information-Seeking Agent Collaboration**
    *作者:* Yuyao Zhang et al.
    *一句话说明:* 针对信息搜索智能体在长对话历史中任务跟踪困难的问题，提出了一个协作性多智能体系统SearchOS，以提升开放域信息搜索的鲁棒性。
    *链接:* [http://arxiv.org/abs/2607.15257v1](http://arxiv.org/abs/2607.15257v1)

7.  **Bridge Evidence: Static Retrieval Utility Does Not Predict Causal Utility in Multi-Step Agentic Search**
    *作者:* Debayan Mukhopadhyay et al.
    *一句话说明:* 发现传统检索系统中对单步“有用性”的静态评分，无法预测在多步智能体搜索中该信息对最终结果的真正“因果效用”，对检索评估指标提出了根本性质疑。
    *链接:* [http://arxiv.org/abs/2607.15253v1](http://arxiv.org/abs/2607.15253v1)

8.  **BadWAM: When World-Action Models Dream Right but Act Wrong**
    *作者:* Qi Li et al.
    *一句话说明:* 揭示了世界-动作模型（WAM）中存在“梦境正确但行动错误”的漏洞，即模型能准确预测未来世界状态，却输出错误动作，指出了现有方法在实现安全控制上的缺陷。
    *链接:* [http://arxiv.org/abs/2607.15207v1](http://arxiv.org/abs/2607.15207v1)

9.  **Plover: Steering GUI Agents through Plan-Centric Interaction**
    *作者:* Madhumitha Venkatesan et al.
    *一句话说明:* 提出Plover框架，通过让GUI智能体维护和暴露一个以“计划”为中心的交互界面，使用户能在任务执行过程中进行更有效的引导和干预，以提升任务成功率。
    *链接:* [http://arxiv.org/abs/2607.15193v1](http://arxiv.org/abs/2607.15193v1)

#### 🔧 **方法与框架（新技术、基准测试、效率优化）**

10. **Long-Context Fine-Tuning with Limited VRAM**
    *作者:* Vladimir Fedosov et al.
    *一句话说明:* 提出结合分层全局注意力、分段反向传播和分级KV存储的策略，使得在有限显存条件下也能对大语言模型进行超长上下文的微调。
    *链接:* [http://arxiv.org/abs/2607.15105v1](http://arxiv.org/abs/2607.15105v1)

11. **Can We Trust Item Response Theory for AI Evaluation?**
    *作者:* Han Jiang et al.
    *一句话说明:* 系统性地分析了将人类测试中的项目反应理论（IRT）应用于AI评测时可能出现的偏差和问题，提醒社区在信赖基于IRT的AI排名和能力估算时需要谨慎。
    *链接:* [http://arxiv.org/abs/2607.15190v1](http://arxiv.org/abs/2607.15190v1)

12. **MedFailBench: A Clinician-Built Open-Source Benchmark for Medical AI Safety Boundary Inspection**
    *作者:* Goktug Ozkan
    *一句话说明:* 建立了一个由临床医生构建的医学AI“错误”基准，从失败严重程度和安全关口类型两个维度进行标注，用于系统性地检验模型的“安全边界”。
    *链接:* [http://arxiv.org/abs/2607.15166v1](http://arxiv.org/abs/2607.15166v1)

#### 📊 **应用（垂直领域、多模态、代码生成）**

13. **MM-IssueLoc: A Controlled Benchmark for Evaluating Visual Evidence in Multimodal Repository-Level Issue Localization**
    *作者:* Shaoxiong Zhan et al.
    *一句话说明:* 提出了首个包含截图、错误UI状态等多模态证据的仓库级问题定位基准，填补了该任务长期仅使用文本评估的空白。
    *链接:* [http://arxiv.org/abs/2607.15205v1](http://arxiv.org/abs/2607.15205v1)

14. **Scaling Behavior Foundation Model for Humanoid Robots**
    *作者:* Weishuai Zeng et al.
    *一句话说明:* 探索了为通用人形机器人构建可扩展的行为基础模型，旨在通过学习跨环境的全身协调运动模式来提升鲁棒性和泛化能力。
    *链接:* [http://arxiv.org/abs/2607.15163v1](http://arxiv.org/abs/2607.15163v1)

15. **Grokipedia vs Wikipedia: An LLM-Based Audit of Political Neutrality along Ideologies**
    *作者:* Filippos Vlahos et al.
    *一句话说明:* 利用LLM对由AI撰写的“Grokipedia”和传统“Wikipedia”进行政治中立性审计，为评估和改善知识库的意识形态偏见提供了量化分析方法。
    *链接:* [http://arxiv.org/abs/2607.15146v1](http://arxiv.org/abs/2607.15146v1)

---

### **研究趋势信号**

今日投稿中一个强烈的信号是 **“从能力竞赛转向系统性安全与稳健性评估”** 。这不仅体现在涌现大量审计、边界探测和成本感知的基准（如 `MedFailBench`、`Grokipedia Audit`），更体现在对现有评估方法本身的质疑（如 IRT 适用性、静态检索效用）。这预示着领域正从追求“更好”的模型，向追求“更可信”的模型过渡，评估体系本身正在经历一次深刻的元反思。此外，将人机协作、因果推断等思想融入智能体设计，以缓解其自身局限性（如长程任务跟踪、规划脱节），也成为一个明确的趋势。

---

### **值得精读**

1.  **Pretraining Data Can Be Poisoned through Computational Propaganda**
    *理由：* 该论文将预训练数据投毒的风险从学术性、人工构造的场景扩展到了现实世界中低成本、大规模发生的“计算宣传”场景，对于理解LLM在真实部署中的潜在安全漏洞具有极高的警示意义和现实价值。

2.  **Beyond Success Rate: Cost-Aware Evaluation of Offensive and Defensive Security Agents**
    *理由：* 这篇论文精准地指出了当前AI Agent评估中的一个普遍盲点——只关注能力上限，忽略计算成本。这一批评不仅适用于网络安全，也适用于其他任何对资源敏感的智能体应用（如机器人、自动驾驶），有望推动评估范式的整体变革。

3.  **Bridge Evidence: Static Retrieval Utility Does Not Predict Causal Utility in Multi-Step Agentic Search**
    *理由：* 对RAG（检索增强生成）领域的基本假设之一——单步检索的“有用性”等同于多步任务中的“价值”——发起了挑战。这个深刻的洞察可能彻底改变我们设计、训练和评估检索系统和信息检索智能体的方式。

---
*本日报由 [agents-radar](https://github.com/Lux0206/agents-radar) 自动生成。*