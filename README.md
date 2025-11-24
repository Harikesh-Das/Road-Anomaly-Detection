#  Road Pothole Detection using YOLOv8

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-00FFFF?style=for-the-badge&logo=yolo&logoColor=black)](https://github.com/ultralytics/ultralytics)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)

##  Overview

This project presents a **deep learning-based system** for detecting road potholes using **YOLOv8 instance segmentation**. It is designed to help with intelligent transportation systems by detecting road surface anomalies in real-time from video input, contributing to safer roads and efficient maintenance planning.

---

##  Features

-  **Real-time pothole detection** using YOLOv8 instance segmentation
-  Handles both **images** and **video streams**
-  Uses **custom-trained weights** on pothole dataset
-  Visualizes predictions with **bounding boxes** and **segmentation masks**
-  **Scalable** and can be integrated into smart surveillance systems
-  High accuracy and fast inference speed
-  Suitable for deployment in autonomous vehicles and road monitoring systems

---

##  Tech Stack

| Component           | Technology                          |
|---------------------|-------------------------------------|
| **Language**        | Python 3.11                         |
| **Deep Learning**   | YOLOv8 (Ultralytics), PyTorch       |
| **Computer Vision** | OpenCV                              |
| **Data Processing** | NumPy, Pandas                       |
| **Visualization**   | Matplotlib                          |

---

##  Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.11 or higher
- CUDA-compatible GPU (recommended for faster inference)
- Git

---

##  Installation

### 1. Clone the Repository or Dowload Zip

```bash
git clone https://github.com/Harikesh-Das/pothole-detection-yolov8.git
cd pothole-detection-yolov8
```

### 2. Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt** should include:
```
ultralytics
opencv-python
torch
torchvision
numpy
pandas
matplotlib
```

### 4. Download Pre-trained Weights

Place your custom-trained YOLOv8 weights file in the `weights/` directory:
```
weights/
└── best.pt  # Your trained model weights
```

---

## 💻 Usage

### Detect Potholes in Images

```bash
python detect.py --source path/to/image.jpg --weights weights/best.pt
```

### Detect Potholes in Videos

```bash
python detect.py --source path/to/video.mp4 --weights weights/best.pt
```

### Real-time Detection from Webcam

```bash
python detect.py --source 0 --weights weights/best.pt
```

### Additional Arguments

```bash
python detect.py \
  --source path/to/input \
  --weights weights/best.pt \
  --conf 0.5 \              # Confidence threshold
  --iou 0.45 \              # IoU threshold for NMS
  --save-txt \              # Save results to txt
  --save-conf               # Save confidence scores
```
##  Training Your Own Model

### 1. Prepare Dataset

Organize your dataset in YOLO format:
```
dataset/
├── images/
│   ├── train/
│   └── val/
└── labels/
    ├── train/
    └── val/
```

### 2. Create Data Configuration

Create `data.yaml`:
```yaml
path: ./dataset
train: images/train
val: images/val

nc: 1  # number of classes
names: ['pothole']
```

### 3. Train the Model

```bash
python train.py --data data.yaml --epochs 100 --img 640 --batch 16
```

---

##  Model Performance

| Metric       | Value  |
|--------------|--------|
| **mAP@0.5**  | 92.3%  |
| **Precision**| 89.7%  |
| **Recall**   | 87.5%  |
| **FPS**      | 45     |

*Note: Update these metrics based on your actual model performance*

---

##  Contributing

If you would like to contiribute 😁, Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📧 Contact

**Project Link:** [https://github.com/your-username/pothole-detection-yolov8](https://github.com/your-username/pothole-detection-yolov8)

**For questions or collaborations:** your.email@example.com

---

<div align="center">
  
### Thanks for your contribuition

</div>
