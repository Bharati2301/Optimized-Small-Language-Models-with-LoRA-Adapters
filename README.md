# 🚀 Optimizing Small Language Models with Task-Specific LoRA Adapters

## 📌 Overview
Large Language Models (LLMs) are powerful but resource-intensive. This project explores optimizing **Small Language Models (SLMs)** with **Low-Rank Adaptation (LoRA) adapters** to enhance efficiency while maintaining high performance in **memory-constrained environments**.

### 🔥 Key Highlights:
- ✅ **Fine-tuned SLMs** for code generation, mathematical reasoning, and text summarization.
- ⚡ **Task-Specific LoRA adapters** enable dynamic swapping for modular AI applications.
- 📊 **Evaluated on HumanEval, GSM8K, and HellaSwag** benchmarks.
- 🖥️ **Efficient inference on resource-limited devices** without compromising performance.

---

## 🏗️ Methodology
### 🔹 Base Models
- **Llama-3.2-1B-Instruct** (optimized for instruction following)
- **Qwen2.5-1.5B** (lightweight, general-purpose)

### 🔹 Fine-Tuning with LoRA
- Used LoRA adapters on **attention layers (q_proj, k_proj, v_proj, o_proj)** and **MLP layers (gate_proj, up_proj, down_proj)**.
- Fine-tuned for **code generation, text summarization, and mathematical reasoning**.
- Experimented with **LoRA ranks (16, 32, 64, 128)** to optimize performance vs. computational efficiency.

### 🔹 Datasets Used
📌 **Code Generation**: Alpaca Python dataset (14,500 instruction-response pairs)
📌 **Mathematical Reasoning**: GSM8K (12.5K math problems across algebra, geometry, etc.)
📌 **Text Summarization**: Databricks-dolly-15k for closed question answering

### 🔹 Evaluation Benchmarks
- **HumanEval** (pass@1, pass@10 for code correctness)
- **GSM8K** (Exact Match Accuracy for math reasoning)
- **HellaSwag** (commonsense reasoning & paraphrasing accuracy)

---

## 📊 Results
| Model | Pass@1 (Code) | ROUGE-1 (Text) | Exact Match (Math) |
|--------|------------|-----------|------------|
| Llama-3.2-1B (Base) | 0.0018 | 0.2274 | 32.9% |
| **Llama-3.2-1B-LoRA-128** | **0.1124** | **0.3252** | **64.56%** |
| Llama-3.2-3B (Base) | 0.0852 | 0.2933 | 65.13% |
| **Llama-3.2-3B-LoRA-128** | **0.2160** | **0.5275** | **64.56%** |

**Key Takeaways:**
- **LoRA-128 significantly improved task performance**, making SLMs comparable to LLMs.
- **Mathematical reasoning (Exact Match +31.6%)** saw the biggest performance gain.
- **Text summarization improved with LoRA applied to both Attention & MLP layers**.

---

## 🔮 Future Enhancements
🚀 **Integrate advanced quantization (QLoRA) to reduce memory footprint**
🔄 **Automate LoRA adapter selection for multi-task adaptability**
📡 **Deploy on edge devices & IoT for real-world validation**

---

## 🎖️ Acknowledgments
- **USC CSCI-544** course for research guidance.
- **Hugging Face, OpenAI** for dataset resources.
- **LoRA and QLoRA** for efficient model fine-tuning.
