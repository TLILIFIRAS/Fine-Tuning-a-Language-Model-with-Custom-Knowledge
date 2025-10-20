# 🧠 Qwen2.5 3B Instruct – Fine-Tuning on Custom Data

Fine-tune the **Qwen2.5 3B Instruct** model (by Alibaba) on your own instruction–response dataset using **LoRA (Low-Rank Adaptation)** for efficient, low-resource training.

This notebook provides a full, ready-to-run pipeline for **domain adaptation, custom chatbot creation**, or **style-specific instruction tuning**.

---

## 🚀 Features

✅ Fine-tunes **Qwen2.5-3B-Instruct** (3B parameters) using **LoRA adapters**  
✅ **4-bit quantization (BitsAndBytes)** for efficient memory use  
✅ Works with **custom instruction–response datasets (JSON, CSV, or text)**  
✅ Easy to train on **Google Colab or local GPU**  
✅ Exports a **ready-to-use fine-tuned model** compatible with `transformers` pipeline  

---

## 📖 Dataset Format

Your dataset should contain **instruction–response pairs**, for example:

```json
[
  {
    "instruction": "Explain quantum computing simply",
    "output": "Quantum computing uses qubits that can represent 0 and 1 at the same time..."
  },
  {
    "instruction": "Write a short poem about AI",
    "output": "Machines that dream and think so bright..."
  }
]
```

## ⚙️ Training Configuration

| Parameter | Description | Default |
|------------|--------------|----------|
| `model_name` | Base model | `Qwen/Qwen2.5-3B-Instruct` |
| `r` | LoRA rank | `16` |
| `lora_alpha` | Scaling factor | `32` |
| `target_modules` | Layers adapted | `["q_proj", "v_proj"]` |
| `lora_dropout` | Dropout | `0.05` |
| `learning_rate` | Learning rate | `2e-4` |
| `epochs` | Training epochs | `3` |
| `batch_size` | Per device batch size | `1` |
| `max_length` | Token limit | `1024` |

# 🧱 References

- [Qwen2.5 Models – Alibaba Cloud](https://www.alibabacloud.com)
- [PEFT: Parameter Efficient Fine-Tuning](https://github.com/huggingface/peft)
- [Transformers Documentation](https://huggingface.co/docs/transformers/index)
- [BitsAndBytes](https://github.com/TimDettmers/bitsandbytes)
- [Unsloth](https://github.com/Unsloth-org)
