Base_model: TinyLlama/TinyLlama-1.1B-Chat-v1.0
library_name: peft
model_name: tinyllama_fake_app_detector
tags:
- lora
- sft
- transformers
- trl
pipeline_tag: text-generation
---

# 🧠 TinyLlama Fake App Detector

A lightweight LLM-based system to detect **fake or malicious app descriptions** using parameter-efficient fine-tuning.

---

## 🚀 Overview

This project fine-tunes **TinyLlama-1.1B-Chat** using **Supervised Fine-Tuning (SFT)** and **LoRA (PEFT)** to classify whether an app description is **legitimate or fake**.

Developed as part of the **CBIT Hackathon**, the focus was to build an efficient and scalable solution using limited computational resources.

---

## 🛠️ Tech Stack

- TinyLlama (1.1B Chat Model)
- Hugging Face Transformers
- PEFT (LoRA)
- TRL (Transformer Reinforcement Learning)
- PyTorch

---

## ⚙️ Key Features

- Fine-tuned LLM for detecting fake app descriptions  
- Parameter-efficient training using LoRA  
- Lightweight and fast inference  
- Prompt-based classification approach  
- Designed for real-world NLP security use cases  

---

## 📂 Project Structure
tinyllama_fake_app_detector/
│
├── README.md
├── adapter_config.json
├── adapter_model.safetensors
├── tokenizer.json
├── tokenizer_config.json
├── chat_template.jinja
│
└── checkpoint-200/
├── adapter_model.safetensors
├── optimizer.pt
├── scheduler.pt
├── trainer_state.json
├── training_args.bin


---

## 🧪 Model Details

- Base Model: TinyLlama-1.1B-Chat-v1.0  
- Fine-Tuning: Supervised Fine-Tuning (SFT)  
- Technique: LoRA (Low-Rank Adaptation)  
- Framework: TRL + Hugging Face Transformers  

---

## ▶️ Usage (Inference Example)
python
from transformers import pipeline

generator = pipeline(
    "text-generation",
    model="your-username/tinyllama_fake_app_detector",
    device="cpu"
)

prompt = "This app gives you free money instantly with no verification."
output = generator(prompt, max_new_tokens=100)

print(output[0]["generated_text"])

📊 Use Cases
Fake app detection
App store security
Scam detection systems
NLP-based content filtering

⚠️ Limitations
Performance depends on dataset quality
May not generalize to unseen scam patterns
Lightweight model may have lower accuracy compared to larger LLMs
🔮 Future Improvements
Improve dataset quality and size
Add evaluation metrics (accuracy, F1-score)
Deploy as a web application (Flask/Streamlit)
Integrate real-time app store data

📚 Citation
If you use this project, consider citing:

@misc{tinyllama_fake_app_detector,
  title={TinyLlama Fake App Detector},
  author={Your Name},
  year={2026},
  note={Fine-tuned TinyLlama using LoRA and TRL}
}

🙌 Acknowledgements
TinyLlama Team
Hugging Face
TRL Library Contributors

👨‍💻 Author
M Sri Venkat Sai
Developed during CBIT Hackathon
