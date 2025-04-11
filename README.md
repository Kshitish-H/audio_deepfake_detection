# audio_deepfake_detection
# 🔊 Audio Deepfake Detection with AASIST 

This repository contains my submission for the Momenta take-home assessment focused on detecting AI-generated human speech. The project includes a comparative analysis of three promising detection models and a complete implementation of the **AASIST** model using the **ASVspoof 2019 PA (VSASV)** dataset.

---

## 🧠 Part 1: Research & Model Selection

### Selected Models:

1. **AASIST (Anti-Spoofing with Squeeze-Excitation and Self-Attention Networks)**
   - **Key Innovation**: Combines convolutional layers with self-attention modules to extract both local and global features.
   - **Performance**: Achieved SOTA on ASVspoof 2019 (EER ~0.39%)
   - **Why Promising**: Strong generalization and temporal modeling, suitable for real-time inference.
   - **Limitations**: Slightly heavy in memory for edge devices.

2. **RawNet2**
   - **Key Innovation**: End-to-end CNN on raw waveform input, removing the need for handcrafted features.
   - **Performance**: EER ~0.34% on ASVspoof 2019 LA.
   - **Why Promising**: No feature extraction overhead; works directly on waveforms.
   - **Limitations**: May struggle with noisy data in real-world conditions.

3. **LCNN (Light CNN)**
   - **Key Innovation**: CNN architecture using Max-Feature-Map activation to detect spoofing cues.
   - **Performance**: Competitive baseline on several spoofing challenges.
   - **Why Promising**: Lightweight and fast inference.
   - **Limitations**: Less robust to sophisticated AI-generated audio.

---

## 🛠️ Part 2: Implementation (AASIST)

- ✅ Implemented AASIST using PyTorch
- ✅ Dataset used: [ASVspoof 2019 PA (VSASV)](https://huggingface.co/datasets/pauls1601/ASVspoof2019_PA)
- ✅ Preprocessing with `torchaudio`, padded variable-length audio
- ✅ Light training on a subset of the dataset due to time constraints


### Folder Structure:
├── AASIST_VSASV_DeepfakeDetection.ipynb # Main notebook 
├── requirements.txt # Dependencies 
├── data/ # Dataset loader logic 
└── utils/ # Model & utility functions

---

## 📈 Part 3: Documentation & Analysis

### Why AASIST?
AASIST's hybrid design of convolution + attention makes it suitable for detecting both low-level and high-level spoofing artifacts, making it ideal for real-world AI-generated speech detection.

### Key Results:
- Model trained successfully on the dataset subset.
- Demonstrated reasonable generalization despite limited training.
- Padded input handling ensured stable training with variable-length audio.

### Challenges & Assumptions:
- Some `.flac` files were corrupt or unreadable — handled with exception catching.
- Assumed binary classification between bonafide and spoofed audio.
- Simplified training pipeline due to compute/time limits.

---

## 💡 Reflection

1. **Biggest Challenge**: Handling corrupted audio files and variable-length inputs for batching.
2. **Real-World Performance**: Expected to work well with clean audio; may need noise-robust training for field deployment.
3. **Improvement Areas**:
   - Use full dataset and hyperparameter tuning
   - Add audio augmentation
   - Try mixed-precision training for efficiency
4. **Production Deployment**:
   - Convert model to ONNX for low-latency inference
   - Deploy on stream-based audio processing service with thresholding logic

---

## 🚀 Setup Instructions

### Step 1: Clone the repo
bash:
git clone https://github.com/Kshitish-H/audio_deepfake_detection.git
cd audio_deepfake_detection

### Step 2: Install dependencies
bash:
conda create -n aasist_env python=3.9
conda activate aasist_env
pip install -r requirements.txt

### Step 3: Download Dataset
You can download the VSASV dataset from Hugging Face and place it in the correct directory:
./PA/PA/ASVspoof2019_PA_train/flac/

## 📬 Contact
For any questions, feel free to reach out via GitHub issues or email.

Author: Kshitish Handa
