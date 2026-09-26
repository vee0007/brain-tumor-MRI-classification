# 🧠 Brain Tumor MRI Classification

A machine learning project for classifying brain MRI images into four categories: **Glioma, Meningioma, Pituitary, and No Tumor**.

## 🚀 Project Overview

This project uses image preprocessing, handcrafted image features, feature selection, and an **Extra Trees Classifier** to classify brain MRI images.

**Workflow:**

MRI Image → Preprocessing → GLCM + Intensity + HOG → Feature Selection → Extra Trees → Prediction

## 📊 Dataset

**Brain Tumor MRI Dataset** from Kaggle:

https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

- Training images: **5,600**
- Test images: **1,600**
- Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary

## 🔄 Preprocessing

- Convert image to grayscale
- Resize to **128 × 128**
- Apply Gaussian blur
- Normalize image values

## 🔬 Feature Extraction

### GLCM Features
Used to capture texture information:

- Contrast
- Dissimilarity
- Homogeneity
- Energy
- Correlation

### Intensity Features

- Mean
- Standard deviation
- Variance
- Minimum
- Maximum
- Median

### HOG Features

**Histogram of Oriented Gradients (HOG)** is used to capture edge, shape, and structural information from the MRI images.

The combined feature vector contains **1,775 features**.

## 🎯 Feature Selection

Extra Trees feature importance was used to select the most useful features.

| Features | Accuracy |
|---:|---:|
| 250 | 91.79% |
| **500** | **92.59%** |
| 750 | 92.05% |
| 1000 | 92.14% |

The top **500 features** were selected for the final model.

## 🤖 Machine Learning Model

The final classical machine learning model is an **Extra Trees Classifier**.

Hyperparameter tuning was performed using **RandomizedSearchCV**.

- Validation Accuracy: **93.30%**
- Official Test Accuracy: **87.00%**

## 📈 Final Test Performance

The final model was evaluated on the official **1,600-image test set**.

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Glioma | 0.93 | 0.66 | 0.77 |
| Meningioma | 0.82 | 0.85 | 0.84 |
| No Tumor | 0.84 | 1.00 | 0.91 |
| Pituitary | 0.91 | 0.97 | 0.94 |
| **Overall** | **0.88** | **0.87** | **0.87** |

### 🏆 Final Accuracy: 87%

## 🖼️ Single MRI Image Prediction

The trained model can also accept a single uploaded MRI image.

Process:

1. Upload an MRI image.
2. Apply the same preprocessing pipeline.
3. Extract GLCM, intensity, and HOG features.
4. Select the top 500 features.
5. Predict using the trained Extra Trees model.
6. Display the predicted class and prediction probabilities.

## 🛠️ Tech Stack

- Python
- Google Colab
- OpenCV
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- scikit-image

## 📂 Project Structure

```text
brain-tumor-mri-classification/
├── Brain_Tumor_MRI_Classification.ipynb
├── README.md
├── Brain_Tumor_MRI_Classification_Report.pdf
└── results/
    └── confusion_matrix.png
```

## ▶️ How to Run

1. Open the notebook in Google Colab.
2. Set up the Kaggle Brain Tumor MRI Dataset.
3. Run the notebook cells in order.
4. Perform preprocessing and feature extraction.
5. Train the Extra Trees model.
6. Evaluate the model on the official test set.
7. Use the single-image prediction section to test a new MRI image.

## 🔮 Future Goals

- **Implement a CNN-based deep learning model** for direct MRI image classification.
- Compare CNN performance with the current Extra Trees approach.
- Explore whether deep learning can improve the current **87% official test accuracy**.
- Build a simple web interface for single-image prediction.
- Save and load the trained model for easier deployment.

## 🎯 Project Goal

The current project establishes a classical machine learning baseline using handcrafted image features.

The next major goal is to implement a **CNN** and investigate whether automatically learned image features can improve classification performance and generalization.

## 📚 Key Learning Outcomes

- Image preprocessing with OpenCV
- Texture feature extraction using GLCM
- Shape and edge feature extraction using HOG
- Feature selection using Extra Trees importance
- Hyperparameter tuning with RandomizedSearchCV
- Multiclass classification
- Model evaluation using precision, recall, F1-score, and accuracy
- Single-image prediction

## ⚠️ Disclaimer

This is an educational machine learning project. It is **not a medical diagnostic system** and should not be used for clinical decisions.

## 👨‍💻 Author

**Rohit Verma**  
B.Tech Computer Science & Engineering
