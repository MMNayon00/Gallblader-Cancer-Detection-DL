# 🦠 Gallbladder Cancer Detection from Ultrasound Images Using Deep Learning

This repository contains the code and models for detecting **Gallbladder Cancer (GBC)** from **ultrasound images** using multiple deep learning architectures and ensemble methods.  
The goal of this project is to support **early and accurate detection** of GBC, thereby assisting in clinical decision-making.

---

## 📌 Overview

Gallbladder cancer is a highly aggressive disease, often diagnosed at a late stage.  
This project implements a **multi-model deep learning ensemble** approach to classify gallbladder conditions from ultrasound images.

### Key Features
- Individual CNN models with **transfer learning**
- **Normal** and **Weighted Ensemble Learning** techniques
- Evaluation using **Accuracy**, **F1-score**, **ROC-AUC**, and **Confusion Matrices**
- Visualization of **training/validation performance** and **ROC curves**

---

## 📁 Dataset Description

**Dataset Used:** Gallbladder Cancer Ultrasound Dataset  
**Total Images:** 2,294  
**Classes:** `Normal`, `Benign`, `Malignant`, `Gallstone`, `Abnormal`

| Split | No. of Images |
|-------|----------------|
| Training | 1,605 |
| Validation | 346 |
| Test | 343 |

*(Train/Validation/Test splits were created manually and randomly from the dataset.)*

---

## 🧹 Data Preprocessing

- Resize all images to a consistent size  
- Normalize pixel values  
- Convert grayscale to RGB (3 channels)  
- **Data Augmentation Techniques:**
  - Horizontal & vertical flips  
  - Random rotation  
  - Zoom  
  - Color Jitter (random brightness/contrast adjustments)

---

## 🧠 Methodology

### Training Details
- **Loss Function:** CrossEntropyLoss  
- **Optimizer:** Adam  
- **Learning Rate Scheduler:** StepLR  
- **Transfer Learning:** Pre-trained weights  
- **Batch Size:** 32  
- **Epochs:** 30  
- **Early Stopping:** Patience = 5 epochs  

### Models Used
- Pre-trained CNN architectures: **ResNet**, **EfficientNet**, **MobileNet**, **DenseNet**, **ShuffleNet**, etc.
- **Normal Ensemble:** Equal averaging of model probabilities  
- **Weighted Ensemble:** Probabilities weighted according to top-6 individual model accuracies  

---

## 📈 Evaluation Metrics

- Classification Report  
- Training/Validation loss and accuracy plots  
- Confusion Matrices  
- ROC Curve and AUC Score  

---

## 📊 Results

A total of **17 models** were evaluated in this study.  
Individual model accuracies ranged from **58.6% to 88.63%**.

### 🔹 Model Performance Summary (Test Accuracy)

| Model | Test Accuracy (%) |
|-------|--------------------|
| **Weighted Ensemble** | **89.21** |
| Normal Ensemble | 88.92 |
| EfficientNetB2 | 88.63 |
| EfficientNetB1 | 87.76 |
| EfficientNetB3 | 87.76 |
| EfficientNetB0 | 87.46 |
| EfficientNetB4 | 86.59 |
| MobileNetV2 | 85.71 |
| ShuffleNetV2 | 85.13 |
| DenseNet201 | 85.13 |
| ResNet50V2 | 85.13 |
| ResNet18 | 84.26 |
| DenseNet121 | 84.26 |
| ResNet50V1 | 83.38 |
| GBCNet | 74.05 |
| SqueezeNet | 70.26 |
| RadFormer | 58.60 |

---

## 🚀 Usage

### 1. Clone the Repository
```bash
git clone https://github.com/Slightsmile/gallbladder-cancer-detection-dl.git
cd gallbladder-cancer-detection-dl
2. Install Dependencies
pip install -r requirements.txt

3. Run the Python File
python main.py

📦 Requirements

Python 3.9+

PyTorch 2.x

torchvision

scikit-learn

matplotlib

seaborn

numpy

✅ Conclusion

This project demonstrates the potential of deep learning in early gallbladder cancer detection using ultrasound imaging.
The comparative analysis reveals the strengths and weaknesses of different models in handling real-world medical data, with the weighted ensemble achieving the highest accuracy of 89.21%.

🏫 Developed By

Md. Mostofa Nayon
Research and Innovation Project, Daffodil International University
