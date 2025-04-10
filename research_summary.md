# 🔍 Research Summary

This document outlines three promising approaches to audio deepfake detection, especially suitable for detecting AI-generated human speech in real-time conversations. These were selected after reviewing the [Audio Deepfake Detection GitHub repository](https://github.com/media-sec-lab/Audio-Deepfake-Detection).

---

## 1. **AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Networks**

- **Key Innovation**:
  - Introduces a graph attention-based model that integrates both spectral and temporal information via learnable edge weights.
  - Specifically designed for anti-spoofing tasks, using spectrogram patches and self-attention mechanisms to detect anomalies.

- **Performance**:
  - Achieved state-of-the-art results on ASVspoof2019 dataset.
  - EER (Equal Error Rate): ~1.08% on LA (Logical Access) subset.

- **Why It’s Promising**:
  - Tailored for real-time deepfake detection.
  - Suitable for conversations and audio clips of varying lengths.
  - Efficient and lightweight, suitable for deployment.

- **Limitations**:
  - Requires high-quality spectrograms.
  - Sensitive to noise and low-quality audio.

---

## 2. **RawNet2: End-to-End Anti-Spoofing with Raw Waveform Input**

- **Key Innovation**:
  - End-to-end model that takes raw audio waveforms as input.
  - No need for feature engineering like MFCCs or spectrograms.
  - Utilizes residual blocks and GRU layers for temporal modeling.

- **Performance**:
  - ASVspoof2019 LA EER: ~1.77% (without data augmentation).

- **Why It’s Promising**:
  - Simple pipeline (raw audio → prediction).
  - Robust across multiple spoofing techniques.
  - Lower latency for inference.

- **Limitations**:
  - May underperform with short-duration clips.
  - Requires normalization and careful preprocessing.

---

## 3. **GraphSpoofNet: Graph Neural Network for Deepfake Detection**

- **Key Innovation**:
  - Graph-based modeling of spectrogram patches.
  - Treats speech as a graph structure and models transitions in time-frequency space.

- **Performance**:
  - Strong performance on ASVspoof2019 dataset.
  - EER: ~1.4% (when combined with data augmentation).

- **Why It’s Promising**:
  - Better representation of speech anomalies.
  - Potential for generalization across attack types.

- **Limitations**:
  - More computationally intensive.
  - May require graph construction overhead.

---

## ✅ Selected Approach for Implementation: **AASIST**

AASIST was chosen due to its superior balance of accuracy, efficiency, and real-time readiness. The model architecture is well-suited for short conversational clips and can generalize across spoofing types. It’s also one of the most cited and production-viable models from recent research.

---

## Dataset Used for Implementation: **ASVspoof2019 PA Subset**

- Public dataset focused on logical access attacks (text-to-speech and voice conversion).
- Real and fake human speech samples.
- Balanced and labeled for spoofing detection tasks.

This dataset is representative of real-world AI-generated speech scenarios and is widely used in benchmarking deepfake detection models.

