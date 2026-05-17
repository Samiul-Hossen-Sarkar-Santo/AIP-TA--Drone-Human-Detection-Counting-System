# Drone Human Detection & Counting System

This project was developed as part of the ANTLINGS Internship Program Recruitment Test conducted by ANTS Aerial Systems Ltd.

The system performs:
- Human detection
- Car detection
- Human counting
- Object tracking using ByteTrack
- Visualization on aerial/drone imagery

---

# Project Overview

The goal of this project is to build a computer vision pipeline capable of detecting humans and cars from aerial/drone imagery and counting the total number of humans present in a scene.

The pipeline includes:
- Dataset preprocessing
- Label filtering and remapping
- YOLOv8 model training
- Evaluation and visualization
- Human counting
- Video tracking

---

# Dataset

Dataset Used:
- VisDrone2019 Detection Dataset

Selected Classes:
| Original Class | Final Class |
|---|---|
| pedestrian | Human |
| people | Human |
| car | Car |

The dataset annotations were already available in YOLO format.

---

# Preprocessing Pipeline

The preprocessing stage performs:
- filtering unwanted classes
- merging pedestrian and people into a single Human class
- remapping labels
- generating train/validation/test splits

---

# Model Architecture

Model Used:
- YOLOv8s

Reason for Selection:
- lightweight and fast
- strong real-time performance
- suitable for small-object aerial detection

---

# Training Configuration

| Parameter | Value |
|---|---|
| Epochs | 50 / 100 |
| Image Size | 640 |
| Batch Size | 16 |
| Optimizer | Auto |
| GPU | Tesla T4 |

---

# Evaluation Metrics

| Metric | Score |
|---|---|
| mAP50 | 0.5057 |
| mAP50-95 | 0.2786 |
| Precision | 0.6609 |
| Recall | 0.4894 |

---

# Results

## Dataset Samples for 50 epochs

![Dataset Samples](presentation_assets/dataset_samples.png)

---

## Class Distribution for 50 epochs

![Class Distribution](presentation_assets_50_epoch/class_distribution_50_epoch.png)

---

## Training Curves for 50 epochs

![Training Results](presentation_assets_50_epoch/results_50_epoch.png)

---

## Precision-Recall Curve for 50 epochs

![PR Curve](presentation_assets_50_epoch/PR_curve_50_epoch.png)

---

## Confusion Matrix for 50 epochs

![Confusion Matrix](presentation_assets_50_epoch/confusion_matrix_normalized_50_epoch.png)

---

## Human Counting Results for 50 epochs

![Counting Results](presentation_assets_50_epoch/counting_visualization_50_epoch.png)

---

# Object Tracking

ByteTrack was integrated for object tracking across video frames.

Tracking Features:
- persistent object IDs
- smoother temporal detection
- multi-frame object association

---

# Challenges Faced

- Tiny human detection from high-altitude drone imagery
- Scale variation between humans and vehicles
- Occlusion in crowded scenes
- Low-resolution distant objects

---

# Limitations

- Tiny distant humans may occasionally be missed
- Tracking quality depends on video quality and resolution
- False positives may occur at lower confidence thresholds

---

# Future Improvements

Potential future improvements include:
- SAHI-based sliced inference
- larger YOLO variants
- higher resolution training
- advanced tracking algorithms
- real-time deployment optimization

---

# Project Structure

```text
project/
│
├── notebook.ipynb
├── weights/
├── presentation_assets/
├── inference_results/
├── counting_results/
├── tracking_results/
└── README.md
```

---

# Demo Video

[Insert Google Drive / YouTube Link Here]

---

# Author

Samiul Hossen  
Bangladesh University of Professionals
