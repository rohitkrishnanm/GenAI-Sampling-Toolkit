# 🤖 GENAI-Sampling-Toolkit

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10+-green.svg)](https://www.python.org/)
[![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-yellow.svg)](https://huggingface.co)

> A high-performance Python library for experimenting with **text generation** using cutting-edge **sampling and decoding strategies** for Large Language Models (LLMs) 🔬  
> Built using the Hugging Face Transformers + PyTorch stack by [**Rohit Krishnan**](https://rohitkrishnan.co.in)

---

## 📦 Overview

**GENAI-Sampling-Toolkit** is a modular and extensible CLI-powered Python library for **controlled text generation** using various **decoding strategies** in LLMs. It helps researchers and developers **compare sampling methods**, run fine-grained generation experiments, and build better GenAI systems with prompt conditioning.

💡 **Use cases**:
- Compare generation quality across sampling techniques
- Integrate constrained decoding (e.g., JSON format output)
- Evaluate models under academic/enterprise conditions

---

## ✨ Features

✅ **Supports 12+ Generation Methods**  
Including both traditional and state-of-the-art techniques:

- `unconstrained` – default greedy sampling  
- `top_k`, `top_p` (nucleus), `min_p`, `typical`, `epsilon`, `eta`  
- `beam_search` – standard beam search  
- `cot_decoding` – Chain-of-Thought decoding  
- `constrained_json` – generate valid JSON outputs  
- `speculative` – fast decoding using draft models  
- `medusa` – fast and accurate parallel decoding using head ensembles

✅ **Chat Template Integration**  
Easily apply templates for Instruct-style models.

✅ **Memory Efficiency**  
Optimized with KV-caching and efficient float precision.

---

## ⚙️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/yourusername/GENAI-Sampling-Toolkit.git
cd GENAI-Sampling-Toolkit
pip install -r requirements.txt
