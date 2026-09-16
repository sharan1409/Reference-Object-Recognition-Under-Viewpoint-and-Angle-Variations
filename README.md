# Reference-Object-Recognition-Under-Viewpoint-and-Angle-Variations
An industrial computer vision system developed for the alfaTKG Hackathon to accurately locate metallic industrial components under challenging manufacturing conditions such as glare, scale changes, and perspective distortion. The solution combines classical computer vision techniques with an Adaptive Trust validation engine for robust object localization.

---

## 📌 Problem Statement

In manufacturing environments, accurately detecting metallic industrial parts is challenging due to:

- ✨ Specular reflections (glare) from shiny metal surfaces
- 📏 Scale variations caused by camera zoom and distance changes
- 📐 Perspective distortions from tilted viewpoints

These factors significantly reduce the reliability of traditional object recognition systems. :contentReference[oaicite:0]{index=0}

---

## 💡 Proposed Solution

A desktop-based computer vision application that uses an **Adaptive Trust Logic** to improve recognition accuracy.

### Key Innovations

- CLAHE-based glare reduction
- Rigid Affine Transformation to prevent bounding box distortion
- Adaptive scale validation
- Dynamic trust-based matching system
- False positive rejection mechanism

The system allows wider scaling for strong matches while applying stricter constraints to weak matches. :contentReference[oaicite:1]{index=1}

---

## 🚀 Features

- Real-time industrial object recognition
- Glare-resistant image processing
- Interactive ROI selection
- Adaptive validation engine
- Bounding box visualization
- Pose estimation
- Real-time logging
- GUI-based operation

---

## 🛠 Technology Stack

### Programming
- Python 3.x

### Computer Vision
- OpenCV (cv2)

### Algorithms
- SIFT
- CLAHE
- RANSAC
- AffinePartial2D

### GUI
- PyQt5

### Numerical Computing
- NumPy

:contentReference[oaicite:2]{index=2}

---

## ⚙️ System Workflow

```text
Reference Image
        │
Target Image
        │
        ▼
Preprocessing (Grayscale + CLAHE)
        │
        ▼
Feature Extraction (SIFT)
        │
        ▼
Feature Matching (BFMatcher + KNN)
        │
        ▼
Adaptive Trust Validation
        │
 ┌──────┴──────┐
 │             │
 ▼             ▼
Accept       Reject
 │
 ▼
Rigid Affine Refinement
 │
 ▼
Bounding Box + Pose Metrics
```

The workflow includes preprocessing, feature extraction, feature matching, adaptive validation, and pose estimation. :contentReference[oaicite:3]{index=3}

---

## 🔬 Implementation Details

### CLAHE Enhancement
Used CLAHE with a ClipLimit of 4.0 to reveal hidden keypoints on reflective metallic surfaces. :contentReference[oaicite:4]{index=4}

### Geometric Solver
Replaced Homography estimation with AffinePartial2D to eliminate shearing distortions and maintain geometric integrity. :contentReference[oaicite:5]{index=5}

### Adaptive RANSAC
The validation engine dynamically adjusts scale constraints based on inlier density:

- High Inliers (≥6): Scale range 0.5x – 3.0x
- Low Inliers (<6): Scale range 0.8x – 1.2x

:contentReference[oaicite:6]{index=6}

### Sub-Pixel Refinement
Applies a Least-Squares optimization step to improve bounding box precision. :contentReference[oaicite:7]{index=7}

---

## 📊 Results

### Achievements

- Reliable under zoom, tilt, and glare conditions
- Stable object localization
- Improved object-vs-noise discrimination

### Performance

- Processing speed below 200 ms per frame
- Sub-pixel localization accuracy

:contentReference[oaicite:8]{index=8}

---

## ⚠️ Limitations

- Performance decreases when objects are heavily occluded
- Motion blur affects feature extraction accuracy
- SIFT is computationally intensive

:contentReference[oaicite:9]{index=9}

---

## 🔮 Future Improvements

- RTSP camera integration
- USB camera support
- Object memory and tracking
- Lightweight AI-based pre-detection stage

:contentReference[oaicite:10]{index=10}
---

## 👥 Team MECTRON

- Dharun S
- Harish J H
- Sharan Raj G G (Teicho)

B.E. Mechatronics Engineering

---

## 🏆 Hackathon

Developed as part of the **alfaTKG AI-Driven Intelligent Industrial Application for Management and Manufacturing Solutions Hackathon 2025–26**. :contentReference[oaicite:12]{index=12}
