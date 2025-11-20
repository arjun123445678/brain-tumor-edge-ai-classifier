# brain-tumor-edge-ai-classifier
Brain Tumor Classification Using Edge AI (MobileNetV2 + Edge Impulse)

A real-time, lightweight Edge AI system for classifying brain tumors from MRI images using MobileNetV2 and Edge Impulse.
The model runs efficiently on mobile devices and supports offline on-device inference.

📌 Project Overview

Brain tumors such as Glioma, Meningioma, and Pituitary Adenoma require early identification for better clinical outcomes. However, MRI diagnosis demands expert radiologists and high-resource environments.

This project provides an edge-deployable brain tumor classifier using:

MobileNetV2 Transfer Learning

Edge Impulse Studio

TensorFlow Lite

Mobile real-time inference via QR code

The system achieves 94% accuracy and performs inference in ~8 ms on an Android phone.

🧠 Target Classes

The model classifies brain MRI images into 4 classes:

Glioma Tumor

Meningioma Tumor

Pituitary Tumor

No Tumor (Normal Brain)

📂 Dataset

Source: Kaggle Brain MRI Dataset (open source)

Contains real MRI images from multiple tumor types

~9,000+ images used after cleaning & preprocessing

Dataset was reorganized into 4 folders

Train/Test splitting handled automatically by Edge Impulse
<img width="850" height="863" alt="image" src="https://github.com/user-attachments/assets/221c56ae-69cc-4584-90b5-f4ed4990391c" />


⚙️ Model Architecture

The classifier uses MobileNetV2 (width=0.5) + Transfer Learning.

Model Flow
Input Image (160×160×3)
       ↓
MobileNetV2 Backbone
(Depthwise Conv, Pointwise Conv, Bottleneck Blocks)
       ↓
Global Average Pooling
       ↓
Dense Layer + Softmax
       ↓
4-Class Prediction

🔄 Project Workflow / Methodology

Dataset Preparation

Cleaned and structured 4-class MRI dataset

Applied augmentation (rotation, brightness, contrast)

Edge Impulse Impulse Design

Image preprocessing (160×160)

Transfer Learning with MobileNetV2

Training cycles: 40

Learning rate: 0.0005

Model Training & Evaluation

Accuracy: 94%

Confusion matrix & per-class performance

Stable loss/accuracy curves

Model Optimization

Generated TensorFlow Lite model

Quantized for edge deployment

Deployment

Tested using Edge Impulse Web Runtime

Scanned QR code → model loads on mobile

Real-time inference in ~8 ms

Runs offline and on-device, ensuring privacy

Application Testing

Tested with multiple MRI samples

Consistent predictions on mobile & web

📱 On-Device Deployment

The model runs directly on:

✔ Android devices

✔ Mobile browser

✔ Edge Impulse Web Runtime

✔ No internet required after loading

✔ All inference happens on-device

Example output:

Prediction: No Tumor  
Confidence: 1.00  
Inference time: 8 ms

🚀 Future Work

Deploy on Qualcomm AI Stack (Hexagon NPU)

Port to STM32 microcontrollers using STM32Cube.AI

Port to Arduino Uno R4 WiFi

Add Grad-CAM explainability

Collect more real clinical MRI data

🔗 Edge Impulse Public Project Link

Paste your project link here:

https://studio.edgeimpulse.com/xxxx

📁 Repository Structure
brain-tumor-edge-ai-classifier/
│
├── README.md
├── model/
│   ├── tflite-model.tflite
│   ├── ei-model.json
│   └── labels.txt
│
├── docs/
│   ├── architecture.png
│   ├── flowchart.png
│   ├── confusion_matrix.png
│   ├── accuracy_curve.png
│   └── inference_screenshot.png
│
└── android_test/
    └── inference_results.png

📚 References (IEEE Format)

[1] Kaggle Brain MRI Dataset, 2019.
[2] M. Sandler et al., “MobileNetV2: Inverted Residuals and Linear Bottlenecks,” CVPR, 2018.
[3] Edge Impulse Documentation, 2023.
[4] TensorFlow Lite Documentation, Google, 2023.
