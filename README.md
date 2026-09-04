# 🦺 PPE Detection - Personal Protective Equipment Detection System

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-Ultralytics-000000.svg)](https://github.com/ultralytics/yolov5)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-5C3EE8.svg)](https://opencv.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

A real-time Personal Protective Equipment (**PPE**) detection system powered by Deep Learning (YOLOv5) and Computer Vision. This project automates workplace safety monitoring in construction sites, factories, and manufacturing plants to detect and alert non-compliance with safety regulations.

---

## 🎥 Video Demo

<p align="center">
  <img src="https://raw.githubusercontent.com/sonlechiht/PPE-Detection/main/data/ppe-test.gif" alt="PPE Detection Demo GIF" width="850">
</p>

> 📹 **Direct GIF File:** [`data/ppe-test.gif`](https://github.com/sonlechiht/PPE-Detection/blob/main/data/ppe-test.gif)

---

## ✨ Key Features

- 🦺 **Multi-Class PPE Detection**:
  - Hardhat / Helmet (`Hardhat`, `NO-Hardhat`)
  - High-visibility safety vests (`Safety Vest`, `NO-Safety Vest`)
  - Protective masks (`Mask`, `NO-Mask`)
  - Gloves and safety boots (`Gloves`, `Boots`)
- ⚠️ **Safety Violation Alerts**:
  - Real-time detection of non-compliant personnel (`NO-Hardhat`, `NO-Safety Vest`).
  - Color-coded bounding boxes (Green for compliance, Red for violation).
- ⚡ **Real-Time Processing**:
  - Optimized inference pipeline for live webcam streams, recorded videos, and CCTV camera feeds.
- 📊 **Object Tracking**:
  - Integrated ByteTrack / BoT-SORT algorithms to maintain worker identity tracking across frames.

---

## 🛠️ Installation

### 1. Prerequisites
- Python >= 3.8
- PyTorch (CUDA supported for GPU acceleration)

### 2. Clone Repository & Install Dependencies

```bash
# Clone the repository
git clone [https://github.com/sonlechiht/PPE-Detection.git](https://github.com/sonlechiht/PPE-Detection.git)
cd PPE-Detection

# Create a virtual environment (Recommended)
python -m venv venv
source venv/bin/activate  # On Linux/macOS
# On Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt
