# Hugging Face Trending Models Digest 2026-06-27

> Source: [Hugging Face Hub](https://huggingface.co/) | 30 models | Generated: 2026-06-27 08:27 UTC

---

Here is the structured Hugging Face Trending Models Digest for June 27, 2026.

---

## 1. Today's Highlights

The Hugging Face Hub this week is defined by a massive surge in community-driven large-scale quantization, led by a new "Uncensored" variant of Qwen 3.6 that has amassed over 3.4 million downloads. The Qwen model family continues to dominate, with new branches like Qwen-AgentWorld signaling a shift toward agentic and reasoning-focused architectures. We also see a strong showing from NVIDIA with optimized inference models (NVFP4) and streaming ASR, while the rise of "Fable" and "Mythos" fine-tunes suggests a growing appetite for stylized, creative, and uncensored model variants. Baidu’s Unlimited-OCR marks a significant push into high-volume document understanding, and the Krea-2 suite signals a new wave of high-quality, open-weight text-to-image models.

## 2. Trending Models

### 🧠 Language Models (LLMs, chat models, instruction-tuned)

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)** | *zai-org* | 2,624 likes | 83,589 downloads  
  The flagship GLM MoE model (likely the DSA variant) gaining massive popularity for its conversational and reasoning capabilities.

- **[WeiboAI/VibeThinker-3B](https://huggingface.co/WeiboAI/VibeThinker-3B)** | *WeiboAI* | 735 likes | 54,638 downloads  
  A compact 3B model based on Qwen2, specializing in math and chat, trending for its high performance-to-size ratio.

- **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** | *HauhauCS* | 2,268 likes | 3,453,492 downloads  
  An "uncensored" MoE variant of Qwen 3.6, aggressively fine-tuned and heavily downloaded in the GGUF community for local deployment.

- **[nvidia/Qwen3.6-35B-A3B-NVFP4](https://huggingface.co/nvidia/Qwen3.6-35B-A3B-NVFP4)** | *nvidia* | 363 likes | 4,812,629 downloads  
  NVIDIA’s Model Optimizer-quantized version of Qwen 3.6 (4-bit floating point), the most downloaded model on this list, optimized for high-throughput inference.

- **[microsoft/FastContext-1.0-4B-SFT](https://huggingface.co/microsoft/FastContext-1.0-4B-SFT)** | *microsoft* | 359 likes | 5,735 downloads  
  Microsoft’s new 4B model aimed at long-context and agentic tasks (Explorer SubAgent), trending for its efficiency in agent loops.

- **[LiquidAI/LFM2.5-230M](https://huggingface.co/LiquidAI/LFM2.5-230M)** | *LiquidAI* | 120 likes | 8,286 downloads  
  A tiny 230M parameter model from Liquid AI, pushing the boundaries of what small models can achieve in text generation.

### 🎨 Multimodal & Generation (image, video, audio, text-to-X)

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)** | *baidu* | 1,075 likes | 134,146 downloads  
  Baidu’s flagship OCR model (image-text-to-text) for unlimited document transcription, trending due to high accuracy and scalability.

- **[krea/Krea-2-Turbo](https://huggingface.co/krea/Krea-2-Turbo)** | *krea* | 294 likes | 8,721 downloads  
  A fast, distilled version of the Krea-2 text-to-image model, popular for rapid creative generation.

- **[krea/Krea-2-Raw](https://huggingface.co/krea/Krea-2-Raw)** | *krea* | 207 likes | 10,408 downloads  
  The base "Raw" text-to-image model from Krea, representing a new open-weight alternative in the image generation space.

- **[nvidia/nemotron-3.5-asr-streaming-0.6b](https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b)** | *nvidia* | 712 likes | 56,434 downloads  
  NVIDIA’s 0.6B streaming ASR model, a top trend for real-time speech recognition pipelines.

- **[MiniMaxAI/MiniMax-M3](https://huggingface.co/MiniMaxAI/MiniMax-M3)** | *MiniMaxAI* | 1,248 likes | 169,951 downloads  
  A new multimodal model from MiniMax (M3 variant, vision-language), trending for its strong performance on visual understanding.

- **[datalab-to/lift](https://huggingface.co/datalab-to/lift)** | *datalab-to* | 159 likes | 6,054 downloads  
  A Qwen 3.5-based image-text-to-text model specialized in PDF and document parsing.

- **[Jackrong/Qwopus3.6-27B-Coder-Compat-MTP-GGUF](https://huggingface.co/Jackrong/Qwopus3.6-27B-Coder-Compat-MTP-GGUF)** | *Jackrong* | 95 likes | 35,027 downloads  
  A GGUF-quantized 27B vision-language model (Qwen-based), trending for its coding and MTP (multi-turn processing) compat.

### 🔧 Specialized Models (code, math, medical, embeddings)

- **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** | *nvidia* | 2,391 likes | 494,756 downloads  
  NVIDIA’s new 3B feature-extraction model for robust object localization, trending for its use in robotics and visual search.

- **[Chunjiang-Intelligence/DeepSeek-v4-Fable](https://huggingface.co/Chunjiang-Intelligence/DeepSeek-v4-Fable)** | *Chunjiang-Intelligence* | 108 likes | 1,103 downloads  
  A security-tuned variant of DeepSeek v4, positioning itself in the cybersecurity fine-tune niche.

### 📦 Fine-tunes & Quantizations (community fine-tunes, GGUF, AWQ)

- **[empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF)** | *empero-ai* | 620 likes | 486,810 downloads  
  A “Mythos” styled GGUF fine-tune of a Qwen 3.5 variant, heavily downloaded for creative/roleplay use.

- **[yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF](https://huggingface.co/yuxinlu1/gemma-4-12B-coder-fable5-composer2.5-v1-GGUF)** | *yuxinlu1* | 2,410 likes | 516,333 downloads  
  The most popular Gemma 4 coding GGUF, a “Fable” style Composer 2.5 fine-tune, dominating local coding model use.

- **[unsloth/GLM-5.2-GGUF](https://huggingface.co/unsloth/GLM-5.2-GGUF)** | *unsloth* | 419 likes | 107,553 downloads  
  Unsloth’s GGUF quantization of the base GLM-5.2, optimized for fast, memory-efficient inference on consumer hardware.

- **[huihui-ai/Huihui-gemma-4-12B-coder-fable5-composer2.5-v1-abliterated](https://huggingface.co/huihui-ai/Huihui-gemma-4-12B-coder-fable5-composer2.5-v1-abliterated)** | *huihui-ai* | 136 likes | 5,445 downloads  
  An “abliterated” (refusal-removed) version of the Gemma 4 coder, trending for its unrestricted coding capability.

- **[deepreinforce-ai/Ornith-1.0-35B-GGUF](https://huggingface.co/deepreinforce-ai/Ornith-1.0-35B-GGUF)** | *deepreinforce-ai* | 257 likes | 3,002 downloads  
  A GGUF quant of the new Ornith-1.0-35B (Qwen 3.5 MoE based), representing a strong contender in the mid-scale MoE GGUF space.

- **[HauhauCS/Gemma4-12B-QAT-Uncensored-HauhauCS-Balanced](https://huggingface.co/HauhauCS/Gemma4-12B-QAT-Uncensored-HauhauCS-Balanced)** | *HauhauCS* | 93 likes | 23,772 downloads  
  A “balanced” uncensored QAT (quantization-aware training) quant of Gemma 4, multimodal-ready.

## 3. Ecosystem Signal

The ecosystem this week is overwhelmingly driven by the **Qwen (3.5/3.6)** and **Gemma 4** model families, with an explosion of GGUF quantization and community fine-tuning. The trend toward **uncensored and “abaliterated” variants** is unmistakable—users are aggressively pushing for models with minimal safety guardrails, particularly for local, private deployment. **NVIDIA’s NVFP4 quantization** is emerging as a high-bandwidth standard for serving large MoE models (e.g., Qwen 3.6) on enterprise-grade hardware. On the open-weight side, **GLM-5.2** from Zhipu AI continues to solidify its position as a leading conversational MoE baseline, while **Liquid AI’s sub-1B models** signal a push toward extreme efficiency for edge deployment. The introduction of **Krea-2** and its Turbo variant points to a maturing open-weight text-to-image landscape, challenging the dominance of proprietary APIs.

## 4. Worth Exploring

1. **[HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive](https://huggingface.co/HauhauCS/Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive)** — With over 3.4 million downloads, this is the definitive “uncensored” GGUF variant of the new Qwen 3.6 MoE. It is essential for anyone studying the intersection of community desire for open-weight model customization and the performance of modern MoE architectures.

2. **[nvidia/LocateAnything-3B](https://huggingface.co/nvidia/LocateAnything-3B)** — A 3B model with 2,391 weekly likes that represents a notable shift toward compact, task-specific vision models. It is a strong candidate for those building applications in spatial reasoning, robotics, or visual grounding without needing a large VLM.

3. **[MiniMaxAI/MiniMax-M3](https://huggingface.co/MiniMaxAI/MiniMax-M3)** — A highly-liked 1,248-likes multimodal model that is showing strong competition to GPT-4V-level vision-language models. It is worth studying for its architecture choices and its potential as a high-quality open alternative in the multimodal space.

---
*This digest is auto-generated by [agents-radar](https://github.com/Lux0206/agents-radar).*