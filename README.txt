# Vehiclator 🚗✈️🚢

I developed **Vehiclator** as an individual project to classify vehicles into three main categories — **land**, **air**, and **sea** — using deep learning techniques. The system is built to recognize vehicle types from images, even in cases where the visuals are ambiguous or challenging due to perspective, background noise, or quality.

## 🧠 Project Overview

The idea for Vehiclator came from the challenge of image-based vehicle classification and its practical applications in areas such as:

- Intelligent transportation systems  
- Self-driving vehicles  
- Military and security use-cases  
- Smart surveillance systems  

This was both a technically and intellectually rewarding task that pushed me to understand how convolutional neural networks (CNNs) learn from image data, how to mitigate overfitting, and how to deal with real-world data complexity.


I implemented two models during this project — a simple CNN and a more complex one. Here's a summary of the models:

## 🏗️ Simple Model Architecture

For the first phase of the project, I used a simple Convolutional Neural Network (CNN) because it was fast to implement, trained quickly, and allowed me to get early feedback on how the model was learning. This model served as a strong baseline.

- **Input:** 224x224 RGB images
- **Layers:**
  - Three convolutional layers with filters: 32 → 64 → 128  
  - Each Conv layer is followed by ReLU activation and MaxPooling
  - A flatten layer to convert the output into 1D
  - A dense layer with 128 neurons (ReLU)
  - Output layer with 3 neurons (Softmax for land, air, sea)
- **Loss Function:** `sparse_categorical_crossentropy`
- **Optimizer:** Adam
- **Training:** 4 epochs

Despite its simplicity, this model achieved **very high accuracy** with minimal training.


## 🏗️ Complex Model Architecture

- **Framework:** TensorFlow (Sequential API)
- **Input:** 224x224 RGB images
- **Layers:**
  - Three convolutional blocks with increasing filter sizes (32 → 64 → 128)
  - Batch Normalization and Max Pooling
  - Dense layers: 256 → 128 with ReLU activations
  - Dropout layers to reduce overfitting
  - Output: Softmax layer with 3 units (land, air, sea)
- **Loss Function:** `sparse_categorical_crossentropy`
- **Optimizer:** Adam
- **Training:** 4 epochs with 80/20 train-validation split

Despite the complexity of this model, the simpler version surprisingly achieved better accuracy due to the nature of the dataset. This taught me that "more complex" does not always mean "better."


## 📊 Dataset

I used publicly available datasets from Kaggle and academic repositories. The data was split as follows:

| Class | # Train Images | # Test Images |
|-------|----------------|---------------|
| Land  | 8,144          | 8,041         |
| Sea   | 7,406          | 7,406         |
| Air   | 10,000         | 6,538         |

Dataset Credits:
I.	Land Vehicles: Stanford Cars Dataset
[1] J. Krause, M. Stark, J. Deng, and L. Fei-Fei, "3D Object Representations for Fine-Grained Categorization," in 4th IEEE Workshop on 3D Representation and Recognition, at ICCV 2013. (3dRR-13), Sydney, Australia, Dec. 8, 2013

II.	Air Vehicles: FGVC-Aircraft Dataset
[2] Fine-Grained Visual Classification of Aircraft, S. Maji, J. Kannala, E. Rahtu, M. Blaschko, A. Vedaldi, arXiv.org, 2013.

III.	Sea Vehicles:
[3] V. Shanawad, "Ships Dataset," Kaggle. [Online]. Available: [https://www.kaggle.com/datasets/vinayakshanawad/ships-dataset]. [Accessed: 25.03.2025].

IV.	Air Vehicles (Test):  Commercial Aircraft Dataset
[4] Nelyg8002000. (2023). Commercial Aircraft Dataset [Data set]. Kaggle. [Online]. Available: [https://www.kaggle.com/datasets/nelyg8002000/commercial-aircraft-dataset]. [Accessed: 05.05.2025].


## 📈 Results
| Model          | Accuracy | Loss   |
|----------------|----------|--------|
| Simple Model   | 99.62%   | 0.0108 |
| Complex Model  | 98.28%   | 0.0812 |

The complex model underperformed slightly, likely due to overfitting and unnecessary regularization. This highlighted the importance of choosing the model architecture based on **data complexity**, not just theoretical sophistication.


## 🧰 Technologies Used
- Python
- TensorFlow
- NumPy, Matplotlib
- Jupyter Notebook


İlke Durmaz. 
May, 2025.
