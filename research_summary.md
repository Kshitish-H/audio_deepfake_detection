# 🔍 Research Summary: Audio Deepfake Detection

## 1. **AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Network**

- **Technical Innovation**:  
  Introduces a spectro-temporal graph attention network (STGAT) that models both time and frequency dependencies in audio signals, enhancing detection of subtle spoofing artifacts.

- **Performance Metrics**:  
  - Achieved EER (Equal Error Rate) of **0.81%** on ASVspoof 2019 LA evaluation set.  
  - Strong generalization across spoofing types.

- **Why It's Promising**:  
  - Excellent performance across both replay and synthetic attacks  
  - Designed specifically for **generalization to unseen attacks**  
  - Works well with spectrogram-based preprocessing, suitable for real-world deployment with GPU acceleration

- **Limitations**:  
  - May be computationally intensive for real-time mobile or edge inference  
  - Requires pre-processing (e.g., spectrogram generation)

---

## 2. **RawNet2: End-to-End Deep Neural Network for Raw Audio Anti-Spoofing**

- **Technical Innovation**:  
  Operates directly on raw waveform input, eliminating handcrafted feature extraction. Uses residual CNNs followed by GRU layers for temporal modeling.

- **Performance Metrics**:  
  - Achieved **1.08% EER** on ASVspoof 2019 LA dataset  
  - Strong baseline in many benchmarks

- **Why It's Promising**:  
  - Simpler preprocessing pipeline  
  - Efficient for inference with optimized frameworks  
  - Captures raw audio patterns often missed by spectrogram-based systems

- **Limitations**:  
  - Sensitive to background noise  
  - May require careful training with large datasets to generalize well

---

## 3. **LTAS: Long-Term Average Spectrum Features + CNN Classifier**

- **Technical Innovation**:  
  Uses long-term average spectral features derived from FFT over long windows. Combines them with CNNs for classification of spoofed vs genuine audio.

- **Performance Metrics**:  
  - Reported good accuracy on Fake or Real datasets  
  - Lightweight model (~1–2% EER on in-domain datasets)

- **Why It's Promising**:  
  - Very low computational cost  
  - Suitable for **real-time applications**  
  - Works well for detecting obvious patterns in synthetic voices

- **Limitations**:  
  - May struggle with sophisticated attacks (e.g., voice cloning with emotion or prosody)  
  - Less accurate in cross-dataset evaluations

