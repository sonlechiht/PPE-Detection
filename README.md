# 🦺 PPE Detection - Personal Protective Equipment Detection System

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-Ultralytics-000000.svg)](https://github.com/ultralytics/ultralytics)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-5C3EE8.svg)](https://opencv.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

A real-time Personal Protective Equipment (**PPE**) detection system powered by Deep Learning (YOLOv5) and Computer Vision [cite: 1.1.1, 1.1.3]. This project automates workplace safety monitoring in construction sites, factories, and manufacturing plants to detect and alert non-compliance with safety regulations [cite: 1.1.3, 1.2.5].

---

## 🎥 Video Demo

### 🎬 Demo Video
You can check out the test demo video stored directly in the repository:

https://github.com/user-attachments/assets/5377f722-e3d8-4a11-b016-52c71f98bc19

> 📹 **Direct File Link:** [`data/ppe-test.gif`](https://github.com/sonlechiht/PPE-Detection/blob/main/data/ppe-test.gif)

---

## ✨ Key Features

- 🦺 **Multi-Class PPE Detection**:
  - Hardhat / Helmet (`Hardhat`, `NO-Hardhat`) [cite: 1.1.3, 1.2.2]
  - High-visibility safety vests (`Safety Vest`, `NO-Safety Vest`) [cite: 1.1.3, 1.2.2]
  - Protective masks (`Mask`, `NO-Mask`) [cite: 1.1.1, 1.2.2]
  - Gloves and safety boots (`Gloves`, `Boots`) [cite: 1.1.3, 1.2.5]
- ⚠️ **Safety Violation Alerts**:
  - Real-time detection of non-compliant personnel (`NO-Hardhat`, `NO-Safety Vest`) [cite: 1.2.2].
  - Color-coded bounding boxes (Green for compliance, Red for violation).
- ⚡ **Real-Time Processing**:
  - Optimized inference pipeline for live webcam streams, recorded videos, and CCTV camera feeds [cite: 1.1.5, 1.2.5].
- 📊 **Object Tracking**:
  - Integrated ByteTrack / BoT-SORT algorithms to maintain worker identity tracking across frames.

---

## 🛠️ Installation

### 1. Prerequisites
- Python >= 3.8 [cite: 1.1.1]
- PyTorch (CUDA supported for GPU acceleration) [cite: 1.1.3, 1.1.5]

### 2. Clone Repository & Install Dependencies

```bash
# Clone the repository
git clone https://github.com/sonlechiht/PPE-Detection.git
cd PPE-Detection

# Create a virtual environment (Recommended)
python -m venv venv
source venv/bin/activate  # On Linux/macOS
# On Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt
```

---

## 🚀 Usage

### 1. Live Stream Detection (Webcam)
```bash
python detect.py --source 0 --weights models/best.pt --conf 0.5
```

### 2. Video File Detection
```bash
python detect.py --source path/to/your_video.mp4 --weights models/best.pt --save
```

### 3. Single Image Detection
```bash
python detect.py --source path/to/image.jpg --weights models/best.pt
```

---

## 🎯 Model Training

To train the model on a custom dataset:

1. Prepare your dataset in **YOLO format** (`images/` and `labels/`) [cite: 1.2.2].
2. Update the `data/data.yaml` configuration file [cite: 1.2.2]:
   ```yaml
   train: ../dataset/train/images
   val: ../dataset/valid/images
   nc: 5
   names: ['Hardhat', 'NO-Hardhat', 'Safety Vest', 'NO-Safety Vest', 'Person']
   ```
3. Run the training command:
   ```bash
   yolo detect train data=data/data.yaml model=yolov8n.pt epochs=50 imgsz=640
   ```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/NewFeature`)
3. Commit your Changes (`git commit -m 'Add new feature'`)
4. Push to the Branch (`git push origin feature/NewFeature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 👤 Author

- **Son Le** - [@sonlechiht](https://github.com/sonlechiht)
- Email: sonlechiht@gmail.com
