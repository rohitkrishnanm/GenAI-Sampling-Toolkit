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
'''bash

python generate.py \
  --model <model_name> \
  --prompt "Your input prompt here" \
  --method <sampling_method> \
  --temperature 0.7 \
  --max_new_tokens 200 \
  --hf-token <your_huggingface_token> \
  --dtype float16


🔍 Parameters
Argument	Description
--model	Hugging Face model name or path
--prompt	Text input prompt
--prompt_file	Alternative to --prompt
--temperature	Sampling temperature (default: 1.0)
--method	Sampling method (top_k, top_p, beam_search, etc.)
--max_new_tokens	Number of new tokens to generate
--hf-token	Hugging Face token
--dtype	Precision: bfloat16, float16, float32
--seed	(Optional) Seed for reproducibility

🔧 Method-Specific Arguments:
--top_k, --top_p, --min_p, --epsilon

--beam_width

--typical_p_mass

--json_schema (for constrained_json)

--draft-model (for speculative)

--medusa-model-heads (for medusa)

--lookahead (for speculative)

💡 Examples
📌 Top-k Sampling
bash
Copy
Edit
python generate.py --model meta-llama/Llama-3.1-8B-Instruct \
  --prompt "Tell me a story" --method top_k --top_k 50 --temperature 0.7
📌 Nucleus Sampling (top-p)
bash
Copy
Edit
python generate.py --prompt "Write a poem" \
  --method top_p --top_p 0.9 --temperature 0.8
📌 Speculative Decoding
bash
Copy
Edit
python generate.py --prompt "Explain quantum physics" \
  --method speculative --draft-model meta-llama/Llama-3.2-1B-Instruct --lookahead 4
📌 Medusa Decoding
bash
Copy
Edit
python generate.py --prompt "Write merge sort code" \
  --method medusa --medusa-model-heads ./medusa_heads
📁 Project Structure
css
Copy
Edit
GENAI-Sampling-Toolkit/
├── generate.py                  # CLI for all methods
├── requirements.txt
├── README.md
├── LICENSE
└── src/
    ├── unconstrained.py
    ├── top_k.py
    ├── top_p.py
    ├── min_p.py
    ├── typical.py
    ├── epsilon.py
    ├── eta.py
    ├── beam_search.py
    ├── cot_decoding.py
    ├── constrained_json_decoding.py
    ├── speculative.py
    ├── medusa.py
    ├── utils.py
🙌 Acknowledgements
Medusa Decoding

vLLM Project

Jsonformer

HuggingFace Transformers

🛡️ License
This project is licensed under the MIT License
Feel free to use, distribute, and modify it with attribution.

👤 Author
Rohit Krishnan
📍 Business & Technology Strategist
🎓 AI, Cybersecurity & Data Science Trainer
🔗 Website • LinkedIn • Instagram
