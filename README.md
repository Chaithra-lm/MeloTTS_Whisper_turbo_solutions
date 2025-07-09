🚀 ROCm on Windows: Solutions for MeloTTS and Whisper Turbo
🔷 Problem
Running the following models on AMD GPUs with Windows:

MeloTTS Japanese: https://huggingface.co/myshell-ai/MeloTTS-Japanese

Whisper Turbo: https://huggingface.co/openai/whisper-large-v3-turbo

⚠️ ROCm Native Support on Windows
❌ Not available.
ROCm is only supported on Linux. There is no native ROCm support for Windows as of mid-2025.

✅ Three Practical Solutions
1. DirectML Backend (Recommended)
Use ONNX Runtime with DirectML execution provider.

Supports inference on AMD GPUs via DirectX 12.

🔹 Steps:

bash
Copy
Edit
pip install onnxruntime-directml
Convert models (Whisper Turbo, MeloTTS) to ONNX format if needed.

Load and run inference using DirectML backend.

2. PyTorch-DirectML or TensorFlow-DirectML
Install Microsoft’s DirectML builds for PyTorch or TensorFlow.

Enables AMD GPU acceleration on Windows.

🔗 PyTorch-DirectML GitHub
🔗 TensorFlow-DirectML GitHub

3. WSL2 + ROCm (Experimental)
Install WSL2 (Windows Subsystem for Linux v2) with Ubuntu.

AMD provides ROCm preview support for WSL2 on select GPUs (RX 6000, 7000 series) with Windows 11.

🔹 Limitations:

Not native Windows support (runs under Linux kernel in WSL2).

Performance, compatibility, and driver issues observed during testing.

For MeloTTS and Whisper Turbo:

MeloTTS requires full VITS-based pipeline setup within Linux under WSL2.

Whisper Turbo (OpenAI variant) often runs better using direct PyTorch CUDA under Linux rather than WSL2 due to memory bottlenecks.

📝 Conclusion
✔️ Best approach on Windows:
Use ONNX Runtime + DirectML for AMD GPU inference pipelines until native ROCm support is released.

🙌 Author
Chaithra Lokasara Mahadevaswamy
AI Tools Research Intern | M.S. Artificial Intelligence
📧 chaithralm17@gmail.com
🔗 LinkedIn : https://www.linkedin.com/in/chaithra-lokasara-mahadevaswamy-5bb076214/
