# 🚀 IITGN SRIP Selection Task: Solar Panel Object Detection  

This project focuses on detecting **solar panels in aerial images** using **YOLOv8**. It involves **data exploration, model training, IoU computation, AP calculation, and performance evaluation**.  

## 📌 **Overview**
- **Dataset**: Aerial images (416x416) with MS-COCO formatted annotations.
- **Model**: Trained **YOLOv8** for object detection.
- **Evaluation**: Used **mAP50, IoU, Precision-Recall, F1 Score**.
- **Implementation**:
  - Converted YOLO labels to bounding boxes.
  - Computed **IoU using shapely** and validated with supervision library.
  - Implemented **Average Precision (AP) using VOC, COCO, and AUC methods**.
  - Split dataset into **80% train, 10% validation, 10% test**.
  - Trained YOLOv8 and validated model performance.

---

## 📌 **Results**
| **Metric**        | **Value**  |
| **Total Solar Panel Instances** | `29625` |
| **Mean IoU Score** | `0.8491` |
| **mAP50 (YOLOv8 Model)** | `0.7491` |
| **Area Mean(m2)** | `191.5178278649789` |
| **Std Dev of Area (m²)** | `1.0571000000000002` |
|


---

## 📌 **How to Run**
```bash
pip install ultralytics shapely supervision torchmetrics scikit-learn
python train.py --epochs 50 --batch 16 --model yolov8s.pt --data dataset.yaml
python evaluate.py --model best.pt --data dataset.yaml
