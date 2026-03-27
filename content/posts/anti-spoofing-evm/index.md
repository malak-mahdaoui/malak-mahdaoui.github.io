---
title: "Advanced Facial Anti-Spoofing using EVM"
date: 2024-03-27
description: "Research Project: Detecting pulse and micro-motions using Eulerian Video Magnification to prevent facial spoofing."
menu:
  sidebar:
    name: Anti-Spoofing (In Progress)
    identifier: anti-spoofing-evm
    weight: 30
author:
  name: Malak Ines MAHDAOUI
  image: images/afficherPhoto.jpeg
---

> **Note:** This project is currently in the **Research & Development** phase as part of my specialization in Computer Vision.

### Project Overview
Facial recognition systems are vulnerable to "spoofing" (photos or video replays). This project develops an advanced anti-spoofing pipeline that detects the **live pulse** and **micro-motions** of a human face—features that are nearly impossible to replicate with a static image or a screen.

#### **Core Technology: Eulerian Video Magnification (EVM)**
I am implementing **EVM** to amplify subtle temporal variations in video sequences. By magnifying these micro-motions (like blood flow in the skin), the system can distinguish between a real person and a spoofing attempt.

![Facial Micro-motion Analysis](evm-analysis.png)
*(Illustration of temporal filtering for pulse detection)*

### Current Pipeline (In Progress)
1. **Face Detection:** Using **MTCNN** to locate and crop faces in real-time.
2. **Temporal Filtering:** Applying ideal bandpass filters to isolate frequencies corresponding to the human heart rate (0.8 - 3 Hz).
3. **Motion Magnification:** Using spatial decomposition to amplify the isolated signal without adding significant noise.
4. **Classification:** Training a model to differentiate the "liveness" signal from video noise or static backgrounds.

### Technical Challenges
- **Real-time Performance:** Optimizing the EVM pyramid decomposition for live video streams.
- **Robustness:** Ensuring the system works under different lighting conditions and handles natural head movements.

### Technical Stack
- **Frameworks:** OpenCV, PyTorch, NumPy
- **Algorithms:** MTCNN (Detection), Eulerian Video Magnification (Motion), LSTM (Temporal Analysis)
- **Environment:** Python 3.10+, GPU acceleration for pyramid processing.