# Brain Tumor Detection using YOLOv8

This repository contains a deep learning model for detecting brain tumors from medical images (MRI scans) using the state-of-the-art **YOLOv8** object detection algorithm. 

## Project Overview

The primary goal of this project is to assist medical professionals in the early and accurate detection of brain tumors. By utilizing the YOLOv8 (You Only Look Once version 8) architecture, this model is optimized for high-speed and highly accurate bounding-box predictions on brain scans.

## Key Features

- **Algorithm:** YOLOv8 Nano (`yolov8n.pt`) via the Ultralytics framework.
- **Dataset:** Trained on the comprehensive [Medical Image Dataset for Brain Tumor Detection](https://www.kaggle.com/datasets/pkdarabi/medical-image-dataset-brain-tumor-detection) from Kaggle.
- **Performance:** Achieved a high Mean Average Precision (mAP50) of ~0.90+ during validation.
- **Ready to Use:** Includes the pre-trained weights file (`best.pt`) so you can immediately run inference without retraining.

## Repository Contents

- `Brain_Tumor_Yolo_Model.ipynb`: A complete Jupyter Notebook containing the code for setting up the environment, downloading the dataset via the Kaggle API, training the YOLOv8 model for 100 epochs, and validating the results.
- `best.pt`: The exported PyTorch weights of the best-performing model from the training run.

## How to Use (Inference)

You can easily use the provided `best.pt` weights to run inference on your own MRI images. 

1. **Install Ultralytics:**
   ```bash
   pip install ultralytics
   ```

2. **Run Prediction (Python):**
   ```python
   from ultralytics import YOLO

   # Load the trained model
   model = YOLO("best.pt")

   # Run inference on an image
   results = model.predict(source="path/to/your/mri_scan.jpg", show=True, save=True)
   ```

## Training Configuration

If you wish to retrain the model, the notebook provides the exact configuration used:
- **Epochs:** 100
- **Image Size:** 640x640
- **Batch Size:** 16
- **Optimizer:** AdamW

## Disclaimer
*This model is for educational and research purposes only. It is not intended to replace professional medical diagnosis.*
