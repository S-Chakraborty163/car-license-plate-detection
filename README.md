# 🚗 Car License Plate Detection System

<p align="center">
  <img src="https://img.shields.io/badge/Model-YOLOv8-blue" alt="Model">
  <img src="https://img.shields.io/badge/Framework-PyTorch-red" alt="Framework">
  <img src="https://img.shields.io/badge/Task-Object%20Detection-green" alt="Task">
</p>

## 📊 Project Overview
This project implements a sophisticated object detection system specifically designed for identifying and localizing vehicle license plates. Utilizing the cutting-edge **YOLOv8** architecture, the system achieves exceptional accuracy and real-time efficiency.

### 🛠️ Technical Stack
* **Detection Model:** YOLOv8 (Ultralytics)
* **Task:** Single-class object detection (License Plates)
* **Framework:** PyTorch with CUDA acceleration
* **Deployment:** Streamlit

---

## 📈 Performance Metrics

### Training Results (Final Epoch)
| Metric | Value | Description |
| :--- | :--- | :--- |
| **Epoch** | 120/120 | Training completion |
| **GPU Memory** | 4.02G | VRAM utilization |
| **Box Loss** | 0.8123 | Bounding box regression loss |
| **Class Loss** | 0.449 | Classification loss |
| **DFL Loss** | 0.9348 | Distribution Focal Loss |

### Validation Performance
| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Precision (P)** | 0.912 | Very high - minimal false positives |
| **Recall (R)** | 0.864 | High - detects most license plates |
| **mAP @50** | 0.918 | Excellent Mean Average Precision |
| **mAP @50-95** | 0.532 | Consistent performance across IoU thresholds |

> **Key Insight:** The model achieves **91.2% precision** and **91.8% mAP@50**, indicating excellent detection accuracy suitable for real-world automated parking or toll systems.

---

## 🚀 Deployment
The system is deployed via a **Streamlit** web interface, allowing users to upload videos/images and receive real-time detection overlays.

🏗️ System Architecture:

<img width="496" height="488" alt="Screenshot 2026-02-07 123108" src="https://github.com/user-attachments/assets/bc578ab9-51a7-49e6-aad3-a97f922f049e" />

## 📋 Pipeline Breakdown
### 1. Data Collection & Preparation
* **XML Annotation Parsing:** Automated conversion of Pascal VOC formats into structured YOLO labels.
* **Bounding Box Extraction:** Precise coordinate normalization $(x_{center}, y_{center}, width, height)$ for consistent scaling.
* **Image Preprocessing:** Grayscale optimization and resizing to $640 \times 640$ to maintain high-speed inference.

### 2. Dataset Strategy
The dataset was strategically partitioned to ensure model generalization and prevent overfitting:

**Total Images:** 433  
Dataset Structure

├── 📁 Training   (80%) ➔ 345 Images

├── 📁 Validation (10%) ➔ 44 Images

└── 📁 Testing    (10%) ➔ 44 Images

3. Model Development:
   
--> Architecture: YOLOv8 Implementation — the current gold standard for real-time object detection.

--> Hardware Acceleration: Leveraged 2x NVIDIA Tesla T4 GPUs using PyTorch Distributed Data Parallel (DDP) for faster convergence.

5. Evaluation & Deployment:
   
--> Comprehensive Metrics: Strict monitoring of Precision, Recall, and mAP calculations.

--> Visual Validation: Automated bounding box verification tools to cross-reference ground truth vs. predicted detections.

--> Deployment: Integrated into a Streamlit dashboard for end-user interaction.

<img width="1233" height="701" alt="image" src="https://github.com/user-attachments/assets/f55fbcfe-5750-4540-b3a6-9928610c9986" />


