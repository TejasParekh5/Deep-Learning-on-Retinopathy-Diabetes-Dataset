# Diabetic Retinopathy Detection Using Convolutional Neural Networks (CNN)

Diabetic retinopathy (DR) is one of the leading causes of blindness in working-age adults. This project presents a deep learning framework for automated DR detection using Convolutional Neural Networks (CNNs) and ResNet-based architectures enhanced with transfer learning. The system is designed to classify retinal images into various stages of DR, with a focus on improving diagnostic accuracy and generalization through advanced preprocessing, temporal modeling, and clinical integration.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Results and Analysis](#results-and-analysis)
- [Future Work](#future-work)
- [Acknowledgments](#acknowledgments)
- [License](#license)

---

## Overview

This project aims to automate the detection of diabetic retinopathy using state-of-the-art deep learning techniques. Key components include:
- **Advanced Preprocessing:** Image resizing, normalization, and a comprehensive data augmentation pipeline.
- **Deep Learning Models:** A custom CNN and a ResNet-based model with residual connections for enhanced feature extraction.
- **Transfer Learning:** Utilization of pre-trained networks (e.g., ResNet-101) to improve performance, especially in data-limited scenarios.
- **Temporal Modeling:** Future integration of RNNs or LSTM layers to analyze sequential retinal images and capture disease progression.
- **Real-World Deployment:** Addressing challenges such as data variability, hardware limitations, and integration into clinical workflows.
- **Clinical Collaboration:** Emphasis on partnerships with healthcare professionals for continuous model refinement and validation.

---

## Features

- **Automated DR Detection:** Classifies retinal images into five DR stages (No DR, Mild, Moderate, Severe, and Proliferative DR).
- **Robust Preprocessing:** Employs techniques to normalize images and enhance dataset diversity.
- **Comparative Analysis:** Benchmarks deep learning performance against traditional methods.
- **Scalable Architecture:** Designed to adapt to different imaging conditions and expanded clinical datasets.
- **Future Extensions:** Roadmap includes temporal modeling and integration of explainability tools (e.g., heatmaps) for clinical trust.

---

## Installation

### Prerequisites

- Python 3.7 or higher
- TensorFlow (or PyTorch, depending on your implementation)
- Keras
- NumPy
- OpenCV
- Matplotlib

### Steps

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Tejas-Parekh5/Deep-Learning-on-Retinopathy-Diabetes-Dataset.git
   cd Deep-Learning-on-Retinopathy-Diabetes-Dataset

2. **Create a Virtual Environment:**

   ```bash
   python -m venv dr_env
   source dr_env/bin/activate  # On Windows, use `dr_env\Scripts\activate`

3. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt

Ensure that your requirements.txt file is updated with all necessary packages.   

---

## Usage

### Data Preparation
1. **Download the Dataset:**  
   Download the [Kaggle Diabetic Retinopathy Dataset](https://www.kaggle.com/c/diabetic-retinopathy-detection/data) and place the images in the designated folder.

2. **Run the Preprocessing Script:**  
   This script resizes, normalizes, and augments the images.
   ```bash
   python preprocess.py

### Model Training
1. **Train the CNN Model:**
Execute the script to train the custom CNN model.
   ```bash
   python train_cnn.py

2. **Train the ResNet-Based Model:**
Execute the script to train the ResNet-based model.
   ```bash
   python train_resnet.py

Both scripts include EarlyStopping and ModelCheckpoint callbacks to avoid overfitting and save the best model.

## Evaluation
After training, run the following command to generate metrics, confusion matrices, and accuracy/loss curves.
      
      python evaluate.py
 
This README snippet provides clear instructions on how to prepare the data, train the models, and evaluate their performance.

---

## Dataset
The project utilizes the Kaggle Diabetic Retinopathy Dataset, consisting of tens of thousands of high-resolution retinal images. Each image is annotated by an ophthalmologist into one of five DR stages:

0: No DR
1: Mild DR
2: Moderate DR
3: Severe DR
4: Proliferative DR
Given the class imbalance—with most images labeled as No DR or Mild DR—our approach employs advanced data augmentation techniques to ensure robust model training.

---

## Model Architecture

### Custom CNN
**Convolutional Layers:** Multiple layers with 3x3 filters and ReLU activations for feature extraction.
**MaxPooling Layers:** Reduce spatial dimensions to emphasize salient features.
**Fully Connected Layers:** Include dropout for regularization.
**Output Layer:** Softmax layer for multi-class classification.

### ResNet-Based Model
**Residual Blocks:** Incorporate shortcut connections to alleviate vanishing gradients.
**Global Average Pooling:** Reduces the dimensions of feature maps before classification.
**Softmax Output Layer:** For final classification across the five DR stages.

---

## Results and Analysis
**Evaluation Metrics:** Accuracy, precision, recall, and F1-score for each DR stage.
**Performance:** The CNN achieved approximately 91.34% training accuracy and 90.58% validation accuracy, while the ResNet model reached about 93.32% validation accuracy.
**Confusion Matrices:** Detailed matrices are generated for both models.
Comparison with Traditional Methods: Deep learning approaches show a 10–15% improvement over traditional methods (e.g., SVMs with hand-crafted features).
**Visualization:** Accuracy and loss curves confirm effective training and early stopping.

---

## Future Work
**Advanced ResNet Architectures:** Investigate deeper networks (e.g., ResNet-101) and ensemble methods to capture intricate features and improve diagnostic accuracy.
**Temporal Modeling:** Develop hybrid architectures that integrate CNN/ResNet with RNN or LSTM layers to analyze disease progression over time. Optimizing sequence length and temporal resolution will be key.
**Diverse Datasets:** Expand the dataset to include a broader range of images from multiple clinical sources to ensure the model generalizes well across different populations and imaging conditions.
**Real-World Deployment and Explainability:** Pilot deployments in clinical settings and incorporate interpretability tools (e.g., heatmaps, saliency maps) to provide clinicians with insights into model decisions.
**Healthcare Collaborations:** Establish and maintain partnerships with medical professionals for continuous feedback, model refinement, and clinical validation.

---

## Acknowledgments
We extend our sincere gratitude to our collaborators at NMIMS University and our clinical partners for their invaluable insights and support. We also thank the open-source community for providing the datasets and deep learning frameworks that made this project possible.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

This README is comprehensive and humanized, providing clear instructions on project usage, installation, and future research directions while addressing key aspects of the project as discussed.
