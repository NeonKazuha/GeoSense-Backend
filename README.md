# GeoSense-Backend

## Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Technical Implementation](#technical-implementation)
  - [SAM Model Configuration](#sam-model-configuration)
- [Technical Dependencies](#technical-dependencies)
- [Installation Process](#installation-process)
  - [1. Repository Setup](#1-repository-setup)
  - [2. Virtual Environment Configuration](#2-virtual-environment-configuration)
  - [3. Dependency Installation](#3-dependency-installation)
- [Implementation Guide](#implementation-guide)
  - [Data Preparation](#data-preparation)
  - [Prediction Execution](#prediction-execution)
  - [Analysis Notebooks](#analysis-notebooks)
- [Project Structure](#project-structure)
- [Licensing](#licensing)

## Overview

GeoSense-Backend is an advanced machine learning system designed for precise land boundary detection. The system utilizes the Segment-Anything Model (SAM) architecture to achieve highly accurate boundary detection in geospatial data. Through integration with Roboflow for data annotation, the system provides comprehensive land segmentation capabilities with documented accuracy rates of 99%.

## Key Features

- Advanced Land Boundary Detection: Implementation of deep learning algorithms for precise boundary identification
- Optimized Segment-Anything Model: Custom-tuned SAM implementation specifically adapted for land imagery analysis
- Comprehensive Training Dataset: Extensive collection of annotated land boundary imagery
- Efficient Processing: Optimized for high-throughput analysis of geospatial data
- Professional Data Annotation: Integration with Roboflow for systematic data labeling

## Technical Implementation

### SAM Model Configuration

The implementation of the Segment Anything Model includes the following specifications:

- Dataset Configuration: High-resolution land boundary imagery with professional annotations
- Model Architecture: Vision Transformer (ViT) backbone with enhanced encoder-decoder segmentation pipeline
- Training Parameters:
  - Batch size range: 16-64
  - Optimizer: AdamW
  - Learning rate schedule: Cosine Annealing
  - Gradient Clipping: 1.0
  - Loss functions: Combined Dice Loss and Focal Loss
- Evaluation Metrics: IoU, Dice Score, and mAP for comprehensive performance assessment

The system implements domain-specific augmentation techniques to optimize the mask decoder for terrain feature detection.

## Technical Dependencies

The system relies on the following primary components:

- opencv-python: Image processing and data preprocessing
- torch: Deep learning framework implementation
- torchvision: Computer vision model support
- fastapi: API framework implementation
- uvicorn: ASGI server implementation
- segment_anything: SAM model integration
- supervision: Segmentation and visualization toolkit
- python-multipart: FastAPI file upload management

## Installation Process

### 1. Repository Setup

```bash
git clone https://github.com/NeonKazuha/GeoSense-Backend.git
cd GeoSense-Backend
```

### 2. Virtual Environment Configuration

```bash
python3 -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
```

### 3. Dependency Installation

```bash
pip install -r requirements.txt
```

## Implementation Guide

### Data Preparation
Place geospatial datasets in the designated directory. Ensure compatibility with supported formats (CSV, GeoJSON) and verify the presence of necessary satellite imagery features.

### Prediction Execution

```bash
python predict.py --input your_dataset.csv --output predictions.csv
```

Specify the input dataset file and designated output location for boundary predictions.

### Analysis Notebooks

Access the provided Jupyter Notebooks for detailed analysis:

```bash
jupyter notebook
```

Available notebooks include:
- Segment-Boundary-Model-2.ipynb: Training and evaluation protocols
- image_predictor_example.ipynb: Implementation examples
- sam_2_2.ipynb: SAM optimization procedures

## Project Structure

```
GeoSense-Backend/
│
├── notebooks/
│   ├── Segment-Boundary-Model-2.ipynb    # Training and evaluation protocols
│   │   └── Contains:
│   │       - Model training procedures
│   │       - Performance metrics
│   │       - Validation methods
│   │
│   ├── image_predictor_example.ipynb     # Implementation examples
│   │   └── Contains:
│   │       - Usage demonstrations
│   │       - Sample predictions
│   │       - Real-world applications
│   │
│   └── sam_2_2.ipynb                     # SAM optimization procedures
│       └── Contains:
│           - Parameter tuning
│           - Architecture modifications
│           - Performance improvements
│
├── predict.py          # Prediction implementation
├── requirements.txt    # Dependency specifications
├── .gitignore         # Version control exclusions
└── LICENSE            # Legal documentation
```

## Licensing

This project is distributed under the Apache License 2.0. Reference the LICENSE file for complete terms and conditions.