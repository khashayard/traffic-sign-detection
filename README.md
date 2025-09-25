# 🚦 Traffic Sign Detection with YOLO  

This repository contains a deep learning project for **real-time traffic sign detection and recognition** using the YOLO family of models.  
The model is trained on a custom dataset of road signs and supports deployment on **edge devices** via ONNX export.  

---

## 📂 Dataset
- **Source:** Custom dataset (exported from Roboflow, ~5K images)  
- **Classes (15):**  
  🟢 Green Light  
  🔴 Red Light  
  🚫 Stop  
  🚗 Speed Limit 10 → 120  
- **Split:**  
  - Train: 3530 images  
  - Validation: 801 images  
  - Test: 638 images  
- **Format:** YOLO annotation format (`.txt` files with normalized bounding boxes)  
- **Data augmentation:**  
  - Random flips, rotations, scaling  
  - HSV color augmentation  
  - Mosaic augmentation  

---

## 🧠 Model Architecture
- **Backbone:** YOLOv11s (pretrained on COCO)  
- **Detection Head:** 3 output layers for multi-scale detection  
- **Input size:** 832 × 832  
- **Training setup:**  
  - Epochs: 100  
  - Batch size: auto (`batch=-1`)  
  - Optimizer: SGD (cosine LR scheduler)  
  - Device: NVIDIA A100 GPU (Colab Pro)  

---

## 📊 Results
- **Validation mAP50:** ~97.5%  
- **Validation mAP50-95:** ~85.6%  
- **Precision:** ~96%  
- **Recall:** ~94%  
- **Inference speed:** ~8 ms/image (PyTorch, A100 GPU)  

Evaluation was performed on the reserved validation and test sets.  
Sample predictions include **speed limit signs, traffic lights, and stop signs**.  

---

## ▶️ Usage

### 1️⃣ Clone Repository
```bash
git clone https://github.com/khashayard/traffic-sign-detection.git
cd traffic-sign-detection

