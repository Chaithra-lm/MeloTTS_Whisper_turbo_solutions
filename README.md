# 🚀 ROCm on Windows: Solutions for MeloTTS and Whisper Turbo

## 🔷 Problem Statement

Running advanced speech models on **AMD GPUs with Windows** presents several challenges due to limited native support.

### Target Models:
- 🎙️ [MeloTTS Japanese (VITS-based)](https://huggingface.co/myshell-ai/MeloTTS-Japanese)
- 🔊 [Whisper Large v3 Turbo](https://huggingface.co/openai/whisper-large-v3-turbo)

---

## ⚠️ ROCm on Windows: Not Natively Supported

As of **mid-2025**, **AMD ROCm** is:
- ❌ **Unavailable natively on Windows**
- ✅ **Supported only on Linux platforms**

---

## ✅ Practical Solutions for Windows Users (AMD GPUs)

### **1. ONNX Runtime with DirectML (💡 Recommended)**

Use `onnxruntime-directml` to run inference on AMD GPUs via **DirectX 12**.

#### 🔧 Setup:
```bash
pip install onnxruntime-directml

2. PyTorch-DirectML or TensorFlow-DirectML (Experimental)
Install Microsoft's custom builds for AMD GPU support:

PyTorch-DirectML GitHub

TensorFlow-DirectML GitHub

⚠️ Limitations:

Limited support for complex pipelines

Inconsistent performance with large models (e.g., VITS)

3. WSL2 + ROCm (Advanced/Experimental)
Run Linux via Windows Subsystem for Linux (WSL2) with ROCm preview support.

🔧 Requirements:
Windows 11

AMD RX 6000/7000 series GPU

Ubuntu 20.04+ in WSL2

⚠️ Limitations:
Not native Windows – runs under Linux kernel emulation

ROCm under WSL2 is still experimental

Memory bottlenecks observed during testing

📌 Model-Specific Notes
📍 MeloTTS:
Requires VITS pipeline (PyTorch-based)

Best run under native Linux with ROCm or CUDA (if NVIDIA)

📍 Whisper Turbo:
Proprietary OpenAI version

Not exportable to ONNX easily

Best used with native CUDA

DirectML backend inference possible with regular Whisper models

📝 Conclusion
✅ Best approach for AMD GPU on Windows:

Use ONNX Runtime + DirectML
until ROCm officially supports native Windows execution.

👩‍💻 Author
Chaithra Lokasara Mahadevaswamy
AI Tools Research Intern | M.S. in Artificial Intelligence
📧 chaithralm17@gmail.com
🔗 LinkedIn Profile : https://www.linkedin.com/in/chaithra-lokasara-mahadevaswamy-5bb076214/

